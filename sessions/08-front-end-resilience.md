# Front End Resilience
Function in a hostile environment. The browser is "hostile" -- differing capabilities, settings, network conditions, etc.

## How Can Systems Fail?
* 3rd party availability
* Internal bugs
* The network
* User's privilege to alter experience (content blocker, rewriter, etc.)

## How Do We Handle It?
* Design for failure!

## Designing for Failure
* Prioritize critical parts of the page
* Make errors a first class citizen; design for the failure paths
  * Something broke; should I tell the user? Could they do anything about it?
* Report your errors back home

## Mitigate Risk
* Build in redundancy
* Serve stale content
  * With CDNs/cache, only expire after TTL when source is still available
  * Service worker can add another "local" CDN/cache to ensure that customized error behavior occurs
