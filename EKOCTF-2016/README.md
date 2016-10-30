


# Certified Excel Hacker - Forensic 50

Opening the file in numbers (osx) gives us an error message.
> Hidden sheets were made visible, Sheet: ANSWER

By zooming out on the answer sheet we see the letter E and knowing that the flag format is EKO{xxxxxxxxxx}, we could just read out the flag.

`EKO{HIDDEN_SHEET_123}`

# Hidden inside EKO - misc 50

> Find the hidden flag in the EKO pixels! 

Looking at the CSS sheet gives a link to the static background

https://ctf.ekoparty.org/static/img/background.png

The flag is shown in plaintext

`EKO{th3_fl4g}`


# Mr. Robot - WEB 25

Trying with the robots file https://ctf.ekoparty.org/robots.txt

> Disallow: /static/wIMti7Z27b.txt

Going to the url gives us the flag
https://ctf.ekoparty.org/static/wIMti7Z27b.txt

`EKO{robot_is_following_us}`


