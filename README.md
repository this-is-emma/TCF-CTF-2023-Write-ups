# TFC-CTF-2023-Write-ups
Write ups fpr a couple challenges in the Few Chosen CTF 

## Challenge: DIZZY

### **Category: CRYPTO**

Description: 

Embark on "Dizzy", a carousel ride through cryptography! This warmup challenge spins around the basics of ciphers and keys. Sharpen your mind, find the flag and remember - in crypto, it's fun to get a little dizzy! 

T4 l16 _36 510 _27 s26 _11 320 414 {6 }39 C2 T0 m28 317 y35 d31 F1 m22 g19 d38 z34 423 l15 329 c12 ;37 19 h13 _30 F5 t7 C3 325 z33 _21 h8 n18 132 k24

Solution: 

Naturally the first thing to do is to identifier the cipher we are dealing with. Using [dcode](https://www.dcode.fr/cipher-identifier) we learn that this is likely encoded according to the letter position. Using Dcode decoder, we get a glimpse of the flag but some letters are missing ... 

**TFCCTF{th_chllng_mks_m_dzzy_;d}**

That's because it was intended to be solved without using automated tools. So doing it by hand where: 
`T4` => Letter T at the 4th position
`l16` => Letter l at the 16th position 
... etc

will give us the flag! 

`TFCCTF{th15_ch4ll3ng3_m4k3s_m3_d1zzy_;d}`

## Challenge: Baby Ducky Notes 

### **Category: WEB**

Description: 

Quack Quack! Try and Huack me!

solution: 

After starting the container, we land on a web page with a login and register button. We dont have any credential so we create a new account and then create a post. Then take a peak at the url, if we just type `admin` in the URL like so:

`..container../posts/view/admin` 

we will access admin's post, while being logged in as the user we just created. 
This is an example of an **"Insecure Direct Object Reference" (IDOR) vulnerability.**

and voila! Flag obtained:

![flag](https://github.com/this-is-emma/TCF-CTF-2023-Write-ups/assets/8417822/699f40a5-acdb-4b4e-8c14-763b771d124e)

