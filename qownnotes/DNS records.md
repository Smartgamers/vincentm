DNS records
========================

There is a zone file in the autoratative name server of a domain. This file carries all tyeps of dns records. We can querie this nameserver for dns records in the zone file. This would usually be used for creating backups.

There are many diffrent types of dns records. All carrying diffrent information. You can request these records with caommands like `$dig example.com A ` for ipv4 address of example.com.  You could also use`$dig example.com soa ` to get state of authoratie of example.com.


 lets create a example zone file of (exampel.com)
 
 ---
 
> $ORIGIN example.com.    
> $TTL 3600                

**SOA records(start of authoratie)**

> example.com.         IN  SOA   ns1.example.com. username.example.com. ( 2020091025 7200 3600 1209600 3600 )

> > 2020091025 ; serial number
> 
> > 7200 ; refresh time (7,200 seconds = 2 hours)
> 
> > 3600 ; retry time (3,600 seconds = 1 hour)
> 
> > 1209600 ; expire time (14 days)
> 
> > 3600 ) ; minimum TTL (1 hour)

`soa records can contain information on the authoritative figures(admins mails) and orginasations(company mails) of a zone file. soa records also contain information about serial numbers and refresh times +more.`

`Serial number (2020091025): indicates the version of the zone file`
`Refresh time (7200 seconds = 2 hours): defines how often secondary name servers should check with the primary nameserver for updates`
`Retry time (3600 seconds = 1 hour): sets the time limit for retrying to contact the primary nameserver if an update fails`
`Expire time (1209600 seconds = 14 days): specifies the maximum time a secondary server can cache data before it expires`
`Minimum TTL (3600 seconds = 1 hour): determines how long DNS resolvers will cache this SOA record`

---

**NS records(nameserver*s*)**
> example.com.         IN  NS    ns1.example.com
> example.com.         IN  NS    ns2.example.com
`"NS records identify the nameservers that maintain DNS zone files for individual domains, enabling a single zone file to serve multiple domains."`

---

**A records(ipv4 adresses)**
> example.com.  IN  A     192.0.2.1             
> ns            IN  A     192.0.2.2            

> mail          IN  A     192.0.2.3      
> mail2         IN  A     192.0.2.4          
> mail3         IN  A     192.0.2.5            
`A records map a domain name to a ipv4 address.`

---

**AAAA records(ipv6 addresses)**
> example.com.         IN  AAAA  2001:db8:10::1      
> ns         IN  AAAA  2001:db8:10::2       
`AAAA records map a domain name to one or more ipv6 address*es*.`

---

**MX(mail exchange)**
> example.com.         IN  MX    10 mail.example.com. 
> @             IN  MX    20 mail2.example.com.
> @             IN  MX    50 mail3             
`MX routes mails sent to the domain to be routed to the correct SMTP(simple mail transfer protocol) servers (or email servers). There can often be multiple mail servers with diffrent priorety values for redundancy.`

---

**PTR records(pointer records)**
> 1.2.0.192.in-addr.arpa.         IN PTR exampel.com.
> 2.2.0.192.in-addr.arpa.         IN PTR ns
`PTR records are used for reverse dns lookup, taking a ip address and sending a dns resolv request to find the domain that ip is responible for.`

---

**CNAME(domain name aliase*s*)**

> www.coolexample.com           IN  CNAME example.com.         
> www.testingisinportant.com       IN  CNAME www.coolexample.com
`The cname dns record types lets you create aliases for a website, so if i want you to be able to type www.cool.com to grt to my website. I can create an CNAME for that.`

---

**TXT records(text)**
> example.com.         IN  TXT   "v=spf1 mx:mail.example.com -all"
> example.com.         IN  TXT   "gpg-key: <key-value>"
> example.com.         IN  TXT   "digital-signature: <signature-value>"

`TXT records can and have been used to send human readeble message between people, aswell as documenting functions inside a zone file. Now it is mostly used for authentication.`

---