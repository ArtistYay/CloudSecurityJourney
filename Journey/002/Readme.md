![placeholder image](Journey/002/assets/ip_addressing.jpg)

# Table of contents

- [IP Addressing](#ip-addressing)
  - [IPV4](#ipv4)
  - [IPV6](#ipv6)
  - [Classful IP Addressing](#classful-ip-addressing)
  - [Classless Addressing](#classless-addressing)
  - [Classless Inter Domain Routing (CIDR)](#classless-inter-domain-routing-cidr)
  - [Subnetting](#subnetting)
  
# IP Addressing

Internet Protocol (IP) addressing is a system of assigning unique identifiers to devices on a network so that they can communicate with each other.

## IPV4

IPv4 is the fourth version of the Internet Protocol, and it has been the dominant IP version for most of the Internet's history. IP stands for Internet Protocol. IPv4 addresses are 32-bit integers.

*8.8.8.8*

> An IPv4 address consists of four numbers, each of which contains one to three digits, with a single dot (.) separating each number or set of digits. Each of the four numbers can range from 0 to 255.

## IPV6 

IPv6 or Internet Protocol Version 6 is a network layer protocol that allows communication to take place over the network. IPv6 was designed by Internet Engineering Task Force (IETF) in December 1998 with the purpose of superseding the IPv4 due to the global exponentially growing internet users.

*3001:0da8:75a3:0000:0000:8a2e:0370:7334*

> An IPv6 address consists of eight groups of four hexadecimal digits.

## Classful IP Addressing

In Classful addressing IP addresses are allocated according to the classes A to E.

### Class A

Class A IP addresses are designed for large-scale networks with a vast number of connected devices, typically found in large organizations or institutions like universities or corporations. They offer a large host ID space, allowing for over 16 million unique hosts on a single network. The network ID occupies the first eight bits of the Class A IP address, while the remaining 24 bits represent the host ID. The default subnet mask for Class A networks is *255.x.x.x*, enabling the creation of numerous subnets within the network.

IP addresses belonging to class A ranges from `1.0.0.0 – 126.255.255.255`.

The first octet of a Class A IP address can be any value from 1 to 126. The remaining three octets can be any value from 0 to 255.

### Class B

Class B IP addresses cater to medium-sized to large-sized networks, commonly used by organizations or institutions with a moderate to extensive need for internet connectivity. They offer a balance between network and host ID space, accommodating up to 65,536 hosts per network. The network ID, occupying the first 16 bits of the Class B IP address, defines the network, while the remaining 16 bits represent the host ID. The default subnet mask for Class B networks is *255.255.x.x*, allowing for the creation of numerous subnets within the network. Class B IP addresses fall within the range of `128.0.0.0 to 191.255.255.255`.

### Class C

Class C IP addresses are specifically designed for small-sized networks, commonly found in residential or small business settings. They offer a limited host ID space, accommodating up to 254 hosts per network. The network ID, occupying the first 24 bits of the Class C IP address, identifies the network, while the remaining 8 bits represent the host ID. The default subnet mask for Class C networks is *255.255.255.x*, allowing for the creation of subnets within the network. Class C IP addresses fall within the range of `192.0.0.0 to 223.255.255.255`.

### Class D

Reserved for multi-casting. IP addresses belonging to class D range from `224.0.0.0 – 239.255.255.255`.

### Class E

IP addresses belonging to class E are reserved for experimental and research purposes. IP addresses of class E range from `240.0.0.0 – 255.255.255.254`.

## Classless Addressing

Classless addressing came to replace the classful addressing and to handle the issue of rapid exhaustion of IP addresses. This can be achieved using CIDR.

### Class A

Class A IP addresses are characterized by having a '0' as the first bit of their first octet. This translates to an IP address range spanning from `0.0.0.0 - 127.255.255.255` (in decimal representation, 01111111 in binary equals 127). The first eight bits, or the first octet, represent the network portion of the IP address, while the remaining 24 bits, or the three octets, designate the host portion. Class A addresses utilize a subnet mask of `255.0.0.0.`Can support 128 Network, 16,777,216 addresses per network and a total of 2,147,483,648 addresses. 

### Class B

Class B IP addresses are distinguished by having a '10' as the first two bits of their first octet. This results in an IP address range encompassing `128.0.0.0 - 191.255.255.255`. The first 16 bits, or the first two octets, constitute the network portion of the IP address, while the remaining 16 bits, or the two octets, represent the host portion. Class B addresses employ a subnet mask of `255.255.0.0`. can support  16,384 Network, 65,536 addresses per network and a total of 1,073,741,824 addresses. 

### Class C

Class C IP addresses are identified by having a '110' as the first three bits of their first octet. This translates to an IP address range stretching from `192.0.0.0 - 223.255.255.255`. The first 24 bits, or the first three octets, signify the network portion of the IP address, while the remaining eight bits, or the remaining one octet, represent the host portion. Class C addresses utilize a subnet mask of `255.255.255.0`. Can support 2,097,152 Network, 256 addresses per network and a total of 536,870,912 addresses.

### Class D

Class D is used for multicast addressing and in a class D address the first octet would always start with ‘1110’. Thus, class D addresses range from `224.0.0.0 - 239.255.255.255`. Its Subnet mask is not defined.

### Class E

Class E addresses are reserved for research purposes and future use. The first octet in a class E address starts with ‘1111’. Thus, class E addresses range from `240.0.0.0 - 255.255.255.255`. Its Subnet mask is not defined.

## Classless Inter Domain Routing (CIDR)

Classless Inter-Domain Routing (CIDR) is a method of allocating IP addresses and for IP routing that allows for more efficient use of IP addresses. CIDR addresses are represented using a slash notation, which specifies the number of bits in the network prefix. For example, an IP address of 192.168.1.0 with a prefix length of 24 would be represented as 192.168.1.0/24. This notation indicates that the first 24 bits of the IP address are the network prefix and the remaining 8 bits are the host identifier.

### Why is CIDR important?

*Efficiency*: CIDR allows for more efficient use of IP addresses by dividing them into smaller subnets. This is important because IP addresses are a limited resource, and CIDR helps to ensure that they are used as effectively as possible.

*Flexibility*: CIDR is more flexible than classful addressing because it allows for the creation of subnets of any size. This makes it easier to manage networks of all sizes, from small home networks to large corporate networks.

*Scalability*: CIDR is more scalable than classful addressing because it can accommodate the growth of the internet. As the number of devices on the internet continues to grow, CIDR will be able to keep up with the demand for IP addresses.

*Routing Efficiency*: CIDR improves routing efficiency by reducing the size of routing tables. Routers use routing tables to determine where to send data packets. With CIDR, routing tables are smaller and more efficient, which reduces the amount of processing time required for routing.

*Security*: CIDR can be used to improve network security by creating subnets. Subnets can be isolated from each other, which can help to prevent unauthorized access to networks.

## Subnetting

Subnetting is the process of dividing a network into smaller, more manageable subnetworks. This is done by borrowing bits from the host portion of an IP address and using them to create additional network addresses. Subnetting can be used to improve network performance, security, and manageability. CIDR and subnetting are often used together because they are both ways to improve the efficiency of IP address usage. CIDR provides a more flexible way to allocate IP addresses, while subnetting allows for the creation of smaller, more manageable networks.

[<img src="https://img.youtube.com/vi/ecCuyq-Wprc>/hqdefault.jpg" width="600" height="300"
/>](https://www.youtube.com/embed/ecCuyq-Wprc)

