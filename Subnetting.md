# Subnetting


## A simple description

Imagine you have a large piece of land (let's call it an IP address range), and you want to divide it into smaller sections (subnets). Each section will have its own purpose and set of addresses.

For example, let's say you have the IP address range 192.168.1.0 to 192.168.1.255. This is like your big piece of land. Now, you want to divide it into smaller sections for different departments in your company. You might reserve one section for the sales team, another for the marketing team, and so on.

Subnetting allows you to do just that. You can take that big IP address range and split it into smaller ranges, each dedicated to a specific part of your network.

So, in simple terms, subnetting is like dividing up a big chunk of addresses into smaller, more manageable chunks to organize and manage your network effectively.

## A visual example

We'll take the IP address range 192.168.1.0 to 192.168.1.255 and subnet it into four smaller subnets.

We'll start with the range 192.168.1.0 to 192.168.1.255, and we'll divide it into four equal subnets.

Here's a table showing how the IP addresses might be subnetted:

| Subnet | Network Address | Prefix | First IP Address | Last IP Address | Broadcast Address |
|--------|-----------------|--------|------------------|------------------|---------------------|
| Subnet 1 | 192.168.1.0 | /26 | 192.168.1.1 | 192.168.1.62 | 192.168.1.63 |
| Subnet 2 | 192.168.1.64 | /26 | 192.168.1.65 | 192.168.1.126 | 192.168.1.127 |
| Subnet 3 | 192.168.1.128 | /26 | 192.168.1.129 | 192.168.1.190 | 192.168.1.191 |
| Subnet 4 | 192.168.1.192 | /26 | 192.168.1.193 | 192.168.1.254 | 192.168.1.255 |

In this example, we've subnetted the original IP address range into four smaller subnets. Each subnet has its own network address, first usable IP address, last usable IP address, and broadcast address. This helps in organizing and managing the IP addresses more efficiently within a network.

## Now on the bit level

| Subnet | Network Address | Prefix | Network Visualization                            |
|--------|-----------------|--------|-------------------------------------------------|
| Subnet 1 | 192.168.1.0 | /26 | `11000000.10101000.00000001.00[000000]` |
| Subnet 2 | 192.168.1.64 | /26 | `11000000.10101000.00000001.01[000000]` |
| Subnet 3 | 192.168.1.128 | /26 | `11000000.10101000.00000001.10[000000]` |
| Subnet 4 | 192.168.1.192 | /26 | `11000000.10101000.00000001.11[000000]` |

The bits in the square brackets are the available bits for devices and is called the host portions. the bits before are the net portion.

## Common subnets

| Subnet Mask     | CIDR Prefix | Number of Subnets | Number of Hosts per Subnet |
|-----------------|-------------|-------------------|----------------------------|
| 255.255.255.0   | /24         | 1                 | 254                        |
| 255.255.255.128 | /25         | 2                 | 126                        |
| 255.255.255.192 | /26         | 4                 | 62                         |
| 255.255.255.224 | /27         | 8                 | 30                         |
| 255.255.255.240 | /28         | 16                | 14                         |
| 255.255.255.248 | /29         | 32                | 6                          |
| 255.255.255.252 | /30         | 64                | 2                          |
