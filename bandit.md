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

Didnt get it becasue i started with il and then home directory opened so couldnt find spaces in this filename there so then I realised i had to exit and then again i logged in and then i tried cat spaces\ in\ this\ filename it worked
password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG


#### Level 3 -> Level 4

tried find cat inhere but didnt work
so next tried find inhere
got the hidden directory which was inhere/.hidden
the password is 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe


#### Level 4 -> Level 5

first tried the same thing
I put find in here
 then i got 9 files like inhere/-file01 and then i started acessing them one by one and got random characters in each and then at the last i got the password at inhere/-file07
the password was lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR


#### Level 5 -> Level 6

so i continued with the same procedure i.e. find inhere but then i got many files
so now i had to find that one file which satisfied the following characteristics
human-readable
1033 bytes in size
not executable
 so I referred chatgpt to give me a code to filter out everything and get me that one file which satisfied the following characteristics
the code was find /path/to/directory -type f -size 1033c -not -executable -exec file {} \; | grep "text"
here i just had to replace /path/to/directory with inhere so the final code is given below
find inhere -type f -size 1033c -not -executable -exec file {} \; | grep "text"
then i got the unique required file that was inhere/maybehere07/.file2
then i just accessed the data within that file with cat inhere/maybehere07/.file2
and i got the password P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU


#### Level 6 -> Level 7

So now what i did was i got a code by referring to chatgpt based on the characteristics given in the question i.e. find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
and when i put this i got a file /var/lib/dpkg/info/bandit7.password
so then i accessed this file through cat /var/lib/dpkg/info/bandit7.password
and i got the password as z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S


#### Level 7 -> Level 8





