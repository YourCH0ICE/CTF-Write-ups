![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/caf26503-487f-4560-a5c8-d237d28b1e75)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/7633c6fc-2602-4e7d-88a7-bb04600bad9f)

<h2>Solution:</h2>

Our file is pcap file.

<h3>Step 1:</h3>

So firstly I started to search info about the flag in the packets.
But before I filtered the all packets by TCP protocol.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/cd7926b0-95ef-40e2-9b1d-8d2d632c8e50)

And found this interesting info.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/ea3d3de6-b5d9-42f4-a151-ab687786993b)

<h3>Step 2:</h3>
It was looking like base64 and I decided to decode it.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/4e840423-97b4-4409-ac4d-efaad9e2a538)

<h2>The flag:</h2>

```wctf{l3tS_3teRn4lLy_g0_bLU3_7n9wm4iWnL}```





