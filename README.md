# You SUCK at Subnetting! - Network Chuck - Notes [Here](https://www.youtube.com/playlist?list=PLIhvC56v63IKrRHh3gvZZBAGvsvOhwrRF)

## IP address

|   | Range                                              | Subnet Mask   |
|---|----------------------------------------------------|---------------|
| A | &nbsp;&nbsp;&nbsp;&nbsp; 1.0.0.0 - 126.255.255.255 | 255.0.0.0     |
| B | 128.0.0.0 - 191.255.0.0                            | 255.255.0.0   |
| C | 192.0.0.0 - 223.255.255.0                          | 255.255.255.0 |
| D | 244.0.0.0 - 239.255.255.255                        |               |
| E | 240.0.0.0 - 255.255.255.255                        |               |

Class D networks are reseved for multi-cast<br>
Class E netwroks are Experimental

any ip address begining with 127.0.0.0 are know as loop-back address that are used for network testing

### RFC 1918

Private IP Addresss<br>
The Internet Band-Aid

|   | Private IPS                                               | Subnet Masks  |
|---|-----------------------------------------------------------|---------------|
| A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 10.0.0.0 - 10.255.255.255  | 255.0.0.0     |
| B | &nbsp; 172.16.0.0 - 172.31.255.255                        | 255.255.0.0   |
| C | 192.168.0.0 - 192.168.255.255                             | 255.255.255.0 |

this table is referring to the default private IP address ranges as defined by RFC 1918. These are typically used in local networks, such as homes, offices, schools, etc.

Here is a summary of the ranges provided:

- Class A: 10.0.0.0 to 10.255.255.255 - Provides up to 16,777,216 private IPv4 addresses (10.0.0.0/8).
- Class B: 172.16.0.0 to 172.31.255.255 - Provides up to 1,048,576 private IPv4 addresses (172.16.0.0/12).
- Class C: 192.168.0.0 to 192.168.255.255 - Provides up to 65,536 private IPv4 addresses (192.168.0.0/16).

These IP ranges are typically used in combination with NAT (Network Address Translation) to allow multiple devices on a local network to communicate with the Internet using a single public IP address.

### NAT (Network Address Translation)

NAT (Network Address Translation) is a method used in networking to conserve public IP addresses and enhance security. It allows multiple devices on a local network to access the internet using a single public IP address.

Here's how it works:

1. A device from the local network sends a request to a server on the internet. The packet contains the device's private IP address and a unique port number.
2. The router receives this request. It replaces the device's private IP address in the packet header with its own public IP address, making a note of the original IP and port number.
3. The router sends the modified packet to the server on the internet.
4. The server responds to the request by sending a packet back to the router's public IP address.
5. The router receives the response from the server and uses its records to replace the public IP address in the packet header with the original private IP address and port number.
6. The router sends the packet to the original device.

By using NAT, local networks can ensure their devices can communicate with the internet without exposing their private IP addresses, thereby enhancing security. Furthermore, NAT helps conserve the limited number of public IPv4 addresses available, by allowing multiple devices to share a single public IP.

### IPv4 vs IPv6

Sure, here's a brief comparison between IPv4 and IPv6:

**IPv4:**

- IPv4 stands for Internet Protocol version 4. It is the fourth revision of the Internet Protocol and a widely used protocol in data communication over different kinds of networks.
- IPv4 uses a 32-bit address scheme allowing for a total of 2^32 addresses (just over 4 billion addresses). Due to the growth of the internet, IPv4 addresses are running out.
- IPv4's header includes a Checksum field, which needs to be recalculated by routers every time the Time to Live (TTL) field decreases. This slows down routing.
- IPv4 uses dot-decimal notation, which is more human-friendly. An example of an IPv4 address is 192.0.2.0.

**IPv6:**

- IPv6, or Internet Protocol version 6, is the most recent version of the Internet Protocol. It was developed to succeed IPv4.
- IPv6 uses a 128-bit address scheme allowing for 2^128 addresses. This is a huge address space which is unlikely to run out in any foreseeable future.
  - 340,282,366,920,938,463,463,374,607,431,768,211,456
- IPv6 doesn't include a checksum in its header. This allows routers to process packets more quickly.
- IPv6 uses hexadecimal notation, which is less human-friendly. An example of an IPv6 address is 2001:0db8:85a3:0000:0000:8a2e:0370:7334.

In addition to the increased address space, IPv6 also introduces features not present in IPv4, such as mandatory support for IPsec (a security protocol for authenticating and encrypting each IP packet of a communication session), more efficient routing, simplified network configuration through address auto-configuration, and better multicast support. IPv6 is not backward-compatible with IPv4, necessitating translation gateways or dual-stack configuration for interoperability.

## Decimal & Binary

my ip address: 192.168.1.74
this is in decimal

8 bits make 1 byte
an ip address is 32 bits or 4 bytes

It is divided into four sections, known as "octets". The name "octet" comes from the fact that each section is made up of 8 bits. With 8 bits, you can have 256 different values (ranging from 0 to 255), hence why each octet in an IP address can range from 0 to 255.

binary only cares about 1's and 0's where 1 means on and 0 means off. This is how computers communicat 

**Binary to Decimal Chart**

| Binary   | Decimal |
|----------|---------|
| 00000001 | 1       |
| 00000010 | 2       |
| 00000100 | 4       |
| 00001000 | 8       |
| 00010000 | 16      |
| 00100000 | 32      |
| 01000000 | 64      |
| 10000000 | 128     |

my ip address in binary: 11000000.10101000.00000001.01001010

