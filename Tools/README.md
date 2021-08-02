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
  - Before checking the hash value of the captured screen, we use the time information of the file to rename the files. Based on the file names, we can compare the files for only 1 second time period. Please, consider the following python code:<br/>`mTime = time.localtime(os.stat(file).st_mtime)`<br/>`t = "%02d%02d%02d " % (mTime.tm_hour, mTime.tm_min, mTime.tm_sec)`<br/>`filename = t + file`<br/>`os.rename(file, filename)`
  - After renaming the files, we use [Certutil](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc732443(v=ws.11)?redirectedfrom=MSDN) to check the hash value of the files. Please, consider the following commands:<br/>`certutil -hashfile "File" MD5`

# Resolution

Resolution is the number of visible pixels in a video frame. We use an open-sourced tool called resdet to obtain the estimated resolution. We capture the recipient's screen every second and use it as the input image to this software, and take the output value as the estimated resolution. For an accurate estimate, we crop the captured image to display only the screen provided by the sender, not the application's interface.

- [resdet](https://github.com/0x09/resdet)
<br/>resdet detects source resolution of upscaled images.

- [FastStone Photo Resizer](https://www.faststone.org/FSResizerDetail.htm)
<br/>FastStone Photo Resizer is an image converter and renaming tool that intends to enable users to convert, rename, resize, crop, rotate, change color depth, add text and watermarks to images in a quick and easy batch mode.


# Streaming Delay

Streaming delay is the time difference between the time when the video is generated at the sender and the time when the video is finally displayed at the receiver, which contains video capture, encoding, transmission, decoding, and rendering delays. To measure the streaming delay, we use the timestamp displayed at the corner of the screen. We record the sender's and the receiver's screens simultaneously and calculate the time difference by comparing the two screens' timestamps.

- Displaying timestamp
<br/>Using the echo command in Linux, we display the current time. Please, consider the following commands: <br/>`while true; do echo -ne "'date +%H:%M:%S:%N'\r"; done`
