---
layout: post
title:  "Gitflow without gitflow commands"
date:   2020-08-20 16:24:08 +0200
categories: Git
---

Hello everyone,

Today I am going to explain how to use git for getting the same workflow as well as you get with gitflow plugin that you probably have installed. I think is better for every gitflow users having an idea about how it works, because if you know the gitflow commands but you had forgotten the raw commands, are you sure you still remember what the workflow in git should look like? To avoid the bad feelings you could start to feel just now, continue reading please:

First of all, open the terminal and go to your local repository folder. Once you are in, initialize repository:

gitflow command:

{% highlight terminal %}
git flow init
{% endhighlight %}

This command encourages users to create the base branches and select a prefix for all supporting branches. You could press enter for select all options as default name:

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

Just one line? Really?. Believe me, you don't need any more. This command creates .git file, also, it creates master branch, which is the main branch and the branch on you are just now.

But of course, both commands are not the same. If you want to recreate the gitflow workflow, you need to create the develop branch, which are both as well as:

{% highlight terminal %}
git branch develop
{% endhighlight %}

or:

{% highlight terminal %}
git checkout -b develop
{% endhighlight %}

with you changes from master to develop and selected this last as main branch. As a result of this:

{% highlight terminal %}
MacBook-Pro:examplerawgit ownuser$ git checkout -b develop
Switched to a new branch 'develop'
MacBook-Pro:examplerawgit ownuser$ 
{% endhighlight %}

For the rest of branches you could write the next sentence (`git status` is only for check our current branch):
{% highlight terminal %}
MacBook-Pro:examplerawgit ownuser$ git status
On branch develop

No commits yet

nothing to commit (create/copy files and use "git add" to track)
MacBook-Pro:examplerawgit ownuser$ git checkout -b feature/feature_branch
Switched to a new branch 'feature/feature_branch'
{% endhighlight %}

[to be continued...]

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
