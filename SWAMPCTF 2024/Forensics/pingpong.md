![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/46f2caf3-f3a9-45b8-9624-0284e636bfcb)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/678db74d-de67-468f-8ca0-04663ba03249)

<h2>Solution:</h2>

This a traffic .pcap file in which we have to find the flag. 

<h3>Step 1:</h3>

<b>When I had opened the file I found the ICMP and SSDP protocols.</b>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/efe2ac25-2021-45b6-8f31-76acd863a2fe)

<b>In the SSDP protocol nothing interesting and suspicious. </b>
![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/9ed63280-0456-4ec1-a0cf-8ff4898f7c70)

<h3>Step 2:</h3>

<b>Then I checked the ICMP protocol: </b>

![Запись-экрана-от-11 04 2024-11_20_41](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/d863645a-9df3-4326-b6c8-e06d511204cf)

<b>It looked like base64 and I decided to decode this strings. I opend the last paket. </b>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/45c0df25-e7a8-437f-b602-151cef12dd4a)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/47fc19d1-5972-41d4-bab9-9e7559e6d5ed)

<h3>Step 3:</h3>

<b>It looks like tail of PNG file. And a lot of packets probably is the bytes of this PNG file. So let's check the first packet. </b>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/612fb49b-5314-4462-b53d-4490c31fb3fb)

<h3>Step 4:</h3>
Yeah! It's totally PNG file and other file in the traffic are bytes of PNG.
at that moments I try to get the idea how to extract this info. 
Firsly I had to extract ONLY ICMP packets.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/892febfb-6a25-442a-9b1a-b2aa9e6d0a75)

I used a ```Tshark``` to do that:

```tshark -r '/home/choice/NewOnlyICMPPackets.pcap' -T fields -e data > ExtractedInfo.txt```

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/d770c2eb-80ff-4004-9bee-baf161a41780)

Then let's decode this strings on CyberChef with hex and base64.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/bca08f7f-f0e9-4ab2-a0bf-cb8212df5238)

<h2>The flag:</h2>

```swampCTF{d474_15_3v3rywhe3re}```















