<h1>Just a PCAP</h1>

![image](https://github.com/user-attachments/assets/e7a40805-665d-4ab1-9c6e-7628f35c2223)

![image](https://github.com/user-attachments/assets/abfb22da-289b-48a5-8d40-9d223452a98e)

<h2>Solution: </h2>

<h3>Step 1:</h3>

Let's use the Wireshark to open this file.

![image](https://github.com/user-attachments/assets/6e9a020a-cbff-4687-a67d-39c50fbceea2)

We have only DNS traffic. 
And let's pay attention on ```Name``` field.

![image](https://github.com/user-attachments/assets/9af8a077-329a-40bf-934e-1e495a4af144)

Looks like a hex-data of file. 
So let's extract the last line to get the hex value.

![image](https://github.com/user-attachments/assets/e65ecb9b-3402-4d90-aaaa-50d27e0ba4c3)

We exported the last string to check what it is.

Maybe it’s some kind of file?

Let's use the CyberChef

![image](https://github.com/user-attachments/assets/73d5650a-afef-45d1-b028-e7ad6125c5d0)

As we can see above, it is indeed the end of the file. Because you saw the text "IEND" that say that this is the end of the picture.

So let’s extract all the data that is up to the point.

![image](https://github.com/user-attachments/assets/edd6fe2f-3912-4490-af0d-910de2462116)

Let's use the following command to extract specific bytes in file and remove ```\n```.

```tshark -r '/home/ubuntu/Downloads/justapcap(1).pcap' -T fields -e dns.qry.name | cut -d'.' -f1 | tr -d '\n' > picture.txt```

![image](https://github.com/user-attachments/assets/5bef2dbb-4c52-4e6a-9917-e46f029d2e70)

<h2>The flag:</h2>

```ectf{DN5_3xflltr@tl0n_15_flnd3```





