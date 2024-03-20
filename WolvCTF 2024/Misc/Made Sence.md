<h1>Made Sense</h1>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/6ef925aa-8c60-4ed6-90f8-d8d0d691244b)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/c3d0c734-8b4f-4882-b1e4-c96067347803)

<h2>Solution:</h2>

<h3>Step 1:</h3>

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/27c45649-0c4f-4835-bde9-f8a3497742c7)

I decided to check the ```source code``` to get some info how it works.

```import os
from pathlib import Path
import re
import subprocess
import tempfile

from flask import Flask, request, send_file

app = Flask(__name__)
flag = open('flag.txt').read()


def write_flag(path):
    with open(path / 'flag.txt', 'w') as f:
        f.write(flag)


def generate_makefile(name, content, path):
    with open(path / 'Makefile', 'w') as f:
        f.write(f"""
SHELL := /bin/bash
.PHONY: {name}
{name}: flag.txt
\t{content}
""")


@app.route('/', methods=['GET'])
def index():
    return send_file('index.html')


@app.route('/src/', methods=['GET'])
def src():
    return send_file(__file__)


# made sense
@app.route('/make', methods=['POST'])
def make():
    target_name = request.form.get('name')
    code = request.form.get('code')

    print(code)
    if not re.fullmatch(r'[A-Za-z0-9]+', target_name):
        return 'no'
    if '\n' in code:
        return 'no'
    if re.search(r'flag', code):
        return 'no'

    with tempfile.TemporaryDirectory() as dir:
        run_dir = Path(dir)
        write_flag(run_dir)
        generate_makefile(target_name, code, run_dir)
        sp = subprocess.run(['make'], capture_output=True, cwd=run_dir)
        return f"""
<h1>stdout:</h1>
{sp.stdout}
<h1>stderr:</h1>
{sp.stderr}
    """


app.run('localhost', 8000)
```

<h3>Step 2:</h3>

I saw 2 usefull ```functions```: 
```'
def generate_makefile(name, content, path):
    with open(path / 'Makefile', 'w') as f:
        f.write(f"""
SHELL := /bin/bash
.PHONY: {name}
{name}: flag.txt
\t{content}
""")
```

And the second one: 
```
def make():
    target_name = request.form.get('name')
    code = request.form.get('code')

    print(code)
    if not re.fullmatch(r'[A-Za-z0-9]+', target_name):
        return 'no'
    if '\n' in code:
        return 'no'
    if re.search(r'flag', code):
        return 'no'
```

So, I decided to check different commands and as I saw in the code: If I'll enter the ```flag``` word - I'll get the ```no``` error.
Thefore I entered the next command:

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/fb693bb3-f426-4137-930e-e4cdeee306f9)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/cec63e4e-4094-4864-8567-b0c78c20e959)

<h3>Step 3:</h3>

And I realized that the ```ls``` command works, thefeore I had to figure out how I can read the flag without the ```flag word``` in the request.

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/c02fe5e5-0faa-4eb0-a629-48821d72694e)

![image](https://github.com/YourCH0ICE/CTF-Write-ups/assets/127401530/7c811d0d-8ef9-4290-98a9-03d850674904)

<h2>The flag:</h2>

```wctf{m4k1ng_vuln3r4b1l1t135}```
