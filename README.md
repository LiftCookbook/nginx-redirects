# Redirects for the Lift Cookbook


## Problem

At first the Cookbook was published at URLs like _/Downloading and running Lift.html_.  

Then it was published at URLs like _/#DownloadAndRun_.  

Now it runs over at O'Reilly's Atlas server, with URLs like _ch01.html#DownloadAndRun_.

We want to keep the URLs working as best we can.


## Solution

* A set of Nginx redirects for the first version of the site.

* A single HTML page with JavaScript to pick out the client-site anchor references and redirect on based on that.

The NGIX redirects are in _nginx.conf_.  That's a vanilla starting config, with changes between `# Re-writes from ...` and `# End of cookbook rewrites`.

The JavaScript is in _index.html_.







