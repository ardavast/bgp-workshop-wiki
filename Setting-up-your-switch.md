### The most important thing is that your participants would always have Internet...

So, in order to achieve that, it is best to have all ports with the untagged VLAN bridged to the untagged local network.

# VLANs
You need one VLAN for Internet Exchange 1 and a second one for Internet Exchange 2. Eveyone should be in these VLANs.

The idea with these VLANs is to emulate the real thing (as if the participant has dedicated links to two IXes).


Every participant should have one dedicated VLAN from him to one of the upstreams and a separate VLAN for the second upstream. Again, the idea is to simmulate a real environment.


The last thing, is that every participant should have a VLAN, which he can use to connect to his neighbors (by switch port). When configuring those VLANs, it is best to configure them to include 3 ports, the port the participant is on, the one before that and the one after that (for example, if the participant is on port 8, he should have VLAN 808, that should include ports 7, 8 and 9).

This way, even if participants are confused who is their neighbor, they will be able to setup one working connection.
