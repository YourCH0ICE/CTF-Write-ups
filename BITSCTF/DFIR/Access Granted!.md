<h1>Access Granted!</h1>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/29669712-db25-4c2c-acb0-e20b746dbc18)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/acf0ca87-d131-4ae7-8124-5dd1ba67e53a)

It was a simply to complite this task, because I undertood that I had find the NTLM hash. So I decided to use the ```volatility3``` with an appropriate plugin.

<h2>Solution:</h2>

<h3>Step 1:</h3>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/dbdc37f5-65f2-48fa-be4b-c173b25b8138)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/1eb811fb-a097-484d-9ca6-bd4f32c7c784)

<h3>Step 2:</h3>

Then we can use the ```https://crackstation.net/``` to crack this hash and get the plain text or the tool ```hashcat``` designed to using in command promt.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/7c65d792-42e6-4c09-8e33-c82fbf3e2431)

After cracking we got the next password: ```adolfhitlerrulesallthepeople```.

<h3>The flag: </h3>

```BITSCTF{adolfhitlerrulesallthepeople}```









