<h1>The island's treasure</h1>

![image](https://github.com/user-attachments/assets/7900efaa-d494-4baf-b136-ace5cdb64fd0)

![image](https://github.com/user-attachments/assets/d9502325-0e76-4f85-a11c-4f414347180e)

<h2>Solution: </h2>

<h3>Step 1:</h3>

Let's figure out with `Photo of Island` with [Aperisolve](https://www.aperisolve.com/)

![image](https://github.com/user-attachments/assets/77b7033f-e889-4afa-904b-d53286bcee0c)

Let's use the [CyberChef](https://gchq.github.io/CyberChef/) to decode this Base64.

![image](https://github.com/user-attachments/assets/5c30027e-877f-4618-9731-1663979b0a9a)

Seems to be a First part of Key. 

First Part: `M3t4d4t4_15_n0t_5af3`

Let's find the Second Part of Key.

![image](https://github.com/user-attachments/assets/0dbdd8e7-e095-401d-bc7a-3838c59d8c3f)

![image](https://github.com/user-attachments/assets/59b9f298-e8e2-4d8e-8bc4-9ba101031a3b)

Second Part: `Hidd3n_p1ctur3`

We got it.

To open the chest we have to combine key1:key2

Key: `M3t4d4t4_15_n0t_5af3:Hidd3n_p1ctur3`

At this point we need to open the chest using this key.
I tried a lot of tools, but [OpenStego](https://www.openstego.com/) was needed.

![image](https://github.com/user-attachments/assets/840f004f-084a-46b6-8d92-79b655a56695)

![image](https://github.com/user-attachments/assets/cf09a3cd-c9f3-46c5-9a0c-45ed4d090d71)

<h2>The flag:</h2>

`ectf(You_found_th3_tr3asur3}`























