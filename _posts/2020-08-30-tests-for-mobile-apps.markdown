---
layout: post
title:  "Tests for mobile apps"
date:   2020-08-30 20:04:00 +0200
categories: Tests
---

## Local unit tests (Located at module-name/src/test/java/.)

1. JUnit test (when your tests have no Android framework dependencies)

  1. runs on the local JVM

  2. instrumented test that runs on a device



2. test frameworks: Mockito (when you can mock the Android framework dependencies)
  to test Android API calls in your local unit tests

## Instrumented tests (Located at module-name/src/androidTest/java/.)

3. Espresso
  to exercise user interaction in your instrumented tests

  1. run on a hardware device or emulator.

  2.  generate Espresso tests automatically using Espresso Test Recorder.







[Under construction]



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
