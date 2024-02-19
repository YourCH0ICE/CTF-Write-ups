<h1>Task description:</h1>

Q1 -The attacker scanned a range of IPs, storing the results in a file for exfiltration. What's the full path of the output file, the count of active hosts, and the IP & Port used for exfiltration?

Q2- The attacker established a new account for persistence. Can you disclose the name of the new account and its creation date, please? TimeStamp (UTC) Format : 0xL4ugh{FullPath_Count_IP:Port_username_TimeStamp}

```
Exmaple: 0xL4ugh{C:**\fileName.ext_0_127.0.0.1:1337_HackerAwyyy_DD-MM-YYYY_HH:MM:SS}
```

So. I have a file from the first task "Gamer-1". 

It's a zip archive which have inside the all of the system files and folder, and in this archive we have a log files.

<h2>Solution:</h2>

When I had opened it I got the next folders and files:

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/47e0e7c6-121d-4e6f-80a2-d5e19f3534d7)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/eadf7a02-7b68-4864-ab24-b140c554c680)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/5484cf44-7248-486e-931e-453220050c07)

<h3>Step 1:</h3>

Q1 — The attacker scanned a range of IPs, storing the results in a file for exfiltration. What's the full path of the output file, the count of active hosts, and the IP & Port used for exfiltration?

After I had read the first question I realized that this person (Attacker) executed the file whose results were saved in file which had extention most likely .txt. 
Therefore I started looking for a suspicious file using Windows Explorer.

<b>By using ```ctrl + f``` I had found a strange name file and opened it.</b>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/3113d223-d94b-4683-91c3-fc6a92688165)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/4c5ca10e-4e9c-4420-9db0-5b92a5dad843)

And what we see? We see the result of anylizing the ip-adresses. Attacker was looking for an active ip-adresses. 

So, we have ```3``` active ip-adresses.

And as you know: If we find the file we can find the full path. Let's check.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/f3426f44-fe8a-4fe1-bd81-f11270f171d7)

Full path: ```C:\Users\Administrator\AppData\Local\Temp\A52148.txt```.

<h3>Step 2:</h3>

Then we had to find the ```:"the IP & Port used for exfiltration"```. 

In this part I stucked because I had no clue how to find this info. I had been checking files and folders for 2-3 hours to find something interesting, but nothing. 

In one moment I realized: If I have the file and this file have inside ```RESULTS OF EXECUTING SCRIPT``` - I can find this file powershell extention (.ps1) or cmd (.bat) and execute it, when WireShark is running to find IP-adress and port used for exfiltration. 

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/57b7a717-5a97-43b6-bf11-b74d41eb13ce)

So I had started WireShark and then ran the .ps1 script. 

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/8ee10953-0c99-415d-89df-6fe6e496796f)

Then, I was looking for dialog and found something suspecios.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/4b5f8044-b1ac-49aa-b954-eee7256149f9)

After that, I realized that I had not seen the packets that were sent to check for IP address activity, so I concluded that the packets that were sent to ```"172.17.121.9:8080"``` were used to exfiltrate data.

<h3>Step 3:</h3>

The last part was to disclose the name of the new account and its creation date. TimeStamp (UTC).

I used the "AutoPsy" to find it much faster than by using "Windows Explorer".

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/925ad58b-2428-428e-8874-9984b2ca6db9)

And what we see?
We see that the last account which was created has name ```7amoksha``` and the time of creation ```07-01-2024_09:16:20 (IN UTC FORMAT)!```

Our flag: 
```
0xL4ugh{C:\Users\Administrator\AppData\Local\Temp\A52148.txt_3_172.17.121.9:8080_7amoksha_07-01-2024_09:16:20}
```














