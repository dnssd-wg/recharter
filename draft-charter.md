Background
----------

Zero configuration networking protocols are well suited to discover services within the scope of a
single link.  In particular, the DNS-SD [RFC 6763] and mDNS [RFC 6762] protocol suite (sometimes
referred to using Apple Computer Inc.'s trademark, Bonjour) are widely used for DNS-based service
discovery and host name resolution on a single link. However, the zero configuration mDNS protocol
is constrained to link-local multicast scope by design, and therefore cannot be used to discover
services on remote links.

The Service Registration Protocol (SRP) [RFC 9665] allows servers to register the services they offer
using unicast DNS. A Discovery Proxy [RFC 8766] enables automatic population of the unicast DNS
namespace with services it learns via mDNS.

With these building blocks it is now possible for clients to discover services using unicast DNS alone.
Service discovery can be extended across a wide area network, going beyong directly connected links.

The scenarios in which multi-link service discovery is required may be zero configuration environments,
environments where administrative configuration is supported, or a mixture of the two.

An example is the [Thread Border Router](https://www.threadgroup.org/Portals/0/documents/support/BorderRouterWhitePaper_657_2.pdf) which implements a [SNAC router](https://datatracker.ietf.org/doc/draft-ietf-snac-simple/), enabling bidirectional
service discovery between a low-power Thread mesh network (using SRP) and Ethernet (using mDNS).
This technology is used by [Matter](https://csa-iot.org/all-solutions/matter/), delivering interoperability between in-home devices from different
manufacturers.


Working Group Description
-------------------------

The focus of the WG is to develop a complete solution for extended, scalable DNS-SD. The WG will
consider the tradeoffs between reusing/extending existing protocols and developing entirely new
ones. It is highly desirable that any new solution is backwardly compatible with existing DNS-SD/mDNS
deployments.

To that end, the DNSSD WG will work on:

Standard-track documents

* Define how to publish SRP-registered names in Multicast DNS, so the services can be discovered by mDNS clients.
* Define mechanisms that improve the efficiency, availability and effectiveness of DNS-SD.
* Define how to resolve conflicts between competing updates for the same name.

Informational documents

* Describe how the different protocol components can be combined to make a complete DNS-SD service
  that is equally accessible by both mDNS and SRP clients.

While developing these, the working group will consider the privacy and security requirements described
by [RFC8882]. It will collaborate with SNAC and other DNS-related working groups when applicable.

The following are out of scope.
- Integration or conflict with other zero-configuration service and naming protocols, such as uPnP and LLMNR.
- Updates to general DNS protocols, unless the responsible area director decides that DNSSD is the best venue for a particular workstream.
