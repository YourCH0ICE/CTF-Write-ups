![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/7377b2e6-ae4d-47a6-b7c2-406fc48bce7a)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/722e17b1-22bd-4d7b-a9b2-1e6d75b29bfe)

<h2>Solution:</h2>

<h3>Step 1:</h3>

This a .pcap file in which we have to find the ```username of compromised account```

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/61cc8a53-b434-4ad3-a6a4-6e69ef1184d9)

I saw the http packets in which we can find ```NTLMSSP auth``` by username ```Administrator```, so then I decided to filter the packets by HTTP and try to find the other username.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/6d7e5cb6-4592-49bc-85b9-c55b7dc9e9af)

And we see that auth happened by user with username ```adamkadaban```.

<h2>The flag:</h2>

```swampCTF{adamkadaban}```



 

