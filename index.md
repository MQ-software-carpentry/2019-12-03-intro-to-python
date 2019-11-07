---
layout: workshop               # DON'T CHANGE THIS.
venue: "Macquarie University"  # brief name of host site without address (e.g., "Euphoric State University")
address: "Active Learning Space, 14SCO 163 (E7B), Macquarie University, Sydney NSW 2122"      
                               # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "au"                  # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"                 # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "-33.774056"         # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "151.114766"        # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "3-4 Dec 2019"      # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 4:30 pm" # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-12-03          # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2019-12-04            # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Richard Miller", "James Tocknell", "Nishen Naidoo"] 
                               # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Fergus Harrison", "Rhiannon Rasins", "Lei Han"]
                               # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["richard.miller@mq.edu.au", "odette.subijano@mq.edu.au"]   
                               # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:           # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite: "80428027395"      # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---


{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION
{% endcomment %}

{% include swc/intro.html %}

{% comment %}
AUDIENCE
{% endcomment %}

{% include swc/who.html %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latitude and page.longitude %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants will need to bring a laptop with a
  macOS, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on.
  They will need an internet browser installed (Chrome recommended).
  Participants must also sign-up for a <a href="https://github.com/">GitHub</a> account if they don't already have one.
</p>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<p id="code-of-conduct">
<strong>Code of Conduct:</strong>
Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>


{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %} 
SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>
{% include swc/schedule.html %}

{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

{% comment %}
SYLLABUS

{% endcomment %}
<h2 id="syllabus">Syllabus</h2>
{% include swc/syllabus.html %}

<hr/>

{% comment %}
SETUP

{% endcomment %}

<h2 id="setup">Pre Workshop Setup</h2>
<p>
  Before attending the workshop, you will need to ensure you have:
  <ul>
    <li> A macOS, Windows or Linux laptop for use during the workshop. </li>
    <li> Internet access from your device - Macquarie OneNet Wifi and eduRoam are available in the venue. </li>
    <li> A <a href="https://github.com">GitHub account</a> - sign up is free. </li>
    <li> Completed the: <a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a> </li>
  </ul>
</p>


<p>
All the workshop materials are available in the follow in GitHub Repository:
<ul>
  <img src="https://img.icons8.com/color/48/000000/git.png">
  <a href="https://github.com/MQ-software-carpentry/2019-07-24-intro-to-python-workshop">https://github.com/MQ-software-carpentry/2019-07-24-intro-to-python-workshop</a> (this is the version from our previous workshop - but the new one will be similar)
</ul>

</p>

<br/>
<br/>
<br/>
<br/>
