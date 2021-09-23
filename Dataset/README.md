## Motivation
### A strong positive relationship between the sender’s rate and the receiver’s rate (or quality)
link is the delay setup and measured throughput (sending rate at user1) and goodput (receiving rate at user2). <br />
It was used for plotting Figure 1: The CDF of throughput and video quality for applications using cloud servers under delay variation.

### Performance comparison under various network scenarios 
link is the packet loss rate setup and measured throughput and latency of applications. <br />
link is the delay setup and measured throughput and latency of applications. <br />
link is the available bandwidth setup and measured throughput and latency of applications. <br />
They were used for plotting Figure 3: Performance comparison between six video conferencing applications and WebRTC.

## Impact of Network Parameters
### Impact of available bandwidth
We check each application’s adaptation behavior while varying the bandwidth from 200Kbps to 5Mbps in 100Kbps steps. <br />
We find that all video conferencing applications keep track of the available bandwidth with different levels of a margin such that they achieve maximum attainable bitrate while not causing any significant congestion. <br />
link is the result.

### Impact of propagation delay
We added the additional propagation delay from 0ms to 400ms while fixing the available bandwidth and packet loss rate at 10Mbps and 0%, respectively. <br />
Our measurement results show that all applications maintain their bitrate while video streaming delay increases linearly, as the propagation delay increases, leading rate insensitivity to the fixed propagation delay. <br />
link is the result.

### Impact of delay variance
We insert a sudden additional delay to the applications to see if their rate controls are different from the fixed propagation delay case above. <br />
We observe that all applications temporarily lower their bit rate due to the extra delay but recover shortly. We conjecture that delay-based rate adaptation mechanisms in the video conferencing applications use the delay variation rather than its fixed value. <br />
link is the result.

### Impact of packet loss rates
We vary the packet loss rates, ranging from 0% to 10%, while fixing the bandwidth and propagation delay. <br />
We observe that the sending rate of each application exceeds the maximum bitrate observed in the ideal scenario. The increases come from loss recovery mechanisms such as forward error correction (FEC) and packet retransmission. <br />
link is the result.


Dataset will be posted here soon.
