# 20221125演習

## 1-④
### Router_Aの結果

```
Router_A#show interfaces serial 0/0
Serial0/0 is up, line protocol is up (connected)
  Hardware is HD64570
  Internet address is 172.17.0.1/16
  MTU 1500 bytes, BW 1544 Kbit, DLY 20000 usec,
     reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation HDLC, loopback not set, keepalive set (10 sec)
  Last input never, output never, output hang never
  Last clearing of "show interface" counters never
  Input queue: 0/75/0 (size/max/drops); Total output drops: 0
  Queueing strategy: weighted fair
  Output queue: 0/1000/64/0 (size/max total/threshold/drops)
     Conversations  0/0/256 (active/max active/max total)
     Reserved Conversations 0/0 (allocated/max allocated)
     Available Bandwidth 1158 kilobits/sec
  5 minute input rate 45 bits/sec, 0 packets/sec
  5 minute output rate 41 bits/sec, 0 packets/sec
     24 packets input, 1932 bytes, 0 no buffer
     Received 15 broadcasts, 0 runts, 0 giants, 0 throttles
     0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored, 0 abort
     23 packets output, 1804 bytes, 0 underruns
     0 output errors, 0 collisions, 1 interface resets
     0 output buffer failures, 0 output buffers swapped out

Router_A#
```

### Router_Bの結果

```
Router_B#show interfaces serial 0/0
Serial0/0 is up, line protocol is up (connected)
  Hardware is HD64570
  Internet address is 172.17.0.2/16
  MTU 1500 bytes, BW 1544 Kbit, DLY 20000 usec,
     reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation HDLC, loopback not set, keepalive set (10 sec)
  Last input never, output never, output hang never
  Last clearing of "show interface" counters never
  Input queue: 0/75/0 (size/max/drops); Total output drops: 0
  Queueing strategy: fifo
  Output queue :0/40 (size/max)
  5 minute input rate 13 bits/sec, 0 packets/sec
  5 minute output rate 15 bits/sec, 0 packets/sec
     29 packets input, 2116 bytes, 0 no buffer
     Received 20 broadcasts, 0 runts, 0 giants, 0 throttles
     0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored, 0 abort
     32 packets output, 2348 bytes, 0 underruns
     0 output errors, 0 collisions, 2 interface resets
     0 output buffer failures, 0 output buffers swapped out
     0 carrier transitions
     DCD=up  DSR=up  DTR=up  RTS=up  CTS=up

Router_B#
```

## 1-⑤-(カ)
### Router_Aの結果

```
Router_A#show interfaces serial 0/0
Serial0/0 is up, line protocol is up (connected)
  Hardware is HD64570
  Internet address is 172.17.0.1/16
  MTU 1500 bytes, BW 1544 Kbit, DLY 20000 usec,
     reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation PPP, loopback not set, keepalive set (10 sec)
  LCP Open
  Open: IPCP, CDPCP
  Last input never, output never, output hang never
  Last clearing of "show interface" counters never
  Input queue: 0/75/0 (size/max/drops); Total output drops: 0
  Queueing strategy: weighted fair
  Output queue: 0/1000/64/0 (size/max total/threshold/drops)
     Conversations  0/0/256 (active/max active/max total)
     Reserved Conversations 0/0 (allocated/max allocated)
     Available Bandwidth 1158 kilobits/sec
  5 minute input rate 34 bits/sec, 0 packets/sec
  5 minute output rate 33 bits/sec, 0 packets/sec
     51 packets input, 3944 bytes, 0 no buffer
     Received 33 broadcasts, 0 runts, 0 giants, 0 throttles
     0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored, 0 abort
     50 packets output, 3816 bytes, 0 underruns
     0 output errors, 0 collisions, 1 interface resets
     0 output buffer failures, 0 output buffers swapped out
     0 carrier transitions
     DCD=up  DSR=up  DTR=up  RTS=up  CTS=up

Router_A#
```

### Router_Bの結果

