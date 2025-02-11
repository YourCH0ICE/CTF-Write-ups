<h1>Finders Keepers</h1>

We’re given a PNG file.

![image](https://github.com/user-attachments/assets/c1a52986-3535-4c9d-b167-e94fe19d4824)

<h2>Solution: </h2>

<h3>Step 1:</h3>

I used the [CyberChef](https://gchq.github.io/CyberChef/#recipe=Render_Image('Raw')Extract_Files(true,true,true,true,true,true,false,true,100)&oeol=FF) to extract the files from photo.

![image](https://github.com/user-attachments/assets/329bd2de-284c-4b9f-bc18-ba51cf5340ee)

We had found 2 files. 

1 – `.wav` with morse Code

2 – `.jpg` file.

<h3>Step 2:</h3>

I used the [Morse Decoder](https://morsecode.world/international/decoder/audio-decoder-adaptive.html) and uploaded file `.wav` to analyze Morse Code.

![image](https://github.com/user-attachments/assets/53ce5a69-f04e-44ce-b8b3-9e87a337c946)

As we can see it looks like a password.

So let's use the StegHide with `PassPhrase` = `snooooooppppppp` to extract hiden data.

![image](https://github.com/user-attachments/assets/dc4f5c30-59b3-4700-a039-f4631665fd07)

<h2>The flag:</h2>

```BITSCTF{1_4m_5l33py_1256AE76}```


















