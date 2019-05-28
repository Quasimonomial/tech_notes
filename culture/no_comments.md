## No Comments

This is closer to a personal opinion than true knowledge, but I'm against commenting code if it is at all possible to do so.

With comments, you quickly run into the [map-territory problem](https://en.wikipedia.org/wiki/Map%E2%80%93territory_relation), where your code is best explained by just reading the code.  There are three major pieces to understanding a function, which is the purpose of a function, its inner workings, and the intended behavior.  These are things that can be inferred and documented by the code itself.  The function title should tell  you what it does, the code itself should tell you how, and your tests should make clear the intent of your function.  Comments need to be kept up to date with a changing codebase.  It's easy to have comments become orphaned to old code they are describing; documentation is never quite as informative as to behavior as the code itself.

Eliminating comments and thus another moving part is something we can do by naming thing effectively, and is another reason why naming things properly is so important.  That's why variable names are so important, because they can quickly give context to desired behavior.  Using good describe / context / it should blocks in our tests help us describe what should be happening in the codebase itself, eliminating the need for closer documentation.

More thoughts for / against this point:
https://dev.to/codemouse92/to-comment-or-not-to-comment-3f7h
http://www.codeodor.com/index.cfm/2008/6/18/Common-Excuses-Used-To-Comment-Code-and-What-To-Do-About-Them/2293
https://blog.codinghorror.com/coding-without-comments/