```
Router_B#show interfaces serial 0/0
Serial0/0 is up, line protocol is up (connected)
  Hardware is HD64570
  Internet address is 172.17.0.2/16
  MTU 1500 bytes, BW 1544 Kbit, DLY 20000 usec,
     reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation PPP, loopback not set, keepalive set (10 sec)
  LCP Open
  Open: IPCP, CDPCP
  Last input never, output never, output hang never
  Last clearing of "show interface" counters never
  Input queue: 0/75/0 (size/max/drops); Total output drops: 0
  Queueing strategy: fifo
  Output queue :0/40 (size/max)
  5 minute input rate 33 bits/sec, 0 packets/sec
  5 minute output rate 41 bits/sec, 0 packets/sec
     50 packets input, 3816 bytes, 0 no buffer
     Received 33 broadcasts, 0 runts, 0 giants, 0 throttles
     0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored, 0 abort
     56 packets output, 4204 bytes, 0 underruns
     0 output errors, 0 collisions, 2 interface resets
     0 output buffer failures, 0 output buffers swapped out
     0 carrier transitions
     DCD=up  DSR=up  DTR=up  RTS=up  CTS=up

Router_B#
```

## 1-⑤-(キ)
### 結果

```
Router_A(config-if)#shutdown

Router_A(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to administratively down

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to down

Router_A(config-if)#no shut

Router_A(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to up

Serial0/0 Using hostname from interface PAP

Serial0/0 Using password from interface PAP

Serial0/0 PAP: O AUTH-REQ id 17 len 15

Serial0/0 PAP: I AUTH-REQ id 17 len 15

Serial0/0 PAP: Authenticating peer

Serial0/0 PAP: Phase is FORWARDING, Attempting Forward

Serial0/0 PAP: Phase is FORWARDING, Attempting Forward

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to up
```

## 1-⑤-(ク)

### Router_Aの結果

```
Router_A(config-if)#shutdown

Router_A(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to administratively down

Serial0/0 PPP: Phase is TERMINATING
Serial0/0 LCP: State is Closed
Serial0/0 PPP: Phase is DOWN

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to down

Router_A(config-if)#
Router_A(config-if)#
Router_A(config-if)#no shutdown

%LINK-5-CHANGED: Interface Serial0/0, changed state to down
Router_A(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to up

Serial0/0 PPP: Using default call direction
Serial0/0 PPP: Treating connection as a dedicated line
Serial0/0 PPP: Phase is ESTABLISHING, Active Open

Serial0/0 LCP: State is Open

Serial0/0 PPP: Phase is AUTHENTICATING

Serial0/0 Using hostname from interface PAP

Serial0/0 Using password from interface PAP

Serial0/0 PAP: O AUTH-REQ id 17 len 15

Serial0/0 PAP: I AUTH-REQ id 17 len 15

Serial0/0 PAP: Authenticating peer

Serial0/0 PAP: Phase is FORWARDING, Attempting Forward

Serial0/0 PAP: Phase is FORWARDING, Attempting Forward

Serial0/0 PPP: Phase is FORWARDING, Attempting Forward
Serial0/0 Phase is ESTABLISHING, Finish LCP
Serial0/0 Phase is UP

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to up

Router_A(config-if)#
```

### Router_Bの結果

```
Router_B(config-if)#
%LINK-3-UPDOWN: Interface Serial0/0, changed state to down

Serial0/0 PPP: Phase is TERMINATING
Serial0/0 LCP: State is Closed
Serial0/0 PPP: Phase is DOWN

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to down

Router_B(config-if)#shutdown

%LINK-5-CHANGED: Interface Serial0/0, changed state to administratively down
Router_B(config-if)#
Router_B(config-if)#
Router_B(config-if)#no shutdown

Router_B(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to up

Serial0/0 PPP: Using default call direction
Serial0/0 PPP: Treating connection as a dedicated line
Serial0/0 PPP: Phase is ESTABLISHING, Active Open

Serial0/0 LCP: State is Open

Serial0/0 PPP: Phase is AUTHENTICATING

Serial0/0 LCP: State is Open

Serial0/0 PPP: Phase is AUTHENTICATING

Serial0/0 Using hostname from interface PAP

Serial0/0 Using password from interface PAP

Serial0/0 PAP: O AUTH-REQ id 17 len 15

Serial0/0 PAP: I AUTH-REQ id 17 len 15

Serial0/0 PAP: Authenticating peer

Serial0/0 PAP: Phase is FORWARDING, Attempting Forward

Serial0/0 PAP: Phase is FORWARDING, Attempting Forward

Serial0/0 PPP: Phase is FORWARDING, Attempting Forward
Serial0/0 Phase is ESTABLISHING, Finish LCP
Serial0/0 Phase is UP

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to up

Router_B(config-if)#
```

