Analytics
=========
##Introduction

Titanium allows you to fire five different types of analytics events
to our cloud services. The results from these events can be viewed
through our optional Analytics product (coming soon!).

##User

User events allow you to generate simple analytics events that just
require an event name. You can also pass in a JSON-based data object
to attach to this event.

	:::javascript
	// Fire a user event and pass along a little extra information.
	Titanium.Analytics.userEvent('my_event', {'login': true});

##Navigation

Navigation Events allow you to track transitions from one part of
your app to another.  You can pass in the from location, the to location,
the navigation event name, and an optional JSON data object.",

	:::javascript
	// Pass in from location, to location, event name and a JSON data object
	Titanium.Analytics.navEvent('home', 'edit_account', 'view_account',
		{'account_id':123});

##Settings

Settings Events allow you track a specific setting or configuration
in your application.  You can pass in the settings event name and an
optional JSON data object

	:::javascript
	// pass in a setting name and a JSON data object
	Titanium.Analytics.settingsEvent('volume', {'value':5});

##Timed

Timed Events allow you track how long an specific activity or task takes
to complete in your application.  You can pass in the timed event name,
start time, stop time, duration,  and an optional JSON data object. The
start time and end time values should be in miliseconds via the JavaScript
Date object.

	:::javascript
	// pass in a timed event name and a JSON data object
	var startTime = new Date();

	// Do some task like register for service and then do....
	var endTime = new Date();
	Titanium.Analytics.timedEvent('register', startTime, endTime, null, 
		{'email':'bob@aol.com'});