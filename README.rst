===================================
University of York Timetable Parser
===================================

This is a parser for the personalised timetables supplied by the University of York e:Vision system.  
Converts a saved HTML file to iCalendar (``.ics``) format, which can then be imported into any other 
calendar application that supports it.

A configuration file, using the JSON syntax, can define abbreviations for module names, term dates, 
etc. - look at the supplied ``config.json`` for guidance.  For basic usage help, run ``./yttp.py 
--help``.

The parser currently recognises 3 types of events: lectures, seminars and practicals.  The 
``--split`` option can be used to write a separate calendar for each type of event.

NOTE:
-----

For yttp to be able to properly extract event type information, the type_offset parameter in 
config.json may need adjusting.  This is due to differences between lesson ID formats.

To work out the number, look at a lesson ID on the timetable, find the number of the character 
that signifies the lesson type (generally E, P or L just before the group number), then subtract 
1.  For first-year Computer Science, the offset is 9 (the default in config.json), though 
other-year CS student timetables are known to require a different offset (try 7).

The base config.json provided contains abbreviations for 1st year Computer Science, as well as 
some 4th/5th-year modules.

Dependencies:
-------------

* Python 2.6
* The following Python modules:
    
  * icalendar
  * beautifulsoup
  * pytz

Credits:
--------

Code -> Alan Briolat
A small bit of hacking for 1st-year use -> Matt Windsor
