#### Writeup on https://overthewire.org/wargames/bandit/


#### Level 0

It was a great challenge to find and learn about ssh and how to access it etc. It was fun. Now moving forward!
It was related to logging in by the way.
![Screenshot from 2023-10-20 23-38-00](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/c7d3a993-88c6-4c0c-8cbc-965161373488)

#### Level 0 -> Level 1

Done with level 1. I couldnt understand how to solve it at first then i learnt by referring to google.
I then used cat readme to access the readme library and got the password and then moved forward.
Password:NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
Code used 
```
cat readme
```
![Screenshot from 2023-10-20 23-40-56](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/000dce65-347e-4718-aedd-9c1beaa9cade)

#### Level 1 -> Level 2

Tried cat - but it doesnt work it started lagging.
Now i tried cat ./- after i looked it up how to represent a library since it can't detect a '-' on its own
so the password is rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
Code used is
```
cat ./-

```
![Screenshot from 2023-10-20 23-44-53](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/95de76c3-bb8d-4192-b1b7-2349040362ee)

#### Level 2 -> Level 3

Didnt get it becasue I started with il and then home directory opened so couldnt find spaces in this filename there so then I realised I had to exit and then again I logged in and then I tried cat spaces\ in\ this\ filename it worked.
The mistake happened because I used misinformation from google.
password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
Code used is:
```
cat spaces\ in\ this\ filename
```
![Screenshot from 2023-10-20 23-51-22](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/3612a8af-e4cf-4ecb-b8ab-5fbcee7c83e5)

#### Level 3 -> Level 4

Tried find cat inhere but it didnt work. So next tried find inhere. Got the hidden directory which was inhere/.hidden. This i looked it up on google.
The password is 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
Code used :
```
find inhere
cat inhere/.hidden
```
![Screenshot from 2023-10-20 23-56-13](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/d3c731eb-2bdb-4912-a16d-be448eb3fa63)

#### Level 4 -> Level 5

First tried the same thing. I put find in here, then i got 9 files like inhere/-file01 and then I started acessing them one by one and got random characters in each and then at the last I got the password at inhere/-file07
the password was lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
The code used is
```
find inhere
```
![Screenshot from 2023-10-21 00-16-48](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/a854d62b-bfd7-44dd-88a1-7652cfa3f10b)

#### Level 5 -> Level 6

So i continued with the same procedure i.e. find inhere but then i got many files
so now i had to find that one file which satisfied the following characteristics
human-readable
1033 bytes in size
not executable
I looked up on google the function of find and how to use or write a command that helps in identifying the above properties. Thus I put the codes given below. And i got the password P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
Code used is
```
find inhere
find . -type f -size 1033c ! -executable -exec file {} \;
$ cat inhere/maybehere07/.file2
```
![Screenshot from 2023-10-21 01-42-47](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/a7665031-ff69-4353-97f8-d7ee8b04c506)


#### Level 6 -> Level 7

Here I did the same thing as before just making some minute changes in my code according to the characteristics given. Although I committed many errors while forming the code in between. 
The codes are given below. I got the password as z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
Codes used:
```
find / -user bandit7 -group bandit6 -size 33c -type f 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
![Screenshot from 2023-10-21 01-57-56](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/1bff8d37-b4e4-45fd-ae6f-3aaba204cdd4)

#### Level 7 -> Level 8

Here it was a bit confusing. I first looked up the functions of the commands given in the questions. I tried grep -millionth -data.txt bu this didnt work. So next i tried reading the data.txt file directly through the command cat data.txt but then I got millions of password. And then finally i used grep millionth data.txt.
Password:TESKZC0XvTetK0S9xNwm25STk5iWrBvP
Code used:
```
grep millionth data.txt
```
![Screenshot from 2023-10-21 02-19-33](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/a06025aa-3b22-465f-ac73-faede2852877)

#### Level 8 -> Level 9

This was more confusing than the other levels. I started using the commands according to the given commands that would be used. For example I used uniq data.txt, uniq -u data.txt, sort data.txt, etc nothing worked. Then after referring to the manual and looking up the proper functtions of the given command at last i put the command given below and got the password EN632PlfYiZbn3PhVK3XOGSlNInNE00t
Code used:
```
cat data.txt | sort | uniq -u
```
![Screenshot from 2023-10-21 02-47-06](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/6b1e0938-7909-48d6-975d-2243ae8752d4)

#### Level 9 -> Level 10Here I had to first filter out  the special characters and get just the string i.e. text passwords. So I used the command cat data.txt | strings | sort | uniq -u. But this didn't work. Then I looked up how to filter out filter out random unreadable characters. Then after some understanding I used the command grep data.txt | strings. But still didnt work. Then I used strings data.txt | grep. Then I noticed the small detail that "preceded by several ‘=’ characters.". Then i used the code given below and i got the password as G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
Code used:
```
strings data.txt | grep ===
```





![Screenshot from 2023-10-21 03-17-49](https://github.com/PML696/overthewire_bandit_writeup_PML/assets/138509535/5441e9fd-96c4-4792-8a1b-19076e6bd8ea)



