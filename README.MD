

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
# Start fresh
Try to comment out everything after line 17 in Trees/build.fsx using 
``` 
(* 
   multiline commenting in F# 
*)
```

Running build.cmd now doesn't do that much anymore.

## Finding files
```
for ref in testReferences do tracefn "Found a file %s" ref
```

(Trace functions are documented here http://fsharp.github.io/FAKE/apidocs/fake-tracehelper.html)

## Try changing the patterns
Try to print out all the files in the subdir

## Filtering and adding files
The special syntax ++ and -- can be added after files included with !!
to include more files or filter out files. Try it! Maybe even on C: to find files, it should/could work.










