# Monitoring traffic using Gnuplot

Get the detailed information about the plotting from the below-mentioned websites for **Gnuplot** and **Tcpstat**.

[Gnuplot](http://www.gnuplotting.org/plotting-data/)

[Tcpstat](https://frenchfries.net/paul/tcpstat/gnuplot_howto.html)

### Data preparation:

> Generate pcap for required duration from existing capture file

```bash
timeout 10 tcpdump -r sample-point-F-202001011400.pcap -w sample.pcap
```

> Generate the traffic data points

```bash
tcpstat -o "%R\t%b\n" -r sample.pcap > stat.dat
```

> Remove the last line from generated data file

```
sed -i '$ d' stat.dat
```

### Plotting:

> Create Gnuplot script

```bash
nano gnuplot.script

# Set linestyle 1 to blue (#0060ad)
set term png
set out "test.png"
set style line 1 \
    linecolor rgb '#0060ad' \
    linetype 1 linewidth 2 \
    pointtype 7 pointsize 1.5

set format y '%.0s%cb'

plot 'stat.dat' with linespoints linestyle 1
set out
```

> Run Gnuplot7

```bash
gnuplot gnuplot.script
```
