This is a replacement javascript file for Triple Seat reservation system.

The form that Triple Seat provides has numerous problems:
* it uses generic text inputs where more specific input types are warranted
* it only loads jquery datepicker on clients that don't support native date inputs; that means it doesn't load jquery-ui resources unless they're actually needed, decreasing payload and improving speed
* it uses native time inputs in supporting browsers; for those that don't, it uses simple select elements instead of timepicker inputs
* it uses its own functions for client-side validation instead of native html5 form constraints like the "required" attribute
* it uses a mere 50 lines of css instead of the 231 in Triple Seat's form, and looks better
* it does not rely on table markup for presentation
* it is adaptable to small devices "out of the box", no additional code needed
* it allows some customization via simple configuration variables to set minimum time, date, etc.

To use, download the script and place it on your server. Then change the base url and path of the Triple Seat provided script to point to the local one, adding the query string to end. So instead of

<code><script src="https://api.tripleseat.com/v1/leads/ts_script.js?lead_form_id=foo&public_key=bar"></script></code>

use

<code><script id="triple-seat-script" src="/scripts/triple-seat.js?lead_form_id=foo&amp;public_key=bar"></script></code>

Make sure to include the id attribute on the tag; the form will not load without it.
