![image](https://github.com/user-attachments/assets/197394e9-2a4c-4c07-b14a-8d764e6e7ee6)<h1>Where When How</h1>

![image](https://github.com/user-attachments/assets/3db9b11b-0341-4769-bd6a-884286f9028e)

![image](https://github.com/user-attachments/assets/5385b9ba-9250-428f-a758-16060bca9abb)

<h2>Solution: </h2>

<h3>Step 1:</h3>

We have a RAM dump. 

Originally I decided to use MagnetAXIOM so he could collect all the artifacts

![image](https://github.com/user-attachments/assets/9f48341b-5cee-46b9-8d31-608096e296b2)

![image](https://github.com/user-attachments/assets/42aefe65-8824-40c9-a6e6-930ff39f3863)

At the moment we can find information about ```WHERE```
And also found information about ```HOW```

<b>WHERE: ```Budapest```</b>

<b>How: ```Airplane```</b>

After that I had to find a date.
I couldn’t find it long enough.
I understood what I needed to look for in the browser history as it contained all the information about TRIP. 
But extracting it through Volatility didn’t help me.

I also had a second theory.
I found information in dump that one night in the hotel costs `13` euros/dollars. 
And I also found the total amount for the hotel.
In theory I could divide this amount by ```13``` to understand how many days the hotel was booked for. 
In addition, I could add `2 days of flight`, in order to count the total number of days of rest.

But it didn’t work out either.

![image](https://github.com/user-attachments/assets/2aa06ed5-23d3-40b6-90f9-3d8fd3b3d821)

So, understanding that the information about TRIP is present somewhere in the dump, I decided to use banally `strings` with a regulator expression as a date

```strings '/home/ubuntu/mdump2.mem' | grep -E '([0-9]{4}[-/]02[-/][0-9]{2}|[0-9]{2}[-/]02[-/][0-9]{4})'```

![image](https://github.com/user-attachments/assets/c0949e28-db53-48aa-ba8a-be252063b493)

And also I have found the strange file `trip cost.txt` 
Then I used `strings` with a regulator expression 

```strings '/home/ubuntu/mdump2.mem' | grep -A 10 "trip cost.txt"```

![image](https://github.com/user-attachments/assets/c11dc43e-c626-4fad-aeff-f8a358be31b9)

So, my answer on WHEN: ```24/01/25-19/02/25```

<h2>The flag:</h2>

```ectf{Budapest.24/01/25-19/02/25.Airplane}```



























