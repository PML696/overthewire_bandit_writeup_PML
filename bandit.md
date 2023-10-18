#### Writeup on https://overthewire.org/wargames/bandit/

#### Level 0
```
It was a great challenge to find and learn about ssh and how to access it etc. But it was fun. Now moving forward!
It was related to logging in by the way.

```

#### Level 0 -> Level 1
```
Done with level 1. I couldnt understand how to solve it at first then i learnt by referring to google.
I then used cat readme to access the readme library and got the password and then moved forward.
Password:NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
#### Level 1 -> Level 2
```
tried cat - but it doesnt work it started lagging.
Now i tried cat ./- after i looked it up how to represent a library since it cant detect a - on its own
so the password is rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
#### Level 2 -> Level 3
```
didnt get it becasue i started with il and then home directory opened so couldnt find spaces in this filename there so then I realised i had to exit and then again i logged in and then i tried cat spaces\ in\ this\ filename it worked
password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
#### Level 3 -> Level 4
```
tried find cat inhere but didnt work
so next tried find inhere
got the hidden directory which was inhere/.hidden
the password is 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```
#### Level 4 -> Level 5
```
first tried the same thing
I put find in here
 then i got 9 files like inhere/-file01 and then i started acessing them one by one and got random characters in each and then at the last i got the password at inhere/-file07
the password was lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
#### Level 5 -> Level 6
```
so i continued with the same procedure i.e. find inhere but then i got many files
so now i had to find that one file which satisfied the following characteristics
human-readable
1033 bytes in size
not executable
 so I referred chatgpt to give me a code to filter out everything and get me that one file which satisfied the following characteristics
the code was
find inhere -type f -size 1033c -not -executable -exec file {} \; | grep "text"
then i got the unique required file that was inhere/maybehere07/.file2
then i just accessed the data within that file with cat inhere/maybehere07/.file2
and i got the password P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
#### Level 6 -> Level 7
```



