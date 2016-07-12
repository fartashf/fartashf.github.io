---
layout: post
title: Git commit old files with their timestamp
comments: True
---

I had a set of files that I wanted to put them in a git repository in a way 
  that would preserve their time-stamp.  The only thing that mattered to me was 
  their last modification date because I would usually write them once and 
  never change them afterwards.  Here is one line of Bash that does the job.  

~~~ bash
find -name '*.prototxt' -exec stat --printf "%Y %n\n" '{}' \; | sort |\
awk '{print "git commit --date=\"~date -Ins --date=@"$1"~\" "$2" -m\""$2"\""}'
|\
while read line; do eval $line; done
~~~

A couple of things that made it difficult to write this:

- I could do this in a matter of seconds if I wanted to use VIM!
- git accepts a limited set of formats for --date.
- eval was needed to handle the evaluation of ~~ and other stuff.
- Some considerations are made to keep the order of commits
chronologically correct.
- I was used to enclosing the argument to -exec by single quotes but
maybe the style has changed or it's been a long time I haven't used
it!
- I had to git add all the files prior to doing this
