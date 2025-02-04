<h1>ASCII me anything but not the flag</h1>

![image](https://github.com/user-attachments/assets/960f920d-f421-48bd-ab28-59bc66279203)

<h2>Solution: </h2>

<h3>Step 1:</h3>

Let's use the ```CyberChef``` to decode this chars.

![image](https://github.com/user-attachments/assets/b7ac7a71-fe17-487a-8de7-c50527888b73)

<h3>Step 2:</h3>

As we can see we got the Flag, but on the second line we have the PROBABLY key.

So we have to deal with the second line before get the flag. 

By Description below we undestood that the used cipher is ```Caesar Cipher```. 

Let's use the [Caesar Cipher Decoder](https://www.dcode.fr/caesar-cipher)

![image](https://github.com/user-attachments/assets/d63b1903-0bff-4213-82c6-7ac3ace1f6b0)

<h3>Step 3:</h3>

We got the correct key for now. 

So let's think about the Cipher, which requires the key to get the correct string?

It's ```Vigenere Cipher```. So let's decode the flag with key.

![image](https://github.com/user-attachments/assets/6ee0c9c6-1552-49f6-bf4b-9546e5d5f1b3)

<h3>Step 4:</h3>

Now we got the correct STRUCTURE of flag. So let's use the ```Caesar cipher``` again to get the final flag.

![image](https://github.com/user-attachments/assets/7000f553-f549-42be-b55a-45f708c02340)

<h2>The flag:</h2>

```ectf{Th1s_i5_Th3_W4y_0f_3nCrYpti0n}```












