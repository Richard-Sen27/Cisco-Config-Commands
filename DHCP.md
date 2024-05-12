# DHCP Config Commands

## Show Commands

## Configuration

Activate/Deactivate the DHCP service on a router
```ruby
Router(config)# service dhcp
Router(config)# no service dpch
```

Exclude IP addresses from the pool
```ruby
Router(config)# ip dhcp excluded-address [[low address] [highest address] | address]
```

Create a pool
```ruby
Router(config)# ip dhcp pool [name]
```

<!-- Configure the DHCP service on a interface
```ruby

``` -->

Complete Example
```ruby
R1(config)# ip dhcp excluded-address 192.168.10.1 192.168.10.9
R1(config)# ip dhcp excluded-address 192.168.10.254
R1(config)# ip dhcp pool LAN-POOL-1
R1(dhcp-config)# network 192.168.10.0 255.255.255.0
R1(dhcp-config)# default-router 192.168.10.1
R1(dhcp-config)# dns-server 192.168.11.5
R1(dhcp-config)# domain-name example.com
R1(dhcp-config)# end
R1#
```

IP helper address is used if the DHCP server is in another network
```ruby
Router(config-if)# ip helper-address [address]
```