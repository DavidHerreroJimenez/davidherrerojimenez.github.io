---
layout: post
title:  "Gitflow without gitflow commands"
date:   2020-08-20 16:24:08 +0200
categories: Git
---

Hello everyone,

Today I am going to explain how to use git for getting the same workflow as well as you get with the Gitflow plugin that you probably have installed. I think is better for every Gitflow user to have an idea about how it works, because if you know the Gitflow commands but you had forgotten the raw commands, are you sure you still remember what the workflow in git should look like? To avoid the bad feelings you could start to feel just now, continue reading please:

First of all, open the terminal and go to your local repository folder. Once you are in, initialize the repository:

Gitflow command:

{% highlight terminal %}
git flow init
{% endhighlight %}

This command encourages users to create base branches and selects a prefix for all supporting branches. You could press enter for select all options as default name:

{% highlight terminal %}
MacBook-Pro:gitflowexample ownuser$ git flow init
Initialized empty Git repository in /Users/ownuser/gitflowexample/.git/
No branches exist yet. Base branches must be created now.
Branch name for production releases: [master] 
Branch name for "next release" development: [develop] 

How to name your supporting branch prefixes?
Feature branches? [feature/] 
Release branches? [release/] 
Hotfix branches? [hotfix/] 
Support branches? [support/] 
Version tag prefix? []     
MacBook-Pro:gitflowexample ownuser$
{% endhighlight %}

raw git:

{% highlight terminal %}
git init
{% endhighlight %}

As a result of git command, you are getting:

{% highlight terminal %}
Initialized empty Git repository in /Users/ownuser/example/.git/
{% endhighlight %}

Just one line? Really?. Believe me, you don't need it anymore. This command creates a .git file, also, it creates a master branch, which is the main branch and the branch on you are just now.

But of course, both commands are not the same. If you want to recreate the Gitflow workflow, you need to create the develop branch:

{% highlight terminal %}
git branch develop
{% endhighlight %}

or change from master to develop and select this last as the main branch:

{% highlight terminal %}
git checkout -b develop
{% endhighlight %}

As a result of this:

{% highlight terminal %}
MacBook-Pro:examplerawgit ownuser$ git checkout -b develop
Switched to a new branch 'develop'
MacBook-Pro:examplerawgit ownuser$ 
{% endhighlight %}

For the rest of the branches you could write the next sentence and create as branches as you want: (`git status` is only to check our current branch):

Gitflow:

{% highlight terminal %}

MacBook-Pro:gitflowexample ownuser$ git flow feature start feature_branch
Switched to a new branch 'feature/feature_branch'

Summary of actions:
A new branch 'feature/feature_branch' was created, based on 'develop'
You are now on branch 'feature/feature_branch'

Now, start committing on your feature. When done, use:

     git flow feature finish feature_branch

MacBook-Pro:gitflowexample ownuser$ 

{% endhighlight %}

raw git:

{% highlight terminal %}
MacBook-Pro:examplerawgit ownuser$ git status
On branch develop

No commits yet

nothing to commit (create/copy files and use "git add" to track)
MacBook-Pro:examplerawgit ownuser$ git checkout -b feature/feature_branch
Switched to a new branch 'feature/feature_branch'
{% endhighlight %}

Currently, we have created three branches, the main branch, as a master, a second main branch, which was named develop, and the third, as an example of the feature branch, as feature_branch. Well, at this point, you may not have noticed big differences between git, or raw git, and the Gitflow. In fact, the biggest difference between both is the workflow with the branches, you know, create a branch, merge, delete... Gitflow hides most of them, because this, you could not remember the original flow of git, Don't be afraid, continue reading...

Every branch you want to create in Gitflow, you only need the next expression, where you only need to change the type of branch, as a feature, release, hotfix... according to your necessities:

{% highlight terminal %}

MacBook-Pro:gitflowexample ownuser$ git flow feature start feature_branch

{% endhighlight %}

 and when you finished you only need to write something as:

{% highlight terminal %}

MacBook-Pro:gitflowexample ownuser$ git flow feature finish feature_branch

{% endhighlight %}

To merge the branch and delete you only need the same command but instead of start, you should type finish. Gitflow will do every work for you.

Nevertheless, you remember that raw git has too much verbosity, haven't you?

First of all, check if you are in the correct branch, that is, develop if you tend to create a feature branch or you pretend to launch a new version using a release branch. Rather than this, you need to check out the master branch, in case you have detected some mistakes in production, and then you will create a hotfix branch, from the master, of course.

{% highlight terminal %}

MacBook-Pro:rawgitexample ownuser$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
MacBook-Pro:rawgitexample ownuser$ 

{% endhighlight %}

If you need to change your current master, then you checkout:

{% highlight terminal %}

MacBook-Pro:rawgitexample ownuser$ git checkout develop
Switched to branch 'develop'
MacBook-Pro:rawgitexample ownuser$ 

{% endhighlight %}


Secondly, create a new branch, and, of course, check out another time:

{% highlight terminal %}

MacBook-Pro:rawgitexample ownuser$ git checkout -b feature/feature_branch
Switched to a new branch 'feature/feature_branch'
MacBook-Pro:rawgitexample ownuser$ 

{% endhighlight %}

Thirdly, add and commit your changes:

{% highlight terminal %}

MacBook-Pro:rawgitexample ownuser$ git add .
MacBook-Pro:rawgitexample ownuser$ git status
On branch feature/feature_branch
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
  new file:   newfile.txt

MacBook-Pro:rawgitexample ownuser$ git commit
[feature/feature_branch d133bfb] new file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 newfile.txt
MacBook-Pro:rawgitexample ownuser$ git checkout develop
Switched to branch 'develop'
MacBook-Pro:rawgitexample ownuser$

{% endhighlight %}

After work in some feature, you could merge the feature branch into develop branch:

{% highlight terminal %}

MacBook-Pro:rawgitexample ownuser$ git merge feature/feature_branch
Updating b1b023a..d133bfb
Fast-forward
 newfile.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 newfile.txt
MacBook-Pro:rawgitexample ownuser$

{% endhighlight %}

Finally, you need to repeat the same process but now for merge a release branch which you has created from develop branch, and you would merge with the master:

{% highlight terminal %}

MacBook-Pro:rawgitexample ownuser$ git status
On branch develop
nothing to commit, working tree clean
MacBook-Pro:rawgitexample ownuser$ git checkout -b release/0.0.1
Switched to a new branch 'release/0.0.1'
MacBook-Pro:rawgitexample ownuser$ git checkout master
Switched to branch 'master'
MacBook-Pro:rawgitexample ownuser$ git status
On branch master
nothing to commit, working tree clean
MacBook-Pro:rawgitexample ownuser$ git merge release/0.0.1
Updating b1b023a..d133bfb
Fast-forward
 newfile.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 newfile.txt
MacBook-Pro:rawgitexample ownuser$ git log --decorate --oneline
d133bfb (HEAD -> master, release/0.0.1, feature/feature_branch, develop) new file
b1b023a Initial commit
MacBook-Pro:rawgitexample ownuser$

{% endhighlight %}


<!--You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/-->
