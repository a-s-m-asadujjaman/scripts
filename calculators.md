### Transmission Delay

This [online calculator](https://www.vcalc.com/wiki/JustinLiller/Transmission+Delay) is very useful.

> Following code can be used to calculate transmission delay in Python: -

```python
PKTSIZE = 1514                                          # Ethernet packet size in bytes
RATE = 1024                                             # 1Gbps link
print("{0:.8f} sec".format((PKTSIZE*8)/(RATE*1024*1024)))  # Convert to bits and bits/sec
```
