Replication data and code for “From Programming to Products: *Softalk* Magazine and the Rise of the Personal Computer User”
===========================================================================================================================

Citation
========

Published paper
---------------

Nooney, Laine, Kevin Driscoll, and Kera Allen. “From Programming to
Products: *Softalk* Magazine and the Rise of the Personal Computer
User.” *Information & Culture* 55, no. 2 (June 18, 2020): 105–29.
https://muse.jhu.edu/article/757558

Data archive
------------

Driscoll, Kevin, Laine Nooney, and Kera Allen. “Replication Data for:
From Programming to Products: *Softalk* Magazine and the Rise of the
Personal Computer User,” December 15, 2020.
https://doi.org/10.18130/V3/IHCHYM.

Abstract
========

In the 1980s, the user emerged as a distinct class of personal computer
owner motivated by instrumental goals rather than the exploratory
pleasures of hackers and hobbyists. To understand the changing values
and concerns of microcomputer owners, we analyzed 1,285 reader letters
published in *Softalk* magazine between 1980 and 1984. During this
period, a preoccupation with programming was displaced by discussions of
software applications, products, and services. This transition
illustrates the separation of users from hobbyists, reflecting changes
in the software industry and attitudes toward amateurism,
professionalization, gender, and expertise.

Data and code
=============

Data
----

-  softalk_letters.1980-11_to_1984-08.tsv
-  softalk_page_count.1980-1984.tsv
-  letters_pages.1980-1982.tsv

Code
----

-  Replication for From Programming to Products.ipynb

Environment
-----------

-  Python 3.8.5
-  IPython 7.19.0
-  Jupyter Notebook 6.1.4
-  Pandas 1.1.3
-  Seaborn 0.11.0

Variables in softalk_letters.1980-11_to_1984-08.tsv
===================================================

full_letter_code
----------------

Each letter is assigned a unique identifier in the format YYYY.MM.NN.
The YYYY and MM refer to the publication data of the issue and NN refers
to the letter’s position in the Open Discussion column. For example,
“1982.10.36” refers to the thirty-sixth letter published in the October
1982 issue. (Caution: Microsoft Excel will attempt to interpret this
column as a “date” by default. You will have to manually set it to
“text”.)

month, year, volume, issue
--------------------------

Publication information as it appeared in the magazine. Volume and Issue
numbering began on September 1980. Each volume consisted of twelve
issues.

page
----

The page on which the letter begins. Page numbers refer to the
magazine’s numbering, not the PDF copies.

author_id
---------

Each letter writer is assigned a unique numeric ID.

name, title, affiliation
------------------------

Letter’s author transcribed from the original. Titles include
professional position, academic credential, and military rank.
Affiliation includes businesses, academic institutions, and government
agencies.

gender, gender_guesser
----------------------

Gender is a categorical variable. Values may be “Male”, “Female”,
“Unknown”, “Couple”, “Organization”, or “Group.” All letters signed with
a first initial were marked “Unknown.” We first identified the gender of
each writer using clues in the letters themselves. Next, we passed each
name to the “gender-guesser” Python package. Where the software
disagreed with our original coding, we manually re-checked the letter. A
human coder made the final decision. (In comparison to other
gender-inference software, gender-guesser performs especially well on
names of European origin, which include a majority of the authors
published in *Softalk*. See: Israel Saeta Pérez, Gender-Guesser: Get the
Gender from First Name, version 0.4.0, 2016,
https://github.com/lead-ratings/gender-guesser/; Lucía Santamaría and
Helena Mihaljević, “Comparison and Benchmark of Name-to-Gender Inference
Services,” PeerJ Computer Science, July 16, 2008, e156.)

city, state, country, location, latitude, longitude, coordinates, geo_address
-----------------------------------------------------------------------------

City, state, and country were transcribed from the pages of the magazine
and automatically concatenated into the location column. We used the
Microsoft Bing Maps API to produce the values for latitude, longitude,
coordinates, and geo_address.

editors_reply
-------------

Binary variable (0, 1) indicating whether or not the magazine’s editors
replied in print.

in_reply_to
-----------

If the writer explicitly referred to an earlier letter, the
full_letter_code for the previous letter is listed here. If there is
more than one reference, this column will include a list of letter codes
separated by commas.

reference_topic, reference_year, reference_month
------------------------------------------------

If the letter explicitly referred to an article from an earlier issue,
we included as much information as possible here to trace the reference.

“Announcement for Softalk readers”, “Arts and music”, …, “Work or professional life”
------------------------------------------------------------------------------------

The remaining columns are binary variables (0, 1) referring to
forty-nine non-exclusive thematic categories. Refer to the coding form
for a complete list.

Coding form
===========

Name (Required)
---------------

Transcribe the writer’s name however it was printed in Softalk, e.g.,
“John Smith” or “Dr. Roland S. Leong, D.M.D.”

Title
-----

Some letter writers list a professional title such as “Branch Manager”
or “CEO”

Affiliation
-----------

Gender (Required)
-----------------

-  Female
-  Male
-  Other:

City (Required)
---------------

State (Required)
----------------

Use the two-letter abbreviation for US states. Enter XX for unknown.

Country (Required)
------------------

Enter XX for unknown.

Month (Required)
----------------

Year (Required)
---------------

Letter Number (Required)
------------------------

The first letter printed in the Open Discussion section is “1”, the next
is “2”, and so on.

Page Number (Required)
----------------------

If the letter spans multiple pages, list just the first page number.

Themes (implicit or explicit, check all that apply)
---------------------------------------------------

-  Announcement for Softalk readers
-  Arts and music
-  BBS modems telecommunications
-  Club or user group
-  Commentary or opinion
-  Contests
-  Cooking or Diet
-  Copyright
-  Correction to an article
-  Criticism of Softalk
-  Databases
-  Disability
-  Domestic themes
-  Education or Teaching
-  Ergonomics
-  Family or children or spouse
-  Gaming
-  Gender Themes
-  Genealogy
-  HiRes Graphics
-  Identifies as novice
-  Includes source code
-  Library
-  Mail Order
-  Notes their own age
-  Personal finance
-  Piracy
-  Praise for Softalk
-  Printer
-  Product or service recommendation or warning
-  Programming
-  Psychology or Mental Health
-  Publishing House
-  Quality or Accountability Issues
-  Request for help or assistance or advice
-  Request to Softalk Editors
-  Romance
-  Royalties
-  Security or Encryption
-  Softporn or Erotic Software
-  Software Distributor or Distribution
-  Software related to cooking
-  Store or Retailers
-  Subscription Issues
-  Technical tip or howto
-  Voice Recognition
-  Warranties
-  Word Processing
-  Work or professional life
-  Other themes?

Reference to a previous article?
--------------------------------

-  Reference: Title or topic
-  Reference: Month
-  Reference: Year

Reply to another Letter?
------------------------

Use the following format year.month.letter or “1982.07.12”. If you don’t
know any of the three parts, use question marks and we can fix it later,
e.g., “1982.07.??”

Did the Editors reply in-line? (Required)
-----------------------------------------

Editor replies are typically set in italic type just below the original
letter

-  Yes, the editors responded
-  No, they did not

Notes about the editors’ reply
------------------------------

Notes
-----
