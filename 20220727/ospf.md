# 1
## ①
### Router0での結果
Router#show ip ospf neighbor 


Neighbor ID     Pri   State           Dead Time   Address         Interface
192.168.1.2       1   FULL/BDR        00:00:36    192.168.1.2     FastEthernet0/0
192.168.1.3       1   FULL/DROTHER    00:00:39    192.168.1.3     FastEthernet0/0
192.168.1.4       1   FULL/DROTHER    00:00:37    192.168.1.4     FastEthernet0/0
192.168.1.5       1   FULL/DROTHER    00:00:34    192.168.1.5     FastEthernet0/0


### 検証
- DRルータ名: Router1
	- ルータID：192.168.1.1
- BDRルータ名：Router2
	- ルータID：192.168.1.2

## ②
### Router0での結果
Router#show ip ospf neighbor 


Neighbor ID     Pri   State           Dead Time   Address         Interface
192.168.1.4       1   FULL/BDR        00:00:38    192.168.1.4     FastEthernet0/0
192.168.1.5       1   FULL/DR         00:00:38    192.168.1.5     FastEthernet0/0
192.168.1.3       1   2WAY/DROTHER    00:00:38    192.168.1.3     FastEthernet0/0
192.168.1.2       1   2WAY/DROTHER    00:00:38    192.168.1.2     FastEthernet0/0

### 検証
- DRルータ名: Router4
	- ルータID：192.168.1.5
- BDRルータ名：Router3
	- ルータID：192.168.1.4

## ③
### Router1での結果
Router#show ip ospf neighbor 


Neighbor ID     Pri   State           Dead Time   Address         Interface
192.168.1.3       1   2WAY/DROTHER    00:00:30    192.168.1.3     FastEthernet0/0
192.168.1.4       1   2WAY/DROTHER    00:00:30    192.168.1.4     FastEthernet0/0
192.168.1.5       1   FULL/BDR        00:00:30    192.168.1.5     FastEthernet0/0
192.168.2.1       1   FULL/DR         00:00:30    192.168.1.1     FastEthernet0/0

### 検証
- DRルータ名: Router0
	- ルータID：192.168.2.1
- BDRルータ名：Router4
	- ルータID：192.168.1.5

## ④
### Router4での結果
Router#show ip ospf neighbor 


Neighbor ID     Pri   State           Dead Time   Address         Interface
192.168.2.1       1   2WAY/DROTHER    00:00:39    192.168.1.1     FastEthernet0/0
192.168.2.254     1   FULL/DR         00:00:39    192.168.1.3     FastEthernet0/0
192.168.2.253     1   FULL/BDR        00:00:39    192.168.1.4     FastEthernet0/0
192.168.1.2       1   2WAY/DROTHER    00:00:39    192.168.1.2     FastEthernet0/0

### 検証
- DRルータ名: Router2
	- ルータID：192.168.2.254
- BDRルータ名：Router3
	- ルータID：192.168.2.253

## ⑤
①ではRouter0からRouter4の順番に設定を行ったため、はじめに設定されたRouter0の192.168.1.1がDRルータとなったが、再起動した際には優先度がリセットされ、再度DR/BDRの選出を行うためIPアドレスの一番大きいRouter4が②ではDRルータに選出された。



# 2
## PC0
C:\>ping 192.168.3.4

Pinging 192.168.3.4 with 32 bytes of data:

Reply from 192.168.3.4: bytes=32 time<1ms TTL=125
Reply from 192.168.3.4: bytes=32 time<1ms TTL=125
Reply from 192.168.3.4: bytes=32 time<1ms TTL=125
Reply from 192.168.3.4: bytes=32 time<1ms TTL=125

Ping statistics for 192.168.3.4:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 0ms, Average = 0ms

## PC1
C:\>ping 192.168.0.2

Pinging 192.168.0.2 with 32 bytes of data:

Reply from 192.168.0.2: bytes=32 time<1ms TTL=125
Reply from 192.168.0.2: bytes=32 time<1ms TTL=125
Reply from 192.168.0.2: bytes=32 time<1ms TTL=125
Reply from 192.168.0.2: bytes=32 time<1ms TTL=125

Ping statistics for 192.168.0.2:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 0ms, Average = 0ms



