This is a replacement javascript file for Triple Seat reservation system. To use, place triple-seat.js on your server. Then replace the script element tag that Triple Seat provided, using triple-seat.js as the source, and copying the query string (the part of the src attribute after the ? character) to the new script tag. So instead of this

<code><script src="https://api.tripleseat.com/v1/leads/ts_script.js?lead_form_id=foo&public_key=bar"></script></code>

use

<code><script id="triple-seat-script" src="triple-seat.js?lead_form_id=foo&amp;public_key=bar"></script></code>

Note that "foo" and "bar" in the example url above must be replaced with the values from the script element you were using. Also, make sure to include the id attribute on the tag; the form will not load without it.

<h2>Why replace the javascript file that Triple Seat provides?</h2>

The form that Triple Seat provides has numerous problems that this script tries to rectify:
* it uses html5 input types (time, date, and number) instead of generic text inputs
* it only loads jquery datepicker on clients that don't support native date inputs; that means it doesn't load jquery-ui resources unless they're actually needed, decreasing payload and improving speed
* it uses native time inputs in supporting browsers; for those that don't, it uses simple select elements instead of timepicker inputs
* it uses its own functions for client-side validation instead of native html5 form constraints like the "required" attribute
* it uses a mere 50 lines of css instead of the 231 in Triple Seat's form, and looks better
* it does not rely on table markup for presentation
* it is adaptable to small devices "out of the box", no additional code needed
* it allows some customization via simple configuration variables to set minimum time, date, etc.
