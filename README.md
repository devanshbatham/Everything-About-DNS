# Everything About DNS

This repo aims to explain the basics of DNS at different levels of complexity for readers with various technical backgrounds. 

# List of Contents

- [What is DNS](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#dns)
  - [Explain like I am Five](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-five)
  - [Explain like I am Eleven](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-a-college-student)
  - [Explain like I am a College student](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-a-college-student)
- [Types of servers invloved in DNS resolution process](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#types-of-servers-invloved-in-dns-resolution-process-1)
  - [Explain like I am Five](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-five-1)
  - [Explain like I am Eleven](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-eleven-1)
  - [Explain like I am a College Student](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-a-college-student)
- [Types of DNS queries](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#types-of-dns-queries)
  - [Explain like I am five](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-five-2)
  - [Explain like I am Eleven](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-eleven-2)
  - [Explain like I am a College Student](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-a-college-student-1)
- [What is DNS caching? Where does DNS caching occur?](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#what-is-dns-caching-where-does-dns-caching-occur)
  - [Explain like I am Five](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-five-3)
  - [Explain like I am Eleven](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-eleven-3)
  - [Explain like I am College Student](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-college-student)
- [DNS Glossary]

# What is DNS

## Explain like I am Five

Imagine the Internet is a big zoo. All the animals in the zoo have numbers like 1, 2, 3, 4 instead of names. When you want to see an animal, you have to remember its number and go find it. That would be hard to remember!

Instead, the zoo has a special directory. The people who work at the zoo give all the animals fun names that are easy to remember, like "elephant" or "giraffe". But the animals still have numbers too. The directory helps you find the number for any animal name you type in.

The DNS is like the zoo directory. When you type a website name like "google.com" in your browser, DNS looks up the number for that website name. The number is called an "IP address" and it helps your computer find the right website. 

DNS works by asking different servers. It first asks a "root server" which tells it to ask a ".com server". The ".com server" then tells it to ask the "google server". The "google server" knows Google's IP address and sends that back. Then your computer can use that IP address to load Google's website.

Your browser and your computer each have a little directory too, so next time you want to go to Google they can remember the IP address and load the website faster without asking all the servers again.

So in summary, DNS is like a directory that turns easy-to-remember website names into hard-to-remember numbers (IP addresses) that your computer actually uses to find and connect to websites on the Internet.

## Explain like I am Eleven

Imagine the Internet is a massive library with billions of books. Each book has a call number like 753.8 or 910.4 instead of a title. When you want to find a book, you need to remember its call number and go search on that shelf.

That would be difficult so the library has something called a card catalog. The card catalog lets you search by book title. Under each title in the card catalog is the call number of that book.

The DNS is like the Internet's card catalog. When you type a website address like "google.com" in your browser, DNS looks up the "call number" for that website, which is called an IP address. The IP address tells your computer exactly where to find that website on the Internet.

DNS works by asking a series of computers called nameservers. It first asks a "root nameserver" which directs it to the ".com nameserver". The ".com nameserver" then tells it the nameserver for "google.com". Finally, the "google.com" nameserver provides Google's IP address.

Your browser and computer each keep a small catalog of recently looked up addresses, so the next time you visit Google they can go straight to its IP address without asking all the nameservers again.

In summary, DNS acts like the card catalog for the Internet. It converts website names that people can remember, like "google.com", into the IP addresses that computers need in order to actually locate and connect to websites. The DNS system of nameservers work together to translate names into IP addresses.

## Explain like I am a College student

The Domain Name System (DNS) is an internet service that translates human-readable domain names into the IP addresses needed for locating and routing devices on the internet.

When you type a website address like "google.com" into your browser, your computer needs to figure out the numeric IP address of that website's server in order to actually connect to it. But no one can remember those long strings of numbers! That's where DNS comes in.

DNS works by using a hierarchical system of DNS servers. At the top is the root server, which contains information about the top-level domains like .com, .net, etc. When your computer makes a DNS request for google.com, it first goes to a root server to get directed to the .com DNS server.

The .com DNS server then contains information about which DNS server is authoritative for google.com. Your request then goes to the google.com DNS server, which contains the actual IP address for google.com's web servers. That IP address is then returned to your computer so it can connect to Google's website.

This all happens in milliseconds, behind the scenes when you type a domain name into your browser.

DNS servers cache responses for performance, so subsequent requests for the same domain name can be answered quickly from cache instead of traversing the entire DNS hierarchy again.

DNS uses a client-server model, with DNS resolvers acting as clients that query authoritative DNS servers to map domain names to IP addresses.

Recursion and recursion queries allow higher-level DNS servers to recursively resolve names on behalf of clients, traversing down the DNS hierarchy until they reach an authoritative DNS server for that domain.


# Types of servers invloved in DNS resolution process

## Explain like I am Five

When you type a website name into your computer, your computer asks a special server called the "First Helper".   

The First Helper doesn't actually know the number for the website, so it has to ask another server called the "Big Boss".  

The Big Boss tells the First Helper if the website ends in .com, .net, or something else.  The Big Boss tells the First Helper to ask the .com server for .com websites.

The First Helper then asks the .com server. The .com server doesn't know the Google website number, so it tells the First Helper to ask the "Google Boss" server.

The Google Boss server actually knows Google's website number. It gives the number to the First Helper server, and the First Helper server gives the number to your computer so it can go to the Google website.

In summary:

1) Your computer asks the First Helper server   
2) First Helper asks the Big Boss root server
3) Big Boss tells First Helper to ask the .com server   
4) .com server tells First Helper to ask the Google Boss server
5) Google Boss server gives the website number to First Helper     
6) First Helper gives the number to your computer