## 1-⑥-(カ)
### 結果

```
Router_A(config-if)#shutdow

Router_A(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to administratively down

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to down

Router_A(config-if)#
Router_A(config-if)#no shut

Router_A(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to up

Serial0/0 IPCP: O CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: I CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: O CONFACK [Closed] id 1 len 10

Serial0/0 IPCP: I CONFACK [Closed] id 1 len 10

Serial0/0 IPCP: O CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: I CONFREQ [REQsent] id 1 len 10

Serial0/0 IPCP: O CONFACK [REQsent] id 1 len 10

Serial0/0 IPCP: I CONFACK [REQsent] id 1 len 10

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to up

Router_A(config-if)#
```

## 1-⑥-(キ)
### Router_Aの結果

```
Router_A(config-if)#shutdown

Router_A(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to administratively down

Serial0/0 PPP: Phase is TERMINATING
Serial0/0 LCP: State is Closed
Serial0/0 PPP: Phase is DOWN

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to down

Router_A(config-if)#no shut

%LINK-5-CHANGED: Interface Serial0/0, changed state to down
Router_A(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to up

Serial0/0 PPP: Using default call direction
Serial0/0 PPP: Treating connection as a dedicated line
Serial0/0 PPP: Phase is ESTABLISHING, Active Open

Serial0/0 LCP: State is Open

Serial0/0 PPP: Phase is AUTHENTICATING

Serial0/0 IPCP: O CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: I CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: O CONFACK [Closed] id 1 len 10

Serial0/0 IPCP: I CONFACK [Closed] id 1 len 10

Serial0/0 IPCP: O CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: I CONFREQ [REQsent] id 1 len 10

Serial0/0 IPCP: O CONFACK [REQsent] id 1 len 10

Serial0/0 IPCP: I CONFACK [REQsent] id 1 len 10

Serial0/0 PPP: Phase is FORWARDING, Attempting Forward
Serial0/0 Phase is ESTABLISHING, Finish LCP
Serial0/0 Phase is UP

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to up

Router_A(config-if)#
```

### Router_Bの結果

```
Router_B(config-if)#shutdown

%LINK-5-CHANGED: Interface Serial0/0, changed state to administratively down
Router_B(config-if)#
Router_B(config-if)#no shut

Router_B(config-if)#
%LINK-5-CHANGED: Interface Serial0/0, changed state to up

Serial0/0 PPP: Using default call direction
Serial0/0 PPP: Treating connection as a dedicated line
Serial0/0 PPP: Phase is ESTABLISHING, Active Open

Serial0/0 LCP: State is Open

Serial0/0 PPP: Phase is AUTHENTICATING

Serial0/0 LCP: State is Open

Serial0/0 PPP: Phase is AUTHENTICATING

Serial0/0 IPCP: O CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: I CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: O CONFACK [Closed] id 1 len 10

Serial0/0 IPCP: I CONFACK [Closed] id 1 len 10

Serial0/0 IPCP: O CONFREQ [Closed] id 1 len 10

Serial0/0 IPCP: I CONFREQ [REQsent] id 1 len 10

Serial0/0 IPCP: O CONFACK [REQsent] id 1 len 10

Serial0/0 IPCP: I CONFACK [REQsent] id 1 len 10

Serial0/0 PPP: Phase is FORWARDING, Attempting Forward
Serial0/0 Phase is ESTABLISHING, Finish LCP
Serial0/0 Phase is UP

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/0, changed state to up
 
Router_B(config-if)#
```
