# Replication data and code for "From Programming to Products"

Nooney, Laine, Kevin Driscoll, and Kera Allen. “From Programming to Products: Softalk Magazine and the Rise of the Personal Computer User.” Information & Culture 55, no. 2 (June 18, 2020): 105–29. https://muse.jhu.edu/article/757558

# Data

Data files
- softalk_letters.1980-11_to_1984-08.tsv
- softalk_page_count.1980-1984.tsv
- letters_pages.1980-1982.tsv

# Code 

Requirements:
- Python 3.8.5
- Pandas 1.1.3
- Seaborn 0.11.0

# Variables in softalk_letters.1980-11_to_1984-08.tsv

full_letter_code
Each letter is assigned a unique identifier in the format YYYY.MM.NN. The YYYY and MM refer to the publication data of the issue and NN refers to the letter's position in the Open Discussion column. For example, "1982.10.36" refers to the thirty-sixth letter published in the October 1982 issue. (Caution: Microsoft Excel will attempt to interpret this column as a "date" by default. You will have to manually set it to "text".)

month, year, volume, issue
Publication information as it appeared in the magazine. Volume and Issue numbering began on September 1980. Each volume consisted of twelve issues.

page
The page on which the letter begins. Page numbers refer to the magazine's numbering, not the PDF copies.

author_id
Each letter writer is assigned a unique numeric ID.

name, title, affiliation
Letter's author transcribed from the original. Titles include professional position, academic credential, and military rank. Affiliation includes businesses, academic institutions, and government agencies.

gender, gender_guesser
Gender is a categorical variable. Values may be "Male", "Female", "Unknown", "Couple", "Organization", or "Group." We identified gender using clues in the letters themselves. All letters signed with a first initial were marked "Unknown." The gender_guesser column refers to the output of the “gender-guesser” Python package. Where the software disagreed with our original coding, we manually re-checked the gender. In comparison to other gender-inference software, gender-guesser performs especially well on names of European origin, which include a majority of the authors published in Softalk. See: Israel  Saeta  Pérez,  Gender-Guesser: Get the Gender from First Name, version 0.4.0, 2016, https://github.com/lead-ratings/gender-guesser/; Lucía Santamaría and Helena Mihaljević, “Comparison and Benchmark of Name-to-Gender Inference Services,” PeerJ Computer Science, July 16, 2008, e156. 

city, state, country, location, latitude, longitude, coordinates, geo_address
City, state, and country were transcribed from the pages of the magazine and automatically concatenated into the location column. We used the Microsoft Bing Maps API to produce the values for latitude, longitude, coordinates, and geo_address. 

editors_reply
Binary variable (0, 1) indicating whether or not the magazine's editors replied in print.

in_reply_to
If the writer explicitly referred to an earlier letter, the full_letter_code for the previous letter is listed here. If there is more than one reference, this column will include a list of letter codes separated by commas.

reference_topic, reference_year, reference_month
If the letter explicitly referred to an article from an earlier issue, we included as much information as possible here to trace the reference.

Announcement for Softalk readers, Arts and music, ..., Work or professional life
The remaining columns are binary variables (0, 1) referring to forty-nine non-exclusive thematic categories.
