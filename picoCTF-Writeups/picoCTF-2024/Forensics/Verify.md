# Verify
[Challenge Information](#challenge-information)

[Solution](#solution)

[References/Resources](#referencesresources)

## Challenge Information
**Level:** Easy

**Tags:** Forensics, picoCTF 2024, grep, browser_webshell_solvable, checksum

**Author:** Jeffery John

**Description:**

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_rhea/10/challenge.zip)

The same files are accessible via SSH here:
`ssh -p 55688 ctf-player<span>@</span>rhea.picoctf.net`
Using the password `83dcefb7`. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!

- Checksum: `467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02`
- To decrypt the file once you've verified the hash, run `./decrypt.sh files/<file>`.

[Challenge Link](https://play.picoctf.org/practice/challenge/450)

## Solution

I solved this challenge using the browser webshell, so I accessed the files via SSH by pasting the command given in the challenge description:

`ssh -p 55688 ctf-player<span>@</span>rhea.picoctf.net`

I was then prompted whether or not I wanted to accept the fingerprint, I typed `yes`. Then I entered in the password, `83dcefb7`.

The files I recieved were `checksum.txt`, `decrypt.sh`, and a directory titled `files` that contained several files.

I then searched for the given SHA-256 hash by entering in the following command:

`sha256sum files/* | grep 467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02`

I was given this result:

`467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02  files/c6c8b911`

The file, `c6c8b911`, was encrypted. So then I ran the decryption program provided to recieve the flag:

`./decrypt.sh files/c6c8b911`

And then we have the flag:

`picoCTF{trust_but_verify_c6c8b911}`

## References/Resources

[grep - Linux manual page](https://man7.org/linux/man-pages/man1/grep.1.html)

[sha256sum - Linux manual page](https://man7.org/linux/man-pages/man1/sha256sum.1.html)

[Wikipedia - Cryptographic hash function](https://en.wikipedia.org/wiki/Cryptographic_hash_function)

[Wikipedia - SHA-2](https://en.wikipedia.org/wiki/SHA-2)
