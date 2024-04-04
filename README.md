****Raft Consensus Algorithm Implementation****
This project implements the Raft consensus algorithm using gRPC for inter-node communication. Raft is a distributed consensus algorithm designed to ensure the consistency of replicated logs in distributed systems.

**Features**
Leader Election: Nodes initiate leader elections when the current leader fails or when a new node joins the cluster.
Log Replication: Logs are replicated across all nodes in the cluster to ensure consistency.
Heartbeat Mechanism: The leader sends regular heartbeat messages to maintain its leadership and prevent elections.

**Components**
Node Class
The Node class represents a single node in the Raft cluster. Each node is responsible for managing its state, handling RPC calls, and participating in leader election and log replication processes.

**Methods**
ServeClient: Handles client requests when the node is in the leader state.
AppendEntries: Handles AppendEntries RPC calls from the leader for log replication.
Voting: Handles VoteRequest RPC calls during leader election.
start_election: Initiates leader election process.
become_leader: Transitions a node to the leader state.
send_heartbeats: Sends periodic heartbeat messages to maintain leadership.

**Server Function**
The serve function initializes a gRPC server for each node and starts serving requests. It also handles graceful server termination upon keyboard interrupt.

**Usage**
Clone the repository.
Install required dependencies (grpcio, grpcio-tools).
Run the main.py file and follow the prompts to specify the port and election timeout for each node.

**Configuration**
Adjust the HEARTBEAT_INTERVAL, ELECTION_TIMEOUT_RANGE, and LEADER_LEASE_TIMEOUT constants in the main.py file to fine-tune Raft algorithm parameters.

**Logging**
Logs for each node, including events, leader changes, and RPC calls, are stored in separate log files within the nodes_logs_<port> directory.

**Contributing**
Contributions are welcome! Feel free to submit issues or pull requests for any improvements or bug fixes.

**License**
This project is licensed under the MIT License. See the LICENSE file for details.