Now your computer can use that website number to load the Google website!

## Explain like I am Eleven

When you type a website address like google.com into your computer, your computer first asks a DNS server to look up the IP address for that website. That first DNS server is called the recursive resolver.   

But the recursive resolver itself doesn't actually know the IP address for google.com right away. So it has to ask another DNS server called the root server.

The root server knows that google.com is part of the .com domain, so it tells the recursive resolver to ask the .com DNS server for the IP address.

The recursive resolver then asks the .com DNS server. But again, the .com server only knows about all the .com domains in general, not the specific IP address for google.com. So it tells the recursive resolver to ask the authoritative nameserver for google.com.

The authoritative nameserver for google.com actually has the IP address stored that points directly to Google's website servers. So it provides that IP address to the recursive resolver.

Finally, the recursive resolver returns that IP address to your computer. Now your computer has the information it needs to connect directly to Google's website servers and load google.com in your browser.

In short, 4 types of DNS servers work together to translate a website name into an IP address:

1) The recursive resolver you first ask   
2) The root server     
3) The .com server
4) The authoritative nameserver for that specific domain

## Explain like I a College student


1. DNS recursor - This is the first server that a DNS query is sent to. It could be your ISP's DNS server or a public DNS server like Google or Cloudflare DNS. The recursor's job is to make additional queries to resolve the original request from the client.

2. Root nameserver - When the recursor cannot resolve the requested domain name itself, it queries one of the root nameservers. The root nameserver points the recursor to the top level domain (TLD) nameserver for the domain. 

3. TLD nameserver - For example, the .com TLD nameserver for domains that end in .com. The TLD nameserver points the recursor to the authoritative nameserver for the specific domain name.

4. Authoritative nameserver - This is the DNS server that actually has the DNS records and IP address for the requested domain name. It provides the IP address to the recursor so it can return it to the client and complete the DNS lookup.

So in summary:

1. Client requests domain name from recursor 
2. Recursor queries root nameserver
3. Root nameserver directs to TLD nameserver (.com, .net, etc)
4. TLD nameserver directs to authoritative nameserver for that domain
5. Authoritative nameserver returns IP address to recursor 
6. Recursor returns IP address to client, completing the DNS lookup

# Types of DNS queries

## Explain like I am five

When you ask your mom or dad for the number of a website, there are 3 ways they can help you:

1. They can find the whole answer. This is a recursive query. 

This means they will ask as many people as they need to, until they find the actual number for the website. Then they give you the full answer.

2. They can tell you the name of the next person to ask. This is an iterative query.

This means they don't know the full answer, but they know who you should ask next. So they tell you another person's name who might know, and then you have to go ask that person yourself. You keep asking people iteratively until someone gives you the full number.

