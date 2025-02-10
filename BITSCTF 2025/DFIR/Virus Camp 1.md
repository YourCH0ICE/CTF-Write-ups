<h1>Virus Camp 1</h1>

In this chall we have to Analyze another `.ad1` file and try to find the footprint of Virus, which have encrypt the flag. 

![image](https://github.com/user-attachments/assets/72ede895-9870-4a51-a5e0-31f16017d771)

<h2>Solution: </h2>

<h3>Step 1:</h3>

Let's use the FTK Imager again.

![image](https://github.com/user-attachments/assets/01283abd-532a-4ef9-9764-eb454d01fe0b)

First of all I found the encrypted flag.

But anyway I have to know how this `file` was encrypted. And where was the `Initial Access`.

![image](https://github.com/user-attachments/assets/202d3940-613b-48c8-8a78-22baffe16656)

After a while I found a `strange file` that contained `Java-Script` code. 

I have analyzed it, found the `details of the Malware` and the `flag` also.

![image](https://github.com/user-attachments/assets/3114d310-ee2f-49df-b4e2-f9732439f523)

Let's use the [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=VkdobElERnpkQ0JtYkdGbklHbHpPaUJDU1ZSVFExUkdlMGd3ZDE5ak5HNWZkbE5mWXpCa00xOXNNM1JmZVRCMVgzQjFZbXd4YzJoZmJUUnNNV05wYjNWelgyVjROek51YzJrd2JuTmZVMDlmWldGemFXeDVQejlmTldFM1lqTXpObU45)

![image](https://github.com/user-attachments/assets/69fa3715-0b51-4907-98e4-3b1ef512f0ea)

<h2>The flag:</h2>

```BITSCTF{H0w_c4n_vS_c0d3_l3t_y0u_publ1sh_m4l1cious_ex73nsi0ns_SO_easily??_5a7b336c}```









