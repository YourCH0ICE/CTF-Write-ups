![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/d1eed88d-4d16-4816-ab88-1502eef8707d)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/5cc03bdc-a488-43fd-b2eb-00925bf7fffb)

<h2>Solution:</h2>

This is a pcap file where we have to find the flag.

<h3>Step 1:</h3>

I saw a strange text data in the HTTP traffic. It looked like symbols. So let's filter by HTTP packets.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/b46f9d78-aa7e-4911-9bc2-b8f3c8d10ea1)

I thought this an our flag. So I decided to check this in the hex dump. 


![Запись экрана от 11 04 2024 12_35_41](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/25f9e8bd-5fbf-4bc9-9e4d-269e4c779c74)

<h2>The flag:</h2>

```swampCTF{w3lc0m3_70_7h3_l4nd_0f_7h3_pc4p}```



