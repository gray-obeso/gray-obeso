# Scan Surprise

[Challenge Information](#challenge-information)

[Solution](#solution)

[References/Resources](#referencesresources)

## Challenge Information

**Level:** Easy

**Tags:** Forensics, picoCTF 2024, shell, browser_webshell_solvable, qr_code

**Author:** Jeffery John

**Description:**

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/3/challenge.zip)

The same files are accessible via SSH here:
`ssh -p 60693 ctf-player@atlas.picoctf.net`
Using the password `6dd28e9b`. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!

[Challenge Link](https://play.picoctf.org/practice/challenge/444?originalEvent=73&page=1)


## Solution

I solved this challenge using the browser webshell, so I accessed the files via SSH by pasting the command given in the challenge description:

`ssh -p 60693 ctf-player@atlas.picoctf.net`

I was then prompted whether or not I wanted to accept the fingerprint, I typed yes. Then I entered in the password, `6dd28e9b`.

The file I received was `flag.png`. 

It's a QR code, so in order to scan it and get the flag, I entered this command:

`zbarimg flag.png`

And then we have the flag:

`picoCTF{p33k_@_b00_a81f0a35}`

## References/Resources

[zbarimg - Linux man page](https://linux.die.net/man/1/zbarimg)

[Reading QR Codes in Linux](https://www.baeldung.com/linux/read-qr-codes)
