# Redirects for the Lift Cookbook


## Problem

At first the Cookbook was published at URLs like _/Downloading and running Lift.html_.  

Then it was published at URLs like _/#DownloadAndRun_.  

Now it runs over at O'Reilly's Atlas server, with URLs like _ch01.html#DownloadAndRun_.

We want to keep the URLs working as best we can.


## Solution

* A set of nginx redirects for the first version of the site.

* A single HTML page with JavaScript to pick out the client-site anchor references and redirect based on the anchor.

The nginx redirects are in [nginx.conf](https://github.com/LiftCookbook/nginx-redirects/blob/master/nginx.conf#L48), between `# Re-writes from ...` and `# End of cookbook rewrites`.  That file is the default nginx config which serves up an _index.html_ page.

The JavaScript is in [index.html](https://github.com/LiftCookbook/nginx-redirects/blob/master/index.html).


## Tests

* [http://cookbook.liftweb.net/Downloading and running Lift.html](http://cookbook.liftweb.net/Downloading and running Lift.html) should redirect to [http://chimera.labs.oreilly.com/books/1234000000030/ch01.html#_problem](http://chimera.labs.oreilly.com/books/1234000000030/ch01.html#_problem) ultimately.

* [http://cookbook.liftweb.net//#DownloadAndRun](http://cookbook.liftweb.net//#DownloadAndRun) should redirect to the same page again. 

And the following should all end up at the home page ([http://chimera.labs.oreilly.com/books/1234000000030/index.html](http://chimera.labs.oreilly.com/books/1234000000030/index.html)):

* [http://cookbook.liftweb.net](http://cookbook.liftweb.net) 
* [http://cookbook.liftweb.net/wibble](http://cookbook.liftweb.net/wibble)
* [http://cookbook.liftweb.net/#wibble](http://cookbook.liftweb.net/#wibble)



