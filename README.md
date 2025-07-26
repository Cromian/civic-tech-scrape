This is the web scraping team's work for the Civic Tech DC hackathon.

We each tried different approaches to scraping the SEC and FEC websites
- File sec_web_scraper.py is a scraper built with AI LLM
- File FCCScraping.py is an API interpreter using the FCC API 
- File sec.py is a basic file where you can type in the sec rule comment page and it will output the docket ID and description. via command python3 `sec.py [url]`


# FCCScraping.py
* Given a range of proceeding creation dates, pull all proceedings within that range to process
* Obtain the Docket # and # of Filings under each proceeding
* Iterate through each of the Filings within each proceeding and obtain:
  * Every document link attached to a Filing
  * The comment text associated with the Filing

# Sec.py
Scrape SEC rule comments - https://github.com/Cromian/sec-comments
## The use of these files for mirrulations.

If you're using sec.py, you can begin by scraping initial data and saving it to the Mirrulations dataset as raw data. When you run the url command at scale, you can create a docket record. Then, by running a looped scrape on the file_links array, you can collect all the raw comments, including HTML, PDF, and other formats, for a specific SEC rule. In short, this script is a foundational tool for helping Mirrulations gather and organize data related to SEC comments.

File sec.py is a basic file where you can type in the sec rule comment page and it will output the docket ID and description. via command python3 sec.py [url]

## Full list can be found: 
- https://www.sec.gov/rules-regulations/rulemaking-activity
- Single Rule: https://www.sec.gov/rules-regulations/2025/06/s7-11-23#34-103320final
- comments for single rule: https://www.sec.gov/comments/s7-11-23/s71123.htm

## How to use:
Run the command `sec.py [url]`

`sec.py https://www.sec.gov/comments/s7-11-23/s71123.htm`
## Sample Output
```[
  [
    "id:",
    "s7-11-23"
  ],
  [
    "title:",
    "Comments on Daily Computation of Customer and Broker-Dealer Reserve Requirements under the Broker-Dealer Customer Protection Rule"
  ],
  [
    "links:",
    [
      "#meetings",
      "/comments/s7-11-23/s71123-typea.htm",
      "/comments/s7-11-23/s71123-typeb.htm",
      "/comments/s7-11-23/s71123-typec.pdf",
      "/comments/s7-11-23/s71123-580435-1668442.pdf",
      "/comments/s7-11-23/s71123-580455-1668442.pdf",
      "/comments/s7-11-23/s71123-526915-1512082.pdf",
      "/comments/s7-11-23/s71123-526655-1511282.pdf",
      "/comments/s7-11-23/s71123-485411-1388374.html",
      "/comments/s7-11-23/s71123-464631-1230054.html",
      "/comments/s7-11-23/s71123-420279-1002982.html",
      "/comments/s7-11-23/s71123-411179-972582.pdf",
      "/comments/s7-11-23/s71123-560562.htm",
      "/comments/s7-11-23/s71123-549442.htm",
      "/comments/s7-11-23/s71123-544882.htm",
      "/comments/s7-11-23/s71123-542242.htm",
      "/comments/s7-11-23/s71123-523702.htm",
      "/comments/s7-11-23/s71123-505202.htm",
      "/comments/s7-11-23/s71123-497002.htm",
      "/comments/s7-11-23/s71123-230159-481122.htm",
      "/comments/s7-11-23/s71123-228959-478702.htm",
      "/comments/s7-11-23/s71123-229319-479462.htm",
      "/comments/s7-11-23/s71123-227719-475942.htm",
      "/comments/s7-11-23/s71123-474822.htm",
      "/comments/s7-11-23/s71123-226239-473922.htm",
      "/comments/s7-11-23/s71123-473282.htm",
      "/comments/s7-11-23/s71123-466042.htm",
      "/comments/s7-11-23/s71123-466302.htm",
      "#comments",
      "/comments/s7-11-23/s71123-548455-1571682.pdf",
      "/comments/s7-11-23/s71123-548295-1570963.pdf",
      "/comments/s7-11-23/s71123-548535-1571882.pdf",
      "/comments/s7-11-23/s71123-272620-657162.pdf",
      "/comments/s7-11-23/s71123-270379-652943.pdf"
    ]
  ]
]```
