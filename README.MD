# Why are we doing this? (Classroom, presentation)
https://nrkbeta.no/2015/11/10/how-i-learned-to-stop-worrying-and-love-the-ci-server/
- Build locally
- Build branches
- Should be easy for anyone to change build definitions

# What is FAKE (Classroom, presentation)
http://forki.github.io/FAKE.Intro/#/

# Fake workshop - part 1 (On own machines)
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

Or the little more fsharpy way of doing it
```
Seq.iter (fun f -> tracefn "Found a file %s" f) testReferences 
```

(Trace functions are documented here http://fsharp.github.io/FAKE/apidocs/fake-tracehelper.html)

## Try changing the patterns
Try to print out all the files in the subdir

## Filtering and adding files
The special syntax ++ and -- can be added after files included with !!
to include more files or filter out files. Try it! Maybe even on C: to find files, it should/could work.

## A better way than iterating
The things we get from !! ++ -- are called FileIncludes, and can be iterated over as we saw earlier as a sequence of strings (IEnumerable<string>) and a lot of FAKE functions take these.

```
Log "found a file" testReferences 
testReferences |> Log "found a file"
```

## Targets
Now try to wrap it up in proper targets and make a list of dependent targets (see how it is done in the already commented out code, define targets, define depedencies and define a default target)

# Real project things (Classroom, presentation)
## Show the builds we have
#Demonstration 
(Can't show here, internal code, but there is a demo in the blog)

# Real project hacking
Look, not dangerous, make a branch and do something to the build. For exapmle add FSharp linting to the backend build.
Or log something to teamcity. Or just break the build by throwing an exception (failwith "oops"), check it in and see what happens on teamcity.

If you want to try something useful try this:
https://github.com/fsprojects/FSharpLint
http://fsprojects.github.io//FAKE-Task.html

Or make a build definition from the not-migrated backend services.




