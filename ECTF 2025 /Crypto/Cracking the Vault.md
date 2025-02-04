<h1>Cracking the Vault</h1>

![image](https://github.com/user-attachments/assets/f56a2539-bbd4-4606-8c28-7b4049fba812)

![image](https://github.com/user-attachments/assets/92845b33-bcba-4f56-8645-5924005ee6c8)

<h2>Solution: </h2>

<h3>Step 1:</h3>

<b>Original code of Encryption:</b>

![image](https://github.com/user-attachments/assets/bcae7f37-7fe1-41bd-bfc4-7805b534306f)


I tried to write functuon of ```Guessing Seed``` of Encrypted text.
So let's check the code below:
```
import hashlib

# gtting seed
def get_seed(text):
    secret_key = str(sum(ord(c) for c in text))  # sum Codes
    secret_key = secret_key[::-1]  # string reverse
    hashed_key = hashlib.sha256(secret_key.encode()).hexdigest()
    return int(hashed_key[:16], 16)  # first 16 symbols --> to hash

# dec
def decryption(encrypted_text, seed):
    decrypted = []
    
    for i, char in enumerate(encrypted_text):
        char_code = ord(char)
        shift = (i + 1) * 3
        original = (char_code - 67 - shift) % 256
        decrypted.append(chr(original))
    
    return ''.join(decrypted)

with open('c:\\Users\\Mykhailo\\Desktop\\VaultKey_encrypted.txt', 'r', encoding='utf-8', errors='ignore') as f:
    encrypted_text = f.read()

# try to get seed value :)
seed = get_seed(encrypted_text)

decrypted_text = decryption(encrypted_text, seed)

with open('VaultKey_decrypted.txt', 'w', encoding='utf-8') as f:
    f.write(decrypted_text)

print("The file has been successfully decrypted!")
```

![image](https://github.com/user-attachments/assets/82659271-23ca-4041-9fff-232cf3941fe9)

<h2>The flag:</h2>

```ectf{1t_W45_ju5T_4_m1nu5}```





