salesforce-locus
================

When Locus Energy finally gives you your key/secret, they then make you get an Oauth token that is only good for an hour. Rather than setup a server that is constantly banging their API every hour of every day, this will only update the key when it's expired when you load the page.

Requirements:
-------------
* client_id and client_secret from Locus
* CSV file from Locus with all your customer data/IDs
* Custom Settings setup called LocusMonitorAPI with the following fields:
	* issued_at
	* expires_in
	* access_token
* Custom Object called Monitor Diagnostics (Monitor_Diagnostics__c)

This uses Salesforce's remoteFunction for the AJAX request. Doing this any other way (*cough*jQuery*cough*) results in an Access-Control-Allow-Origin error in Chrome. Trust me, I tried.

Good luck!
