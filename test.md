IPv4 contains 32 bits per address.
it splits decimal : 
Ex ) 221.67.143.47 ====> 11011101 // 01000011 // 10001111 // 00101111  
IPs uses for communication between two or more nodes in a local network (LAN/MAN/CAN) or world wide network (WAN)
IP = NetID + HostID ( both are explained in line [LINES]
Subnet mask = contains 32 bits per each  |  it splits networks whenever is needed | in SP envoirments is also used for IP renting to clinets/partners 
Ex ) 221.67.143.47/24  ===> after forward-slash, two or may one number is occupied, it's called subnet mask (Prefix also, mostly for IPv6) ==> 221.67.143.47 / 255.255.255.0
In subnets {8,16,24,32} whenever decimal subnet mask shows "255" it's NetID, and whenever shows "0", it's HostID (255 remains as a reminder BTW.)

NetworkID(NetID) === > each subnet splits some ip addresses into some groups, very first ip of each group will be called NetID and is reserved, IT'S NOT SETABLE, and will be used for broadcasting 

IP Classes :

-----------------
| [Class : Range/SM]       |   [Default SM]   |      [How range prove]   |   [IP Pool amount] |
| -------------------------|------------------|--------------------------| ------------------ |
| A : (1 - 126).0.0.0/8    |    255.0.0.0     | [0][X][X][X][X][X][X][X] | -- 16,777,214 IPs  |
| B : (128-191).0.0.0/16   |   255.255.0.0    | [1][0][X][X][X][X][X][X] | -- 65534 IPs       |
| C : (192-223).0.0.0/24   |   255.255.255.0  | [1][1][1][X][X][X][X][X] | -- 254 IPs         |
| D : (224-239).0.0.0      |    MultiCast     |                          |                    |
| E : (240-255).0.0.0      |    MultiCast     |                          |                    |


Multicast IPs cannot be set on Normal NICs.
Multicast IPs commonly used for service/platforms that require higher speed, bandwith, and performance

----------------- Creating isolated networks with subneting -----------
take 192.168.10.0/24 as an example -- 10 isolated networks are asked
Tutorial : 
1. write down decimal form of SM ==> 255.255.255.0
2. convert it to binary ==> (11111111.11111111.11111111.00000000)
3.convert number of asked network to binary ==> (1010)
4.count number of digits on step3 ==> (4)
5.as much as amount of digits on step4, add to left side of HostID in step2 ==> (11111111.11111111.11111111.11110000)
6.add amount of digits on step4 to your subnet mask ==> 24+4=28
===> Final Ansewr : 192.168.10.0/28 --- now it has 10 seperate networks.

(N)Network              (H)Hosts                   (B)Broadcast
192.168.10.0            192.168.10.(1-14)          192.168.10.15
192.168.10.16           192.168.10.(17-30)         192.168.10.31
192.168.10.32           192.168.10.(33-46)         192.168.10.47
192.168.10.48           192.168.10.(49-62)         192.168.10.63
192.168.10.64           192.168.10.(65-78)         192.168.10.79
...                     ...                        ...

-----------------------------------------------------------------------
