##Learn vue.js

Can use with CDN without installing but not a good approach.
Now install node js https://nodejs.org/en/download/
npm is installed by default.
Install vue 
```
npm install -g @vue/cli
```
Now run in vue tut folder
```
vue create blog
```
Access locally 
```
Microsoft Windows [Version 10.0.19045.3803]
(c) Microsoft Corporation. All rights reserved.

C:\Users\User\Desktop\vue tut>vue create blog
?  Your connection to the default npm registry seems to be slow.
   Use https://registry.npmmirror.com for faster installation? Yes


Vue CLI v5.0.8
? Please pick a preset: Default ([Vue 3] babel, eslint)


Vue CLI v5.0.8
✨  Creating project in C:\Users\User\Desktop\vue tut\blog.
⚙️  Installing CLI plugins. This might take a while...


added 866 packages in 2m
🚀  Invoking generators...
📦  Installing additional dependencies...


added 103 packages in 19s
⚓  Running completion hooks...

📄  Generating README.md...

🎉  Successfully created project blog.
👉  Get started with the following commands:

 $ cd blog
 $ npm run serve


C:\Users\User\Desktop\vue tut>code .
'code' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\User\Desktop\vue tut>cd blog

C:\Users\User\Desktop\vue tut\blog>code .
'code' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\User\Desktop\vue tut\blog>sudo code .
'sudo' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\User\Desktop\vue tut\blog>gsudo code .
'gsudo' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\User\Desktop\vue tut\blog>runas code .
RUNAS USAGE:

RUNAS [ [/noprofile | /profile] [/env] [/savecred | /netonly] ]
        /user:<UserName> program

RUNAS [ [/noprofile | /profile] [/env] [/savecred] ]
        /smartcard [/user:<UserName>] program

RUNAS /trustlevel:<TrustLevel> program

   /noprofile        specifies that the user's profile should not be loaded.
                     This causes the application to load more quickly, but
                     can cause some applications to malfunction.
   /profile          specifies that the user's profile should be loaded.
                     This is the default.
   /env              to use current environment instead of user's.
   /netonly          use if the credentials specified are for remote
                     access only.
   /savecred         to use credentials previously saved by the user.
   /smartcard        use if the credentials are to be supplied from a
                     smartcard.
   /user             <UserName> should be in form USER@DOMAIN or DOMAIN\USER
   /showtrustlevels  displays the trust levels that can be used as arguments
                     to /trustlevel.
   /trustlevel       <Level> should be one of levels enumerated
                     in /showtrustlevels.
   program         command line for EXE.  See below for examples

Examples:
> runas /noprofile /user:mymachine\administrator cmd
> runas /profile /env /user:mydomain\admin "mmc %windir%\system32\dsa.msc"
> runas /env /user:user@domain.microsoft.com "notepad \"my file.txt\""

NOTE:  Enter user's password only when prompted.
NOTE:  /profile is not compatible with /netonly.
NOTE:  /savecred is not compatible with /smartcard.



 DONE  Compiled successfully in 8472ms                                                                        3:21:46 pm


  App running at:
  - Local:   http://localhost:8080/
  - Network: http://172.16.11.112:8080/

  Note that the development build is not optimized.
  To create a production build, run npm run build.

```

