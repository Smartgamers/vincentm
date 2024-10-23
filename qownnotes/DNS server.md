DNS server
========================

DNS is the phonebook of ip addresses. Responsible for knowing what domainnames goes with what ip.

when typing a domain name, you are sending a DNS querie to a DNS resolver. This server will then have to resolve your DNS request to be able to. Connecting you to a Origin server, or a CDN edge server so you can access website information like, html and css.

![Skärmbild 2024-10-02 010925](../../media/Skärmbild 2024-10-02 010925.png)

In a DNS query, there are four servers working thogheter to deliver an ip based on a domain name to the DNS client.
- Recursive resolvers
- Root nameservers
- TLD nameservers
- Authorative nameservers

---

**Recursive resolver**
The recursive resolver *also known as* DNS resolver
is a type of server that recives DNS queries from DNS clients and
acts like a second dns client. Sending queries to the three nameservers. This proccess is called *DNS resolution* or *DNS lookup*.
It will also store resolved DNS queries in cache. This means that futer domain name request can be solved locally on the DNS resolver, inturn reducess nameserver traffic and decreases latency.

He is a middle man inbetween you and the nameservers. Storing DNS query results in cache to reduce DNS traffic for the nameservers.

---
**Root nameservers**
The first nameserver to be contacted in a DNS querie. The Root nameserver is a group of 12 orginasations that controll and manage the 13 root nameserver groups. just a little less than two thousand servers make up these root nameserver groups. One of the root nameserver sees what the top level domain(TLD) of that domain name is, for example .com or .co. It then give you the top level domain server resposible of that TLD.

He knows who to call based on the top level domain. he dosent know any .com's but he does know the TLD who knows.

---

**TLD nameserver**
The TLD nameserver is the second nameserver that will be contacted in a DNS request. Every TLD server will store ip addresses of the Authorative nameserver for a specific TLD(.com .net .no) It does this by requesting the Authorative server in charge of the domain names second level domain(SLD spinach.com football.com) The DNS resolver will then querie the Authorative nameserver in charge of that SDL.

The TLD nameserver can trackdown the Authoratative nameserver based on the SDL. But this is only if you are in his top level domain.

---

**Authorative nameservers**
The Authorative nameserver is the last nameserver the DNS resolver contacts. The Authoratative nameserver will store zonefiles. This file will store the SOA(State of authorety). This tell you whos in charge of the domain name. The SOA will store the ip address of the website or subdomain. With this, the DNS resolver can finnaly send back the website information to the DNS client aka you.





