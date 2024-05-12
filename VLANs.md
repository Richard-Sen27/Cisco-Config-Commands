# Basic Navigation

## Access privileged Exec mode
```ruby
Device> enable
```

## Access Global Configuration terminal
```ruby
Device# configure terminal
```

## Exit to lower instance
```ruby
Device(config-if)# end
Device(config-vlan)# end
Device(config)# exit
Devcie# exit
```

## Delete Something
```ruby
Device(config-ig)# no ip address <ip-address> <subnet mask>
```

# Show commands

```ruby
Device# show interface <interface-id> switchport
```
```ruby
Device# show vlan {brief | id <vlan-id> | name <vlan-name> | summary}
```
```ruby
Device# show dtp interface <id>
```
```ruby
Device# show spanning-tree summary
```
## Etherchannel
```ruby
Device# show interfaces port-channel
```
```ruby
Device# show etherchannel summary
```
```ruby
Device# show etherchannel port-channel
```
```ruby
Device# show interfaces etherchannel
```

# Security

## Set a console password
```ruby
Device(config)# line console 0
Device(config)# password <password>
Device(config)# login
```

## Encrypt plaintext passwords
```ruby
Device(config)# service password-encryption
```

## Encrypt privileged Exec mode
```ruby
Device(config)# enable secret <password>
```

## Create Access Control lists
```ruby
Device(config)# access-list <ACL number> {permit|deny} <source> <destination> <protocol>
```

# Routing

## Set interface IP address
```ruby
Router(config)# interface <interface-id>
Router(config-if)# ip address <ip-address> <subnet mask>
Router(config-if)# ipv6 address <ipv6-address> <reserved bits/mask>
```

## Configure a static route
```ruby
Device(config)# ip route <destination network> <subnet mask> <next-hop IP address or exit interface>
```

## Enable dynamic routing protocols (e.g., OSPF, EIGRP, BGP)
```ruby
Device(config)# router ospf <process-id>
Device(config)# network <network address> <wildcard mask> area <area-id>
```

# VLAN Configuration

## Create a VLAN
```ruby
Switch(config)# vlan <vlan-id>
Switch(config-vlan)# name <vlan-name>
```

## Assign a VLAN to a Switch port
```ruby
Switch(config)# interface <interface-id>
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan <vlan-id>
```

## Create a voice VLAN
```ruby
Switch(config)# vlan <id>
Switch(config-vlan)# name VOICE
Switch(config-vlan)# exit
Switch(config)# interface <id>
Switch(config-if)# mls qos trust cos
Switch(config-if)# switchport voice vlan <id>
Switch(config-if)# end
```

## Confiuger a trunk port
```ruby
Switch(config)# interface <id>
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk native vlan <vlan-id>
Switch(config-if)# switchport trunk allowed vlan <vlan-list>
Switch(config-if)# end
```

## Activate DTP on Trunk Port (Dynamic Trunking Protocol)
```ruby
Switch(config-if)# switchport mode dynamic auto
```

## Deactivate DTP on Trunk Port
```ruby
Switch(config-if)# swtichport nonegotiate
```

## Remove STP
```ruby
Device(config)#no spanning-tree vlan 1
```

# Remote Access Configuration

## Switch Virtual Interface
```ruby
Switch(config)# interface vlan <id>
Switch(config-if)# ip address <address> <subnet mask>
Switch(config-if)# no shutdown
```

## Default Gateway
```ruby
Switch(config)# ip default-gateway <ip-address>
```


# Ethernet Channell Configuration
## Example
```ruby
Device(config)# interface range FastEthernet 0/1 - 2
Device(config-if-range)# channel-group 1 mode active
Device(config-if-range)# exit
Device(config-if)# interface port-channel 1
Device(config-if)# switchport mode trunk
Device(config-if)# switchport trunk allowed vlan 1,2,20
```