3. They already know the answer! This is a non-recursive query.

This means they recently helped someone else find the same website number, so they just remembered the answer and can give it to you right away. No need to ask anyone else.

In summary:

Recursive queries mean someone finds the full answer for you.
Iterative queries mean someone tells you who to ask next.
Non-recursive queries mean someone remembers the recent answer.

## Explain like I am Eleven

When you type a website name into your browser, like google.com, your computer first needs to find the actual IP address for that website. That's where DNS comes in. DNS stands for Domain Name System, and it's basically a phonebook that translates names into numbers.

There are three main types of DNS queries:

1. Recursive queries - These are when your computer asks a DNS server to look up the IP address for you and give you the full answer. The DNS server will then have to query multiple other DNS servers until it finds the right answer and returns the IP address to your computer.

2. Iterative queries - These are when your computer asks a DNS server and that server doesn't have the full answer. Instead, it gives your computer the information for another DNS server that might have the answer. Then your computer has to go query that next DNS server, and so on, until finally a DNS server gives your computer the full IP address. 

3. Non-recursive queries - These happen when the DNS server your computer queries already knows the answer because it recently looked up that same website name. So it can give your computer the IP address right away, without having to query any other DNS servers.

So in summary:

- Recursive queries mean the DNS server finds the full IP address for you.
- Iterative queries mean the DNS server points you to the next DNS server to ask. 
- Non-recursive queries mean the DNS server already knows the IP address from its cache.

The types of DNS queries help determine the most efficient way for your computer to get the information it needs to load a website.


## Explain like I am a College Student

1. Recursive queries:

In a recursive query, the client (e.g. your computer) asks the DNS server to resolve the full domain name. The DNS server will then make additional queries to other DNS servers as needed, until it gets an authoritative response with the IP address. It will then return that full resolved response to the original client.

Recursive queries are used when the client does not have the processing power or knowledge of DNS servers to resolve the domain name itself.

2. Iterative queries:

In an iterative query, the client only asks the DNS server it knows of. That DNS server will then give a "referral" response, pointing the client to the next DNS server it should query. The client then makes iterative queries, moving down the DNS server hierarchy until it gets an authoritative response. 

Iterative queries are used when the client has the ability to make multiple queries, but not do full recursion itself.

3. Non-recursive queries:

A non-recursive query is when the DNS server that is queried already has the requested DNS record in its cache. It can then immediately respond to the query without needing to make any additional queries.

Cached responses are the most efficient type of DNS query, since no additional network traffic is needed beyond the original query.

So in summary:

- Recursive queries are when a DNS server fully resolves the domain name on behalf of the client
- Iterative queries involve the client iteratively querying DNS servers based on referrals  
- Non-recursive queries are served from cache and require no additional lookups.

The type of query sent depends on the capabilities of the client and the information available in DNS servers' caches.

# What is DNS caching? Where does DNS caching occur?

## Explain like I am Five

You know how sometimes Mom or Dad can tell you the answer to a question right away, but other times they have to stop and think or go look something up first?  

Well, for the answers they know right away, that means they already had the answer stored in their brain. They "cached" that information in their memory from last time you asked or they learned it.

When computers need to find website addresses, they have to go ask special servers on the Internet. But those servers can "cache" the answers too, so next time the same question is asked they have the answer ready instantly.

Your computer, your internet box, and the special DNS servers on the internet all cache DNS information:

• Your computer caches website addresses so if you go to the same website again soon, it knows the answer right away.

• Your internet box caches answers for all the devices using it. That means answers are super fast for anyone using that internet box.

• The special DNS servers cache answers too. The more servers that have cached an answer, the faster it will be for anyone asking that question.

Just like how Mom and Dad can forget answers after a while, cached DNS information expires after a set period of time. That's so the website addresses stay up to date. Then the next time that website is looked up, a full DNS lookup has to happen again.

So in short, DNS caching is just like how you cache answers in your brain. Storing information means you can remember and access it faster next time!

## Explain like I am Eleven

Remember when we learned about search engines and how they crawl and index websites to store information so searching is fast? DNS caching works a bit like that.

When you type a website address into your browser, your computer has to figure out the actual IP address of the website to connect to it. It does this by asking a DNS server. 

