<h1>Hashes Binder</h1>

![image](https://github.com/user-attachments/assets/4c19a770-5bb7-49f1-b81a-2a28da852a80)

![image](https://github.com/user-attachments/assets/731c4b60-86ff-4f48-8f50-27cd5e28d79b)

<h2>Solution: </h2>

<h3>Step 1:</h3>

Initially we need to get the hash of the encrypted file ```.xlsx```.
We can do this using ([office2john.py](https://github.com/Deloril/Python/blob/master/office2john.py) script) or ([office2john.py](https://hashes.com/ru/johntheripper/office2john) web-site).

![image](https://github.com/user-attachments/assets/ffdda9b4-778d-4423-b92b-a922b4fd7819)

![image](https://github.com/user-attachments/assets/e6c484e9-b827-4337-8a25-a7f7ba752349)

<h3>Step 2:</h3>

Let's use the hashcat to crack this hash and get the password for the encrypted file

![image](https://github.com/user-attachments/assets/37698148-6523-4353-8bb3-52095f9e69ac)

![image](https://github.com/user-attachments/assets/8e9f888f-c8df-49a4-aaca-6bc1ff20bcc6)

![image](https://github.com/user-attachments/assets/f019f4e4-87c8-4f7f-b658-69d6d069aa5a)

<h3>Step 3:</h3>

Try using the found password to ```.xlsx```.

![image](https://github.com/user-attachments/assets/dc64d390-8314-4825-99fb-3733a5242211)

<h3>Step 4:</h3>

Let's figure out with ```Part1``` by using CyberChef

![image](https://github.com/user-attachments/assets/94b154a2-6d36-4ee4-bb41-1d2d2bb7e330)

As we can see it's not a hex. Let's use the [Cipher Identifier](https://www.dcode.fr/cipher-identifier) to get the correct hash-value.

![image](https://github.com/user-attachments/assets/9c964074-f25a-487f-85dd-ae28fb175fc7)

Let's use the [Hashes.com](https://hashes.com/ru/decrypt/hash) to Crack hash

![image](https://github.com/user-attachments/assets/e878a98f-0c17-459e-8798-f5afbef1e366)

<b>Part 1: spooky </b>

<h3>Step 5:</h3>

Let's figure out with ```Part2``` by using CyberChef

![image](https://github.com/user-attachments/assets/f80a4257-2ae6-459c-bf81-871bedd1bb70)

<b>Part 2: digestive </b>

<h3>Step 6:</h3>

Let's figure out with ```Part3``` by using CyberChef

![image](https://github.com/user-attachments/assets/253fc113-61c0-4c7d-86f9-680dabb00e9e)

<b>Part 2: prescription </b>

<h3>Step 7:</h3>

Now let's try to open the Achive, but let's look on the password format.

![image](https://github.com/user-attachments/assets/c2e19047-a574-437c-9b82-154907c55a9e)

So let's concat the all found parts:

![image](https://github.com/user-attachments/assets/a3568b2d-4297-4e79-b9e2-4bf30613188b)

<h2>The flag:</h2>

```ECTF{J0nH_tH3_Cr4ck3R_95234826}```






















