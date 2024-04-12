![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/04a04c6f-6627-49a5-98ba-64e0461ed20c)![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/d94c0b57-7d0c-464d-ae22-44f17a00d28f)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/8b8df98d-613b-49c7-a479-a081ceb279d7)

<h2>Solution:</h2>

It was the most hard task of the Forensics category. I know that we have to recover the NTLMv2 hash of the the user ```adamkadaban``` because we saw the NTLMv2 auth, but I had no clue how to solve this...

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/176ede8e-589a-4049-9dd9-f9b3f2aeca11)

But at the one moment I understood that we can recover this NTLMv2 by using the next packets:

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/3729b6f5-a6b4-47c7-8785-6186de5f2da9)

How? So we have to find the hext value: 

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/8ef214df-b478-43c8-bbe1-84acf6a79c26)

So, How to find it? Above-mentioned packets can help us. 

<h3>Step 1:</h3>

Let's start. 
```Name``` = ```adamkadaban```

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/c878508a-f9f7-4148-805b-7fb9138c86de)

```Domain``` = ```NULL``` so we can enter like ```:```

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/fa77ac25-24ff-417f-9fe1-0c42d1042a01)

```Challenge``` = ```1fed9e8e0ca470a3```

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/b3d4c90f-c9a5-4e7a-9cc2-ef4566c1e6e9)

```HMAC-MD5``` = ```98ebffae0b77865893846dfadb757cfb```

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/4e4fe314-e951-45ed-ac76-1894f2f0ca97)

```NTLMv2Response``` = ```The string without 16 bytes or without HMAC-MD5 value``` = ```0101000000000000801c50dbc266da0188d48d08eff230a80000000002001e0045004300320041004d0041005a002d00450033003300530047004c00380001001e0045004300320041004d0041005a002d00450033003300530047004c00380004001e0045004300320041004d0041005a002d00450033003300530047004c00380003001e0045004300320041004d0041005a002d00450033003300530047004c003800070008005783ebd6c266da010000000000000000```

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/2657c144-4e99-49fa-bdf4-72c751689fc3)

<h3>Step 2:</h3>

After finding all the values we get the next file:

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/5e756bf8-dda4-4586-abf5-4bbcb0da05f5)

Then we have to change this file:

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/b6c03f76-7737-4980-81ee-a92d1d043f39)

It looks like NTLM hash, we have to crack it. Let's try.

<h3>Step 3:</h3>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/fb596d71-997b-4bbf-8ef3-f62c4ba05e67)

Wow! It's our password. Cool task!

<h2>Flag:</h2>

```swampCTF{emilyyoudontknowmypassword}```





















