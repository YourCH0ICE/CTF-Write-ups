<h1>I'm wired in</h1>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/edfab31f-b94d-4f49-9967-8c01ba150d6d)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/db31519b-4425-4cb1-83a0-9936bc845981)

<h2>Solution:</h2>

<h3>Step 1:</h3>

So, when I had read the task I understood that I have to determine which keys he pressed. But I had no clue how to do it, 'cause I have never worked with it. 
In one moment via scrolling the system files I find the strange .pcap file.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/36a35ead-f9ae-48dc-920b-c40216f133a4)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/bb479863-d439-41cb-bc6b-fe9a303ca5ff)

<h3>Step 2:</h3>

Then I had to filter the packets by using the next filter: ```usb.transfer_type == 0x01 and frame.len == 35 and!(usb.capdata == 00:00:00:00:00:00:00:00)``` 

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/7aa879b5-e3fc-4d3e-93dc-7a98a6f63d93)

<h3>Step 3:</h3>

Then I saved the all packets in new .pcap file

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/20ad146f-b920-4a3d-8d06-202502ab0fb0)

<h3>Step 4:</h3>

Then I found a scipt on GitHub which can parse the keyboard button presses. 
```https://github.com/carlospolop-forks/ctf-usb-keyboard-parser```

By using command bellow I could extract the button pressing.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/2d5646a2-5bf5-4c1f-9966-3172c9c90d27)

When I had pasted the last command which parse the all information in the plain text — I got the flag:

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/2b9da6dd-0878-49f3-850c-128293b3cf52)

<h3>Step 5:</h3>

<h2>The flag: </h2>

```BITSCTF{I_7h1nk_th3y_4Re_k3yl0991ng_ME!}```












