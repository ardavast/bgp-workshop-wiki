# Preparation
1. Find a place with enough tables and chairs.
2. Find a managed switch that you can configure.
3. Create VMs or containers that will be your routers.
4. Create the event and share it with the world (NOG or RIPE mailing lists).
5. Ask RIPE for temporary IPv4 and IPv6 allocations. For this you would need a sponsoring LIR.  
   HINT: I can always help with this, but do give me enough lead time (at least two weeks).
6. Prepare a basic introductory talk about BGP. Make sure you explain ASNs and why you can have a single AS originating prefixes from two or more different locations. You can also explain anycast.
7. Generate files for each client/port. If possible, upload them somewhere or print them for the participants (you can use the gen-client-data.sh for this).

# During the workshop
1. Make the presentation.
2. Give each participant a copy or URL to his own configuration.
3. Explain the tasks:
    * Setting up the VLANs.
    * Connecting to the upstream routers (in my case Tom & Jerry).
    * Connecting to the Internet Exchange routers.
    * Choosing a prefix to peer with your neighbors on the switch and peer with them.
    * Play with local preference:
        * Prefer your neighbor prefix from one of the upstreams (instead of the peer).
        * Prefer your neighbor prefix from one of the IXes (instead of the peer).
        * Test failover routes, by dropping the session to your peer and observing that the route has changed via one of the IXes or one of the upstreams.

# Some hints
* Always make sure that you have connectivity between the participants machines and the routers they try to connect to.
  You would be surprised how many people simply skip pinging the remote machine, before setting up BGP with it :)
* Ask the participants to first configure a single VLAN and a single BGP session with one of the upstreams, then continue with the next router.
* Advise everyone to start configuring IPv6 after they have successfully connected with all IPv4 peers
* Have a laptop connected to a projector, displaying the output from one or more of the routers. I use a simple looking glass for this: https://github.com/hackman/bird-lg-perl  
  This way everyone can see if they are connected to the upstreams or if they are leaking the whole BGP table into the exchanges :)

# More advanced tasks, that can be done during the workshop
* Configure BGP communities.
* Enable and test BFD.