But DNS servers can "cache" the answers to DNS lookups. This means that when the same question is asked again soon, the DNS server already knows the answer and can give a fast response without having to look it up again.

Caching occurs at several levels:

• Your computer caches DNS answers so if you visit the same website again in the next hour or day, it can give you the IP address right away from its cache. This means the website loads faster.

• Your router caches DNS answers for all the devices connected to it. So if anyone using that router visits a website, the router can often provide the IP address from its cache.

• DNS servers on the Internet cache answers too. The more DNS servers that cache an answer, the faster it will be for anyone looking up that website address.

But just like information in a search index gets outdated, cached DNS information eventually expires. This keeps the website addresses up to date. Then the next time that website is looked up, a full DNS lookup has to happen again to get the most recent  IP address.

In summary, DNS caching is a lot like how search engines store information - it speeds up future lookups of information you've already found once. The more places that cache the information, the faster future lookups will be.

So the next time a website loads really fast for you, remember that DNS caching is probably helping out behind the scenes!

## Explain like I am College Student

DNS caching is a technique used to improve DNS performance and efficiency by storing the results of recent DNS lookups in memory caches. When the same DNS query is received again, the result can be retrieved directly from the cache instead of querying the authoritative nameservers, thus reducing latency and bandwidth consumption. 

Caching occurs at multiple levels in the DNS hierarchy:

• Resolver caching -  DNS resolvers, which receive recursive queries from clients and query upstream nameservers, will typically cache responses to reduce the load on authoritative nameservers. The TTL value returned with the record determines how long the cache entry is valid.

• Operating system caching - Many operating systems incorporate DNS caches to store results for processes running on that system. This reduces the number of queries to the resolver.

• Browser caching - Web browsers also maintain their own DNS caches to speed up lookups for domains they have recently accessed.

• Authoritative nameserver caching - Even authoritative nameservers may cache negative responses (no such domain exists) to optimize future lookups.

The benefits of DNS caching include:

• Faster response times - Answers can be retrieved directly from cache, skipping upstream queries.

• Reduced load - Fewer queries are made to authoritative nameservers and resolvers.

• Scalability - Caching distributes load across multiple caching layers, enabling the DNS system to scale for a larger number of requests.

However, cached records eventually time out based on their TTL. This ensures that DNS information remains up-to-date. Records may also be explicitly flushed from caches.

In summary, DNS caching at multiple layers improves the efficiency, performance and scalability of the DNS system by speeding up repeat lookups and reducing load on upstream nameservers. The trade-off is that records may become stale, so TTL management and cache invalidation policies are important to consider.


# DNS Glossary

Term | Definition
-|-
Domain Name System (DNS)| The system that translates human readable domain names (like google.com) to IP addresses required by computers to locate resources on the internet.
DNS Query| A request from a DNS client (like a web browser) to a DNS server to lookup a domain name. 
Recursive DNS Query | A query where the client requests the DNS server to lookup and return the final IP address, potentially querying multiple upstream servers.
Iterative DNS Query | A query where the client accepts referrals from the DNS server pointing to the next server in the lookup chain, and queries that server itself.  
Authoritative DNS Server | A DNS server that contains the actual DNS records for a domain and can respond directly without forwarding the query.
Recursive DNS Resolver | A DNS server that can resolve queries recursively by querying upstream nameservers until it finds the definitive answer or reaches the authoritative nameserver.
DNS Record | Information stored in a DNS server, including: <br> - A records (maps domain to IP address)<br> - NS records (maps domain to nameservers)<br> - MX records (maps domain to mail servers) <br> - CNAME records (maps domain to an alias) <br> - PTR records (maps IP address to domain name)
DNS Caching | Storing DNS records in caches to speed up future lookups of the same data. Caching occurs at browser, OS, resolver and nameserver levels.
DNS TTL | Time To Live - An expiration time assigned to DNS records, determining how long they can be cached before refetching.  
DNS Resolution | The process of translating a domain name into its corresponding IP address. involves querying nameservers in the DNS hierarchy. 
Root DNS Servers | The authoritative DNS servers for the root zone (.) and act as a reference for the top-level domain (TLD) nameservers.

