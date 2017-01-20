---
layout: post
title: Deciphering a puzzle from a company's hiring page I came across
excerpt: A friend asked me to look at a puzzle at the hiring page of a company he was applying to. Here is my attempt to the problem. Haven't seen the problem before, so I am not sure if I solved it completely, but sharing my attempt here.
---

## Information Provided
A zipped folder containing a text file and 2 images with following content.

* A string of characters (A, T, C and G)
![_config.yml](/images/CipherAndKey/DNAFragment.png)
* A wheel with some decoding information
![_config.yml](/images/CipherAndKey/KEY-01.jpg)
* A key that indicates use of enigma
![_config.yml](/images/CipherAndKey/KEY-02.jpg)

## Step 1. Decoding codons

Looking at the string, we can immediately observe a message encrypted in language of nucleotides (A, T, C and G). I happen to know a sequence of **three** DNA or RNA nucleotides corresponds to a specific amino acid.


```python
GivenString = "GGCTACTAACATGCCTTTCAACTTCCAGGGTTACTGTCAGGGTACTTATGCTCGCATTTACAAGGGCCCTACTCACTGTCAGAAGGGCTTTGGTCTTCAGGGCAATTCAAAAGAGAACCTACCGATCAATCCATCAGAGAACGAGCTTGGATGTGATACCCCTCACGCAGAAACGGCAGTTTGCATGTGGCGCGACAAAGCACCGCTTACGGAATGGATGTCGGGTGTCCGGGATACACTACTGGCTATAACATTCTGTATCAAGGCTCGGGTCGTATGGGTTAGGATGAGGTAGATCTAGAAGCTTTTCTTCCAGGGCCTCTTTTCTACGAGCGAGCCGCGATACACTCAGAATTGCAGCGTACCCTTTCTTGGATTTAACCAAATAAGCATTACCATCTAAACCATAGATATCAATAAACTGAAATGACACCTGCCGTCGGTTCTACCCGATGCGAATGGTTGAATCCGACGCAATTGACGATTCCAGGCCGGGGCACTATGCAGACGCAAAACCAAAATTTGTAATACATGCGCGGGATGCGGTGTAGAGATCTTTAGACGCTAGCCGCTCGGAAAATGTGTTGGTTTTGCCCGTCAGGGCCCTACTCAGGGTCATGGTAATATTGATTAGACGGGTCCCTGCTTCTCGGGCCACCTGGGTTAGGGTTCCAGCCCGTCCAATAGCTAGGTTTTTGATTATAATGCGGGTTACCCGGGTTATACTGACACTGCCCGCTACTATAAAATTCTCCACTGTCATCGTAACCCGAATCTCTTTGATTCTCACTTACTGTCGACGGCTCGGTTCTTCCAAGCACTGCA"
print(len(GivenString))
```

    825


Provided string is a multiple of three. Seems promising. Lets build a hashmap out of the wheel provided. What seems apparent is outmost letter is encoded by sequence of letters from center to periphery (or vice versa).


```python
import string

charlist = [chr(9658), chr(9608)]+ \
    list(string.ascii_uppercase)+ \
    list([str(x) for x in range(10)])+ \
    list("~!@#$%^&*()-+{}\/<>,.?:;` ")
    
x = 'TCAG'
symbollist = [k+j+i for k in x for j in x for i in x]

mapping = dict(zip(symbollist, charlist))
```

Now that we have a hashmap. Lets try to decode the string provided.


```python
DecodedString = ''
for i in range(0,len(GivenString),3):
    decode = mapping[GivenString[i:i+3]]
    DecodedString += decode
```


```python
DecodedString
```




    ';HIW\\►YOU ARE HALFWAY THERE. ONCE Y█$*.S9>YD5*.2}N7MHTE1*#;^BW{<2Y&9}H`7>- KV`H88;G#4RGY;F:07:J>?+>Q.}►OU SO█H?2\\<6XE.BZ09OCN4IU@%WHWQ#W*GYI8.7~S\\-:C92L.NB@V!YB!4U;3;87Z!Y#Y@BIH71 73K*>OJ!Q\\}3$7KN►LVE THE ENIGMA, DROP US A █ZT-YJQ:►MAIL AT AHMXLVQQI@CUREFIT.COM█EO8-,;F)OU&8/'



Not quite perfect, but you can make out some words

"YOU ARE HALFWAY THERE."

"LVE THE ENIGMA"

"DROP US A █ZT-YJQ:►MAIL AT AHMXLVQQI@CUREFIT.COM"

## Step 2. Enigma

Now I am no cryptography expert, but given they have some nice bunch of keys in one of the images, next logical step is to try out enigma cipher. A simple google search leads you to these nice folks by the name of [Practical Cryptography](http://practicalcryptography.com/ciphers/enigma-cipher/).

They have an online tool to encrypt/decrypt things with enigma. I tried multiple parts of above string in their website. What I think is a possible solution is to decode part in the e-mail address.

![_config.yml](/images/CipherAndKey/Decrypted-01.png)

Seems alright. I guess I have got the e-mail address alright. Didn't try sending them e-mail yet. Didn't try solving the meaning of rest of the sentence as well. If any of you figure it out, let me know in the comments.
