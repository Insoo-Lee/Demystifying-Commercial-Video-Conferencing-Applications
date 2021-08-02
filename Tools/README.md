# Sending Rate

Sending rate is the number of bits transmitted per second over the network, measured by using TCPDUMP (WinDump).

- [TCPDUMP](https://www.tcpdump.org/index.html)
<br/>TCPDUMP is a powerful command-line packet analyzer for UNIX.
- [WinDump](https://www.winpcap.org/windump)
<br/>WinDump is the Windows version of tcpdump.
- [Wireshark](https://www.wireshark.org/)
<br/>Wireshark is the world’s foremost and widely-used network protocol analyzer.

# Frame Rate

Frame rate is the number of frames per second that appear on a screen. Specifically, we display a clock in nanoseconds at the corner of the video screen and capture the screen using the ScreenToGif program. Then, we check the hash values of the captured screens to calculate how many times the screen changed per second.

- [ScreenToGif](https://www.screentogif.com/)
<br/>ScreenToGif is a screen, webcam, and sketch board recorder with an integrated editor.
- Checking hash values

# Resolution

Resolution is the number of visible pixels in a video frame. We use an open-sourced tool called resdet to obtain the estimated resolution. We capture the recipient's screen every second and use it as the input image to this software, and take the output value as the estimated resolution. For an accurate estimate, we crop the captured image to display only the screen provided by the sender, not the application's interface.

- [resdet](https://github.com/0x09/resdet)
<br/>resdet detects source resolution of upscaled images.

- [FastStone Photo Resizer](https://www.faststone.org/FSResizerDetail.htm)
<br/>FastStone Photo Resizer is an image converter and renaming tool that intends to enable users to convert, rename, resize, crop, rotate, change color depth, add text and watermarks to images in a quick and easy batch mode.


# Streaming Delay

Streaming delay is the time difference between the time when the video is generated at the sender and the time when the video is finally displayed at the receiver, which contains video capture, encoding, transmission, decoding, and rendering delays. To measure the streaming delay, we use the timestamp displayed at the corner of the screen. We record the sender's and the receiver's screens simultaneously and calculate the time difference by comparing the two screens' timestamps.

- Displaying timestamp
