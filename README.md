# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```
### Display the content of the files
cat < file1
## OUTPUT
![Alt text](img/os1.png)



cat < file2
## OUTPUT
![Alt text](img/os2.png)

# Comparing Files
cmp file1 file2
## OUTPUT
![Alt text](img/os3.png)
 
comm file1 file2
 ## OUTPUT
![Alt text](img/os4.png)
 
diff file1 file2
## OUTPUT
![Alt text](img/os5.png)

#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```






cut -d "|" -f 2 file22
## OUTPUT
![Alt text](img/os6.png)

cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT
![Alt text](img/os8.png)


grep hello newfile 
## OUTPUT
![Alt text](img/os9.png)



grep -v hello newfile 
## OUTPUT
![Alt text](img/os10.png)


cat newfile | grep -i "hello"
## OUTPUT
![Alt text](img/os11.png)



cat newfile | grep -i -c "hello"
## OUTPUT

![Alt text](img/os11......png)


grep -R ubuntu /etc
## OUTPUT
![Alt text](img/os12.png)


grep -w -n world newfile   
## OUTPUT
![Alt text](img/os13.png)


cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT
![Alt text](img/os15.png)



egrep -w '(H|h)ello' newfile 
## OUTPUT
![Alt text](img/OS16.......png)


egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
![Alt text](img/OS17.....png)



egrep '(^hello)' newfile 
## OUTPUT
![Alt text](img/os17.png)



egrep '(world$)' newfile 
## OUTPUT
![Alt text](img/os18.png)




egrep '((W|w)orld$)' newfile 
## OUTPUT
![Alt text](img/os19.png)


egrep '[1-9]' newfile 
## OUTPUT
![Alt text](img/OS19......png)


egrep l{2} newfile
## OUTPUT
![Alt text](img/os19.png)


egrep 's{1,2}' newfile
## OUTPUT 

![Alt text](img/os21.png)

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
![Alt text](img/os22.png)



sed -n -e '$p' file23
## OUTPUT
![Alt text](img/os22.png)


sed  -e 's/Ram/Sita/' file23
## OUTPUT
![Alt text](img/os26.png)



sed  -e '2s/Ram/Sita/' file23
## OUTPUT
![Alt text](img/os27.png)


sed  '/tom/s/5000/6000/' file23
## OUTPUT
![Alt text](img/os28.png)


sed -n -e '1,5p' file23
## OUTPUT
![Alt text](img/os29.png)


sed -n -e '2,/Joe/p' file23
## OUTPUT
![Alt text](img/os30.png)



sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
![Alt text](img/os31.png)


seq 10 
## OUTPUT
![Alt text](img/os32.png)


seq 10 | sed -n '4,6p'
## OUTPUT
![Alt text](img/os33.png)



seq 10 | sed -n '2,~4p'
## OUTPUT
![Alt text](img/os34.png)



seq 3 | sed '2a hello'
## OUTPUT
![Alt text](img/os35.png)



seq 2 | sed '2i hello'
## OUTPUT
![Alt text](img/os36.png)


seq 10 | sed '2,9c hello'
## OUTPUT
![Alt text](img/os37.png)

sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
![Alt text](img/os38.png)

sed -n '2,4{s/$/*/;p}' file23
## OUTPUT
![Alt text](img/os39.png)


#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
![Alt text](img/os40.png)


cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT
![Alt text](img/os41.png)



#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
 ![Alt text](img/os42.png)

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
![Alt text](img/os44.png)

 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
![Alt text](img/os45.png)


#Backup commands
tar -cvf backup.tar *
## OUTPUT
![Alt text](img/os46.png)


mkdir backupdir
 
mv backup.tar backupdir

cd backupdir
 
tar -tvf backup.tar
## OUTPUT
![Alt text](img/os47.png)


tar -xvf backup.tar
## OUTPUT

gzip backup.tar

ls .gz
## OUTPUT
 
gunzip backup.tar.gz
## OUTPUT

 
# Shell Script
```

# RESULT:
The Commands are executed successfully.
