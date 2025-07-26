This is the web scraping team's work for the Civic Tech DC hackathon.

We each tried different approaches to scraping the SEC and FEC websites
- File sec_web_scraper.py is a scraper built with AI LLM
- File FCCScraping.py is an API interpreter using the FCC API 
- File sec.py is a basic file where you can type in the sec rule comment page and it will output the docket ID and description. via command python3 `sec.py [url]`


The use of these files for mirrulations.
If you're using sec.py, you can begin by scraping initial data and saving it to the Mirrulations dataset as raw data. When you run the url command at scale, you can create a docket record. Then, by running a looped scrape on the file_links array, you can collect all the raw comments, including HTML, PDF, and other formats, for a specific SEC rule. In short, this script is a foundational tool for helping Mirrulations gather and organize data related to SEC comments.

