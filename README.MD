

# Why are we doing this?
Build locally
Build branches
Should be easy for anyone to change build definitions

https://nrkbeta.no/2015/11/10/how-i-learned-to-stop-worrying-and-love-the-ci-server/

# What is FAKE
http://forki.github.io/FAKE.Intro/#/

# Fake workshop - part 1
Goal: Getting used to the syntax

Use the machine and code from here (setup instructions in the README)
https://github.com/bjartwolf/Kebab/tree/xunit-2.10

```
git clone https://github.com/bjartwolf/Kebab
cd Kebab
git checkout xunit-2.10
cd Trees
build.cmd
```
or on linux/mac
```
build.sh
```

If everything is green it works.

## Exercices
Try to comment out everything after line 17 in Trees/build.fsx using 
``` 
(* 
   multiline commenting in F# 
*)
```


