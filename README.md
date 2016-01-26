# A basic Gnutella p2p Client
A simple peer to peer client for a Gnutella like network written in C

Refer to the protocol specification here -> http://rfc-gnutella.sourceforge.net/src/rfc-0_6-draft.html

#### HOW TO BUILD AND RUN?
To build the application use GNU C compiler on Linux. Follow the steps mentioned below

1. To build use the following command.

        gcc ./src/node.c -o node

2. Run the executable "node" by specifying a port as an argument

        ./node 6346


#### USING THE APPLICATION
After successful build and run, a menu will be provided listing the supported commands which are as follows.
 - connect <ip> <port>
 - peers
 - query <key>
 - pingb <ip> <port>
 - bye


#### USAGE GUIDELINES
1. Connect to at least one node (bootstrap node) after starting the application. To connect use the "connect" command and specify ip and port.

    	connect 192.168.1.1 6346

    	connect 192.168.1.2 6346

    	connect 192.168.1.3 6346

2. To view the peers connected to the node, use the "peers" command
	peers

3. To query the network for key value pairs, use the "query" command and specify the query key. Query hits will be displayed.
	    query commonkey

4. To find neighbors of a connected node use the "pingb" command specifying ip and port. The application will return the list of neighbors of the node.

Check the peers command to get list of connected peers.

	    pingb 192.168.1.1

5. To disconnect from all peers and exit the application use the "bye" command.

	    bye


#### LOGGING OF MESSAGES

All the messages received and sent by the application are logged in the "log.txt" file. 

This includes:
 - PING A requests sent/received every 5 seconds and correspong PONG A responses
 - PING B requests send by pingb command and corresponding PONG B responses
 - QUERY requests, QHIT responses
 - JOIN requests and responses
 
Incoming messages are marked as "<--" while outgoing messages are logged as "-->". View the cat command to view the log file.
 	cat log.txt
 

For querying this node from other nodes, we have published three key-value pairs

1. "commonkey":0x110A5150

2. "group20key":0x20

3. "lostkey":0x666
