Stub resolver
========================

The stub resolver Stores(caches) DNS query results(domain name to IP address mappings) locally on the device inside the RAM memory for anywhere from a few minutes, all the way to multiple days. Depending on specific device settings. Usually nothing more than a few minutes.

This lets your device check locally what domain name to map to witch ip address without sending requests to a DNS server. With this we can reduce the requests sent to a DNS server.

The stub resolver is a DNS resolver that caches DNS query results temporarily in RAM, whereas a DNS server typically stores all records indefinitely.
