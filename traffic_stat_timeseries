# Obtaining per-flow traffic statistics for timeseries analysis

### Install necessary software:

```bash
sudo apt-get install argus-client
```

> To generate the traffic dataset (.pcap) run the following commands from two different terminals

```bash
wget https://your-favorite-software
```

```bash
sudo tcpdump -w your-favorite-software.pcap
```

> Convert the pcap into argus format

```
argus -r your-favorite-software.pcap -w your-favorite-software.argus
```

### Use RABins to generate timeseries from argus:


```bash
rabins -m saddr daddr sport dport proto -M hard time 10s -r your-favorite-software.argus
```

> To remove any flows that you are not interested in, you can use sed

```bash
rabins -m saddr daddr sport dport proto -M hard time 10s -r your-favorite-software.argus |sed '2,${/man/d}'
```
![rabins-demo.png](https://github.com/a-s-m-asadujjaman/scripts/blob/main/rabins-demo.png)
