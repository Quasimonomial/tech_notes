# Art of Unix Programming

## Introduction

[The Art of Unix programming](http://www.catb.org/~esr/writings/taoup/html/) is a book I picked up about a year ago from the advice of some forgotten forum post.  I hadn't gotten around to it for a while, and in the beginning of the year I made my way through it.  I've take copious notes, which you can find here.

A quick summary of what this book is about, and keep in mind it came out in about 2003.  It describes a Unix-centric philosophy of coding.  The book is 500+ pages of coding opinions.  Rather than telling you how to code, the book makes an attempt to describe what good code _is_.  This book is opinionated; it has thoughts on what makes code beautiful, and I don't think what they have to say is always universal.

But, on the other hand, looking back at this book over a decade later, a lot of the core ideas of the book don't seem as radical as they may have then.  A lot of the ideas of the book are things that you find in Agile Programming, Extreme Programming, and modern paradigms that Silicon Valley has sine adopted.  A lot of ideas, especially in the introductory chapters, are really important, and I would really recommend reading this book for any new coder that has learned a language fully and has built a couple of project.


Some quick takeaways, and themes of the book:
* Parts One and Two are the most useful; they deal with systems design and thinking.  Parts Three and Four are mostly worth reading if you haven't come around to open source, most of the ideas they are pushing for have already been widely accepted.
* Build systems that are as simple to reason about as possible to make them more maintainable
* Humans make lots of errors, so make design and process decisions that minimize the negative business impacts of those errors
* Bugs in software is proportional to total lines of code, agnostic to programming language.  This means that writing as few lines as possible allows for robust software
