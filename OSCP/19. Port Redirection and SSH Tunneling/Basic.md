
## Flat Networks
Most network environments are not -and should not be- [_flat_](https://en.wikipedia.org/wiki/Flat_network), In a flat network, all devices are able to communicate freely with each other. There is little (or no) attempt to limit the access that each device has to other devices on the same network, regardless of whether devices need to communicate during normal operations.

Flat network topology is generally considered poor security practice. Once an attacker has access to a single host, they can start communicating with every other host. From there, it will be much easier to spread through the network and start compromising other hosts.

## Segmented Networks
A more securely designed network type is [_segmented_](https://en.wikipedia.org/wiki/Network_segmentation). This type of network will be broken into smaller networks, each of which is called a [_subnet_](https://en.wikipedia.org/wiki/Subnetwork). Each subnet will contain a group of devices that have a specific purpose, and devices on that subnet are only granted access to other subnets and hosts when absolutely necessary. Network segmentation severely limits attackers, because compromising a single host no longer gives them free access to every other device on the network.

As part of the network segmentation process, most network administrators will also implement controls that limit the flow of traffic into, out from, and across their networks. To enforce this, they will deploy various technologies throughout the network.

## How is it done
One of the most common technologies used for this is [_Firewalls_](https://en.wikipedia.org/wiki/Firewall_\(computing\)). Firewalls can be implemented at the endpoint software level. For example, the _Linux kernel_ has firewall capabilities that can be configured with the [_iptables_](https://en.wikipedia.org/wiki/Iptables) tool suite, while Windows offers the built-in [_Windows Defender Firewall_](https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). Firewalls may also be implemented as features within a piece of physical network infrastructure. Administrators may even place a standalone _hardware firewall_ in the network, filtering all traffic.

Firewalls can drop unwanted inbound packets and prevent potentially malicious traffic from traversing or leaving the network. Firewalls may prevent all but a few allowed hosts from communicating with a port on a particularly privileged server. They can also block some hosts or subnets from accessing the wider _internet_.

Most firewalls tend to allow or block traffic in line with a set of rules based on _IP addresses_ and _port numbers_, so their functionality is limited. However, sometimes more fine-grained control is required. [_Deep Packet Inspection_](https://en.wikipedia.org/wiki/Deep_packet_inspection) monitors the contents of incoming and outgoing traffic and terminates it based on a set of rules.

Boundaries that are put in place by network administrators are designed to prevent the _arbitrary movement of data into, out of, and across the network_. But, as an attacker, these are exactly the boundaries we need to traverse. We'll need to develop strategies that can help us work around network restrictions as we find them.

_Port redirection_ (a term we are using to describe various types of [_port forwarding_](https://en.wikipedia.org/wiki/Port_forwarding)) and [_tunneling_](https://en.wikipedia.org/wiki/Tunneling_protocol) are both strategies we can use to traverse these boundaries. Port redirection modifies the data flow by redirecting packets from one socket to another. Tunneling means [_encapsulating_](https://en.wikipedia.org/wiki/Encapsulation_\(networking\)) one type of data stream within another, for example, transporting _Hypertext Transfer Protocol_ (HTTP) traffic within a _Secure Shell_ (SSH) connection (so from an external perspective, only the SSH traffic will be visible).


