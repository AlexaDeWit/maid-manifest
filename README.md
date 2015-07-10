# Maid Manifest

This readme is mainly to serve as a place for me to preserve and develop some of the ideas I am playing wtih.

## Project Purpose
The purpose of maid manifest is to provide an alternative to [semantic versioning](http://semver.org/). Many of the thoughts contained herein are inspired by this [article](http://mth.io/posts/annex/) by [Mark Hibberd](https://github.com/markhibberd).

### Intentions
The primary purpose is to replace version number data with a robust querying system using a collection of predicate functions. What this basically means is that you would now pin your project against a dependency on essentially any qualifiers you deem important. Some examples would be.

1. Checking the dependency's commit hash
2. Checking the build date of the dependency
3. Accepting only dependencies built from a specific version control branch. 
4. Checking against.... oh lord, a semantic version number. Backwards compatibility, what is this?
5. Checking against other meta-data provided by the library, such as:
* Builds tested against specific architectures/browsers/etc
* Whatever else you can think of. The user writes the predicate function, after all.


### Forseen Issues to address:

#####  Security patches.
Security patches often exist for very old project branches, in order to preserve old APIs. One way to solve this would obviously be with a semantic versioning predicate, but then that sort of defeats the purpose of this project to provide an alternative to semantic versioning.

Another route I can see for this is for library maintainers to take note of populate builds of their library and provide a branch for that point in time, which would then receive non-API-breaking security changes.

This would allow a user to then provide a branch predicate instead of a date predicate, or perhaps in addition to... I'm not your mother, do what you want.


### But where will we GET our dependencies FROM?
This project presupposed a common query interface between the main-manifest resolver, and a provider service which can also supply meta data. It is currently my intention to write an example service in tandum with this resolver. 

I also consider it extremely critical that maid-manifest not need to have a hard dependency upon a specific provider service. Something akin to a respository pattern here would be ideal in my eyes, where the manifest file will define the provider service function which will return the meta-data, and then that same manifest file will provide the user's dependency identifiers and dependency predicates.

Right now all of this is just sort of general ideas I am playing with and have written down simply to avoid forgetting them. I have much haskell and graph theory to learn before I begin actually developing this project.

Let us hope this becomes something more than a readme artifact.
