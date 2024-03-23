#networking #dns

### What is DNS?
Domain Naming System(DNS) is just like the phonebook of the internet. DNS basically translates domain names(e.g. google.com) to [[IP-address]] so that browsers can load internet resources.

Each device connected to the Internet has a unique IP address which other machines use to find the device. DNS servers eliminate the need for humans to memorize IP addresses such as 192.168.1.1 (in IPv4), or more complex newer alphanumeric IP addresses such as 2400:cb00:2048:1::c629:d7a2 (in IPv6).

### How does DNS work?
The process of DNS resolution involves converting a hostname (such as www.example.com) into a computer-friendly IP address (such as 192.168.1.1). An IP address is given to each device on the Internet, and that address is necessary to find the appropriate Internet device - like a street address is used to find a particular home. When a user wants to load a webpage, a translation must occur between what a user types into their web browser (example.com) and the machine-friendly address necessary to locate the example.com webpage.

In order to understand the process behind the DNS resolution, it’s important to learn about the different hardware components a DNS query must pass between. For the web browser, the DNS lookup occurs "behind the scenes" and requires no interaction from the user’s computer apart from the initial request.

### There are 4 DNS servers involved in loading a webpage:
1. ![[DNS recursor]]
2. ![[DNS root nameserver]]
3. ![[TLD nameserver]]
4. ![[Authoritative nameserver]]
### Types of DNS query
1. ![[recursive DNS query]]
2. ![[iterative DNS query]]
3. ![[non-recursive DNS query]]
### DNS Caching
![[DNS caching]]



### Attacking DNS

![[DDOS Attack]]

**Learn More:** https://www.cloudflare.com/learning/dns/what-is-dns/