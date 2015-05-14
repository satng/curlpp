# Code History #

## Current branch (0.5.x and newer) ##

This version is a complete re-factorization of cURLpp against 0.3.x and older versions. This re-factorization was made for the following reasons:
  * cURLpp was difficult to maintain.
  * cURLpp wasn't flexible.

Those two points are in fact related. cURLpp was difficult to maintain because each libcURL's option change needed a change in cURLpp; the design didn't allow those changes to be automatically taken in charge. Because I don't monitor libcURL project carefully, those changes were only applied 2-3 months after the release. It wasn't flexible because it didn't allowed the user to change cURLpp's behavior without risking to break previously made applications.

But in fact, the real problem is that I'm a fat bastard who DOES read feature requests, but does not necessarily program them (You can send your complains to my university/job/girlfriend). So, this design is, in fact, "Ze" one that is compatible with my laziness.

Seriously, here's the advantages of this new design:
  * Allow you to change cURLpp's C++ wrapping behavior, without requiring its recompilation.
  * Allow you to retrieve the option values already set on the handle.

For more details, see the guide. Note that, as you probably deduced, this version is NOT compatible against 0.3.x and older versions.

## 0.3.x and older ##

This version is designed over the project began by Eric Lavigne. It's no longer active.