# Preparations
1. Find a place with enough tables and chairs
2. Find a managed switch, that you can configure
3. Create VMs or Containers that will be your routers
4. Create the event and share it with the world(NOG or RIPE mailing lists)
5. Ask RIPE for temporary allocations IPv4 and IPv6. For this you would need a sponsoring LIR. 
   
   HINT: I can always help with this, but do give me enough leed time(at least two weeks).
6. Prepare an basic introductionary talk about BGP. Make sure you explain ASNs and why you can have a single AS originating prefixes from two or more different locations. You can also explain anycast.
7. Generate files for each client/port. If possible uploaded them somewhere or print them for the participants. (you can use the gen-client-data.sh for this)

# During the workshop
1. Make the presentation
2. Give each participant a copy or url to his own configuration.
3. Explain the tasks:
* Setting up the VLANs
* Connecting to the upstream routers (in my case Tom & Jerry)
* Connecting to the Internet Exchange routers
* Choosing a prefix to peer with your neighbors on the switch and peer with them.
* Play with local preference:
** prefer your neighbor prefix from one of the upstreams(instead of the peer)
** prefer your neighbor prefix from one of the IXes(instead of the peer)
** test failover routes, by droping the session to your peer and observing that the route has changed via one of the IXes or one of the Upstreams

# Some hints:
* Always make sure they have connectivity between the participants machine and the router they try to connect. You would be surprised that many people simply skip pinging the remote machine, before setting a BGP with it :)
* Ask the participants to first configure a single vlan and a single BGP session with one of the upstreams, then continue with the next router.
* Advise everyone to start configuring IPv6 after they have successfully connected with all IPv4 peers
* Have a laptop connected to a projector, displaying the output from one or more of the routers. I use a simple looking glass for this: https://github.com/hackman/bird-lg-perl
  This way eveyone can see if they are connected to the upstreams or if they are leaking the whole BGP table into the exchanges :)


# More advanced tasks, that can be done during the workshop
* Configure BGP communities
* Enable and test BFD