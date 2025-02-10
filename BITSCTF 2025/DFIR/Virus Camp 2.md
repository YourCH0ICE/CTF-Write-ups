<h1>Virus Camp 2</h1>

In this task, we have to undestand how the file was encrypted.

<h2>Solution: </h2>

<h3>Step 1:</h3>

As we can see in the previous task, we have to analyze the file located in `Temp` folder.

So let's start.

![image](https://github.com/user-attachments/assets/889db7ac-de63-4437-90e8-ec50f9877610)

<h3>Step 2:</h3>

Let's use the `Notepad++` or another `tool` to paste this code. (I used `Notion`).

![image](https://github.com/user-attachments/assets/8b03cb0e-7154-4b36-a3f6-293fd755df1b)

As we can see it's like an obfuscated PowerShell script. 

So let's figure out...

The long string in `Base64 encoding`, placed in a distributed array of chars – is the main thing. 

![image](https://github.com/user-attachments/assets/1d148ec4-fd61-4591-8332-506e24fc1595)

P.S. This string is reversed by `Reverse()` function.

So let's use the `CyberChef` to decode it. 

![image](https://github.com/user-attachments/assets/3836e03c-ccf8-47f9-abc0-9da667a53d32)

As we can see above – we have the code, which used for encryption the main flag. 

It's originally PNG file, which was encrypted as we can see in the code.

```
$password = "MyS3cr3tP4ssw0rd"
$salt = [Byte[]](0x01,0x02,0x03,0x04,0x05,0x06,0x07,0x08)
$iterations = 10000
$keySize = 32   
$ivSize = 16 

$deriveBytes = New-Object System.Security.Cryptography.Rfc2898DeriveBytes($password, $salt, $iterations)
$key = $deriveBytes.GetBytes($keySize)
$iv = $deriveBytes.GetBytes($ivSize)

$inputFile = "C:\\Users\\vboxuser\\Desktop\\flag.png"
$outputFile = "C:\\Users\\vboxuser\\Desktop\\flag.enc"

$aes = [System.Security.Cryptography.Aes]::Create()
$aes.Key = $key
$aes.IV = $iv
$aes.Mode = [System.Security.Cryptography.CipherMode]::CBC
$aes.Padding = [System.Security.Cryptography.PaddingMode]::PKCS7

$encryptor = $aes.CreateEncryptor()

$plainBytes = [System.IO.File]::ReadAllBytes($inputFile)

$outStream = New-Object System.IO.FileStream($outputFile, [System.IO.FileMode]::Create)
$cryptoStream = New-Object System.Security.Cryptography.CryptoStream($outStream, $encryptor, [System.Security.Cryptography.CryptoStreamMode]::Write)

$cryptoStream.Write($plainBytes, 0, $plainBytes.Length)
$cryptoStream.FlushFinalBlock()

$cryptoStream.Close()
$outStream.Close()

Remove-Item $inputFile -Force
```

What about the decode function?

We can use the same `IV`, `Key`, `Password` but have to use the `Decryptor` insted of `Incryptor` in the code.

So let's start.

```
$password = "MyS3cr3tP4ssw0rd"
$salt = [Byte[]](0x01,0x02,0x03,0x04,0x05,0x06,0x07,0x08)
$iterations = 10000
$keySize = 32   
$ivSize = 16 

$deriveBytes = New-Object System.Security.Cryptography.Rfc2898DeriveBytes($password, $salt, $iterations)
$key = $deriveBytes.GetBytes($keySize)
$iv = $deriveBytes.GetBytes($ivSize)

$inputFile = "C:\\Users\\Mykhailo\\Desktop\\flag.enc"
$outputFile = "C:\\Users\\Mykhailo\\Desktop\\flag.png"

$aes = [System.Security.Cryptography.Aes]::Create()
$aes.Key = $key
$aes.IV = $iv
$aes.Mode = [System.Security.Cryptography.CipherMode]::CBC
$aes.Padding = [System.Security.Cryptography.PaddingMode]::PKCS7

$decryptor = $aes.CreateDecryptor()

$encryptedBytes = [System.IO.File]::ReadAllBytes($inputFile)

$outStream = New-Object System.IO.FileStream($outputFile, [System.IO.FileMode]::Create)
$cryptoStream = New-Object System.Security.Cryptography.CryptoStream($outStream, $decryptor, [System.Security.Cryptography.CryptoStreamMode]::Write)

$cryptoStream.Write($encryptedBytes, 0, $encryptedBytes.Length)
$cryptoStream.FlushFinalBlock()

$cryptoStream.Close()
$outStream.Close()
```

And we got the flag!

![image](https://github.com/user-attachments/assets/7a7fed84-83b3-41a4-994a-bc20a2c1d603)

<h2>The flag:</h2>

```BITSCTF{h0pe_y0u_enj0yed_th1s_145e3f1a}```























