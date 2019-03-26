# Part Three: Implementation
## Chapter 14: Languages
* This chapter isn’t particularly helpful compared to the others; it contains notes on various programming languages and their strengths/weaknesses, but the discussion is about older languages and wasn't something I personally got as much value out of.

## Chapter 15: Tools
* This chapter has lots of detail on technical tools, but doesn’t have information on modern tools (talking about version control w/o [_git_](https://git-scm.com/))  and not the best place to learn about domain-specific tooling that is still used like [_make_](https://cmake.org/).  Would just read documentation and learn abut best practices elsewhere.

## Chapter 16: Reuse
* Don’t re-invent the wheel, use working software when known solutions exist
* Transparency is the key to reuse; if code isn’t transparent it won’t be reused
* Documentation always has the [map is not the territory](https://en.wikipedia.org/wiki/Map%E2%80%93territory_relation) problem — if the documentation gave every nuance of the code, you then you are just reading the code itself.
  * That means to use third party software, you really should have the source code, which means open source.  Otherwise you can't understand or modify internals
  * This can mean using open source software (rails gems, npm libraries)
* (A lot of this chapter is spent defending open source vs commercial code, don’t see a need to repeat it here.  Just read [this](https://www.gnu.org/philosophy/free-sw.html).)
* What qualifies as open source?
	* An unlimited right to copy be granted
	* An unlimited right to redistribute in unmodified form be granted
	* An unlimited right to modify for personal use be granted
