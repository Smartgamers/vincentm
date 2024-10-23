Hacking tools
========================

crt.sh
========================
Certificate Transparency (CT) is a system designed to increase trust in the global PKI by making it possible for anyone to observe and verify the issuance of digital certificates. crt.sh allows you to search for `specific domains`, `IPs`, or `certificates` within these logs. 

For bug bounty recon, crt.sh can be useful for identifying potential targets that have been issued certificates in the past.

 ![qownnotes-media-hnNTGY](../../../media/qownnotes-media-hnNTGY.png)

![qownnotes-media-lRuJQc](../../../media/qownnotes-media-lRuJQc.png)


host
========================
host is a linux command that lets you get website info like

to find a websites ip
    `$host google.com`  ***or*** `$host zophar.net`
    
Also email servers.

```
$host yahoo.com

yahoo.com has address 98.137.11.164
yahoo.com has address 74.6.143.25
yahoo.com has address 74.6.143.26
yahoo.com has address 74.6.231.20
yahoo.com has address 74.6.231.21
yahoo.com has address 98.137.11.163
yahoo.com has IPv6 address 2001:4998:44:3507::8001
yahoo.com has IPv6 address 2001:4998:124:1507::f001
yahoo.com has IPv6 address 2001:4998:124:1507::f000
yahoo.com has IPv6 address 2001:4998:24:120d::1:1
yahoo.com has IPv6 address 2001:4998:24:120d::1:0
yahoo.com has IPv6 address 2001:4998:44:3507::8000
yahoo.com mail is handled by 1 mta7.am0.yahoodns.net.
yahoo.com mail is handled by 1 mta5.am0.yahoodns.net.
yahoo.com mail is handled by 1 mta6.am0.yahoodns.net.
```


Shodan
========================

Shodan costs 70$ a month,
but the free version with limited scans is free.

Shodan tracks and logs devices and vulnrebileties in those devices, without doing anything.
Hackers and maybe pen testers can then get that info and act on these vulnreable devices.

we can use it in website hacking with (example)
     ` $shodan host 74.6.143.25`(yahoo.com's ip)
     
![shodan host yahoo.coms ip](../../../media/qownnotes-media-AGMzXp.png)

Shodans official website shodan.io also has a nice gui  and a bunch of search query examples and more!



theharvester
========================

theharvester is a linux command that can give a huge amount of info on a domain. Inculiding IPs emails and hosts aka domains.

$ theHarvester -d google.com -b duckduckgo
Read proxies.yaml from /config/.theHarvester/proxies.yaml
*******************************************************************
*  _   _                                            _             *
* | |_| |__   ___    /\  /\__ _ _ ____   _____  ___| |_ ___ _ __  *
* | __|  _ \ / _ \  / /_/ / _` | '__\ \ / / _ \/ __| __/ _ \ '__| *
* | |_| | | |  __/ / __  / (_| | |   \ V /  __/\__ \ ||  __/ |    *
*  \__|_| |_|\___| \/ /_/ \__,_|_|    \_/ \___||___/\__\___|_|    *
*                                                                 *
* theHarvester 4.6.0                                              *
* Coded by Christian Martorella                                   *
* Edge-Security Research                                          *
* cmartorella@edge-security.com                                   *
*                                                                 *
*******************************************************************

`[*] Target: google.com `

`[*] Searching Duckduckgo. `

`[*] No IPs found.`

`[*] No emails found.`

[*] Hosts found: 14
---------------------
.google.com
2Fencrypted.google.com
2Fpatents.google.com
2Fsupport.google.com
Encrypted.google.com
accounts.google.com
apis.google.com
consent.google.com
encrypted.google.com
ogs.google.com
patents.google.com
policies.google.com
support.google.com
trends.google.com


whois
========================
who is is a linux command that lets you get a holebunch of information regarding a domain. Anything from mail servers to Registrar URLs


$ whois example.com

   Domain Name: EXAMPLE.COM
`   Registry Domain ID: 2336799_DOMAIN_COM-VRSN`
`   Registrar WHOIS Server: whois.iana.org`
   Registrar URL: http://res-dom.iana.org
`   Updated Date: 2024-08-14T07:01:34Z`
   Creation Date: 1995-08-14T04:00:00Z
   Registry Expiry Date: 2025-08-13T04:00:00Z
`   Registrar: RESERVED-Internet Assigned Numbers Authority`
`   Registrar IANA ID: 376`
   Registrar Abuse Contact Email:
   Registrar Abuse Contact Phone:
   Domain Status: clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited
   Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
   Domain Status: clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited
`   Name Server: A.IANA-SERVERS.NET`
`   Name Server: B.IANA-SERVERS.NET`
   DNSSEC: signedDelegation
   DNSSEC DS Data: 370 13 2 BE74359954660069D5C63D200C39F5603827D7DD02B56F120EE9F3A86764247C
   URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/
>>> Last update of whois database: 2024-10-07T21:43:24Z <<<

For more information on Whois status codes, please visit https://icann.org/epp

NOTICE: The expiration date displayed in this record is the date the
registrar's sponsorship of the domain name registration in the registry is
currently set to expire. This date does not necessarily reflect the expiration
date of the domain name registrant's agreement with the sponsoring
registrar.  Users may consult the sponsoring registrar's Whois database to
view the registrar's reported date of expiration for this registration.

TERMS OF USE: You are not authorized to access or query our Whois
database through the use of electronic processes that are high-volume and
automated except as reasonably necessary to register domain names or
modify existing registrations; the Data in VeriSign Global Registry
Services' ("VeriSign") Whois database is provided by VeriSign for
information purposes only, and to assist persons in obtaining information
about or related to a domain name registration record. VeriSign does not
guarantee its accuracy. By submitting a Whois query, you agree to abide
by the following terms of use: You agree that you may use this Data only
for lawful purposes and that under no circumstances will you use this Data
to: (1) allow, enable, or otherwise support the transmission of mass
unsolicited, commercial advertising or solicitations via e-mail, telephone,
or facsimile; or (2) enable high volume, automated, electronic processes
that apply to VeriSign (or its computer systems). The compilation,
repackaging, dissemination or other use of this Data is expressly
prohibited without the prior written consent of VeriSign. You agree not to
use electronic processes that are automated and high-volume to access or
query the Whois database except as reasonably necessary to register
domain names or modify existing registrations. VeriSign reserves the right
to restrict your access to the Whois database in its sole discretion to ensure
operational stability.  VeriSign may restrict or terminate your access to the
Whois database for failure to abide by these terms of use. VeriSign
reserves the right to modify these terms at any time.

The Registry database contains ONLY .COM, .NET, .EDU domains and
Registrars.
% IANA WHOIS server
% for more information on IANA, visit http://www.iana.org
% This query returned 1 object

domain:       EXAMPLE.COM

organisation: Internet Assigned Numbers Authority

created:      1992-01-01
source:       IANA

