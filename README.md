# Everything-About-DNS

- [What is DNS](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#dns)
  - [Explain like I am five](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-five)
  - [Explain like I am Eleven](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-a-college-student)
  - [Explain like I am a college student](https://github.com/devanshbatham/Everything-About-DNS/blob/main/README.md#explain-like-i-am-a-college-student)
- [Types of servers invloved in DNS resolution process]
  - 

# What is DNS

## Explain like I am five

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

## Explain like I am a college student

The Domain Name System (DNS) is an internet service that translates human-readable domain names into the IP addresses needed for locating and routing devices on the internet.

When you type a website address like "google.com" into your browser, your computer needs to figure out the numeric IP address of that website's server in order to actually connect to it. But no one can remember those long strings of numbers! That's where DNS comes in.

DNS works by using a hierarchical system of DNS servers. At the top is the root server, which contains information about the top-level domains like .com, .net, etc. When your computer makes a DNS request for google.com, it first goes to a root server to get directed to the .com DNS server.

The .com DNS server then contains information about which DNS server is authoritative for google.com. Your request then goes to the google.com DNS server, which contains the actual IP address for google.com's web servers. That IP address is then returned to your computer so it can connect to Google's website.

This all happens in milliseconds, behind the scenes when you type a domain name into your browser.

DNS servers cache responses for performance, so subsequent requests for the same domain name can be answered quickly from cache instead of traversing the entire DNS hierarchy again.

DNS uses a client-server model, with DNS resolvers acting as clients that query authoritative DNS servers to map domain names to IP addresses.

Recursion and recursion queries allow higher-level DNS servers to recursively resolve names on behalf of clients, traversing down the DNS hierarchy until they reach an authoritative DNS server for that domain.


# Types of servers invloved in DNS resolution process

## Explain like I am five

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

## Explain like I a college student


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

