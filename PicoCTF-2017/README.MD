# JSut Duck It Up : REV 100

What in the world could this be?!?!  Link to a file

 HINTS
Maybe start searching for uses of these chunks of characers? Is there anything on the Internet with them?

Looked at the file and identified it as jsfuck. 

Execute the code on http://www.jsfuck.com/ and an alert will prompt with the flag.

`aw_yiss_ducking_breadcrumbs_b703db4e`


# looooong : misc 20

I heard you have some "delusions of grandeur" about your typing speed. How fast can you go at shell2017.picoctf.com:44840?

 HINTS
Use the nc command to connect!
I hear python is a good means (among many) to generate the needed input.
It might help to have multiple windows open

```
import sys
from pwn import *
x = remote('34.206.4.227', 44840)

#Regex to extract between quotes
a = re.findall(r"'(.*?)'", x.recv())

#Extracting the letter + number + ending
b = a[0]
c = int(a[1])
d = a[2]

#constructing payload
payload = b * c
payload += d
payload += "\n"

x.send(payload)
sys.stdout.flush()
print(x.recv()) 

```
