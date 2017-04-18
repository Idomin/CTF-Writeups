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

# VR Gear Console

Here's the VR gear admin console. See if you can figure out a way to log in. The problem is found here: /problems/51645e84d55d376442beaf264e0908b9

 HINTS
What happens if you read in more characters than the length of the username buffer?
You should look at an ascii table to see what character you need to choose.
Numbers are stored in little-endian format, which means that the lowest byte of the number is first.
"cat file - | vrgearconsole " will keep the pipe open for commands.

Reference : http://www.asciitable.com/ 

```
    if (access >= 0xff || access <= 0) {
        printf("Login unsuccessful.\n");
        exit(10);
    } else if (access < 0x30) {
        printf("Admin access granted!\n");
        printf("The flag is in \"flag.txt\".\n");
        system("/bin/sh");
    } else {
        printf("Login successful.\n");
        printf("You do not have permission to access this resource.\n");
        exit(1);
    }

```
If Username == AAAAAAAAAAAAAAAAAAAAA for example the acesslevel will be set to 0x41414141 and we get to the else case.

If Username == AAAAAAAAAAAAAAAAA  we get 0x00000041 and we need to set access < 0x30   -> Look at asciitable and we know $ is hex 24 so lets go with that.

Username == AAAAAAAAAAAAAAAA$  -> Results in shell.