my ip address in binary to decimal 1st octet: 11000000 = &nbsp;&nbsp; 128 + 64 &nbsp;&nbsp; = 192<br>
my ip address in binary to decimal 2nd octet: 10101000 = 128 + 32 + 8 = 168<br>
my ip address in binary to decimal 3rd octet: 00000001 = &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = 1<br>
my ip address in binary to decimal 4th octet: 01001010 = &nbsp; 64 + 8 + 2 &nbsp; = 74

## Subnet Mask

my toliet's ip address: 192.168.32.5<br>
my toliet's subnet mask: 255.255.255.0

my toliet's ip address (binary): 11000000.10101000.00100000.00000101<br>
my toliet's subnet mask (binary): 11111111.11111111.11111111.00000000

when looking at the subnet mask the 1's tell us what bits are the network bits and the 0's tell us what bits are the host bits<br>
1 = network bits<br>
0 = host bits

to see how many host's can be in our network we just need to take $2^{(num\ of\ 0's)}$<br>
$2^8 = 256$<br>
but you have to minus 2 from that so 254<br>
$2^{(num\ of\ 0's)}-2$ is the new formula

### Subnet 3 Coffee Shops

ip address to start: 10.1.1.0/24

each coffee shops needs about 40 hosts

so $40 * 3 = 120$, or 120 hosts

this is the basic subnet mask: 255.255.255.0 this is what we are going to mess with but before we can we need to convert this into binary which comes out to be 11111111.11111111.11111111.00000000

<table>
  <thead>
    <tr>
      <th colspan="8"><strong>Subnetting Host Bit Requirements</strong></th>
    </tr>
  </thead>
    <tbody>
      <tr>
        <td>128</td>
        <td>64</td>
        <td>32</td>
        <td>16</td>
        <td>8</td>
        <td>4</td>
        <td>2</td>
        <td>1</td>
    </tr>
    <tr>
      <td>256</td>
      <td>128</td>
      <td>64</td>
      <td>32</td>
      <td>16</td>
      <td>8</td>
      <td>4</td>
      <td>2</td>
    </tr>
  </tbody>
</table>

using this chart we now now that we need to hack 6 host bits but since we are not going from right to left but from left to right we need to save the bits.

this means that 6 hosts bits will remain 0 while 2 hosts bits become a 1. if we follow the rules for subnetting that would make are new subnet mask 11111111.11111111.11111111.11000000

now with this we have our increment which will be 64 becuase its our last bit that is 1

now that we have our increment we can create our networks

we start with 10.1.1.0 - 10.1.1.63 because its including 0

then 10.1.1.64 - 10.1.1.127

then 10.1.1.128 - 10.1.1.191

there we have all three networks that we need for our 3 coffee shops

but what is our subnet mask we know what it is in binary but know we need to know what it is in decimal so we need to convert it.

we know what the first 3 octet's are because those were not changed, they stayed 255. but know we needed the last octet which we get by doing $128 + 64 = 192$

so our new subnet mask would be 255.255.255.192 but for the $/n$ part of our ip all we need to do is count the bits we started with 24 and added 2 so we now have 26

so are 3 new networks would be

1. 10.1.1.0 /26
2. 10.1.1.64 /26
3. 10.1.1.128 /26

### Lab Practice

We are an ISP (Internet Service Provided) and we have 4 companies who need 20 ISPs each how would you break it up. The Ip address we will use is 142.2.0.0 /16

First we need to figure out how many hosts we need and to this we $20 * 4 = 80$

we need to have are subnet mask which is 255.255.0.0

convet to binary: 11111111.11111111.00000000.00000000

using the table above we now that we need to save 4 bits

so are new subnet masks would 11111111.11111111.11111111.11100000

with this we now are incremnt is 32

1. 142.2.0.0 - 142.2.0.31
2. 142.2.0.32 - 142.2.0.63
3. 142.2.0.64 - 142.2.0.95
4. 142.2.0.96 - 142.2.0.127
5. 142.2.0.128 - 142.2.0.159
6. 142.2.0.160 - 142.2.0.191
7. 142.2.0.192 - 142.2.0.223
8. 142.2.0.224 - 142.2.0.255

We only need to use the first four networks that we created

are new subnet mask in decimal would be 255.255.255.244 /27

each network would have 30 useable address well with the range for our network

### Reverse Subnetting?

- Router
  - IP Address: 172.17.0.1
- Beatrice
  - IP Address: 172.17.16.255
  - Subnet Mask: 255.255.240.0
- Bernard Hackwell
  - IP Address: 172.17.12.101
  - Subnet Mask: 255.255.240.0

Something is wrong Beatrice's IP address and to find out why we need to do Reverse Subnetting.

Luckly we are given the Subnet Mask so we dont need to find it

Not we need to convert the subnet mask to binary, and when we do that we get:

11111111.11111111.11110000.00000000

now that we have it in binary we can find the subnet masks insider notation which is /20 for this subnet

we got this by counting the amount of 1 bits in the subnet

we also use the last network bit to find the increment and in this case it's 16

now we can create our networks

- 172.17.0.0 - 172.17.15.255
- 172.17.16.0 - 172.17.31.255
- 172.17.32.0 - 172.17.47.255
- 172.17.48.0
- 172.17.64.0

We know know that Beatrices computer is in this network 172.17.16.0 - 172.17.31.255

#### Another Example

IP Address: 48.25.24.71 /21

- Network Address?
- Broadcasting Address?
- Router?

Subnet Mask (binary): 11111111.11111111.11111000.00000000 - this was found because of the insider notation of the ip address provided and we know the increment too which is 8<br>
Subnet Mask (decimal): 255.255.248.0

1. 48.25.0.0 - 48.25.7.255
2. 48.25.8.0 - 48.25.15.255
3. 48.25.16.0 - 48.25.24.255

- Network Address = 48.25.8.0
- Broadcasting Address = 48.25.15.255
- Router = 48.25.8.1


































