<h1>Introduction</h1>

<p>Have you ever wanted to scrape reviews from Glassdoor, but bemoaned the site's lack of a public API for reviews? Worry no more! This script will go through pages and pages of reviews and scrape review data into a tidy CSV file. Pass it a company page and set a limit to scrape the 25 most conveniently available reviews, or control options like the number of reviews to scrape and the max/min review publication date.</p><p>It takes about 1.5 seconds per review to scrape. So it will take about 25 minutes to scrape 1,000 reviews, or a little over 4 hours to scrape 10,000 reviews. This script requires patience. 😁</p>

<h1>Installation</h1>

<p>First, make sure that you're using Python 3.</p>

<ol><li>Clone or download this repository.</li><li>Run <code>pip install -r requirements.txt</code> inside this repo. Consider doing this inside of a Python virtual environment.</li><li>Install <a href="http://chromedriver.chromium.org/" rel="nofollow">Chromedriver</a> in the working directory.</li><li>Create a <code>secret.json</code> file containing the keys <code>username</code> and <code>password</code> with your Glassdoor login information, or pass those arguments at the command line. Note that the second method is less secure, but in any case you should consider creating a dummy Glassdoor account.</li></ol>
  
 <h1>Usage</h1>
 <pre>
 <code>usage: main.py [-h] [-u URL] [-f FILE] [--headless] [--username USERNAME]
               [-p PASSWORD] [-c CREDENTIALS] [-l LIMIT] [--start_from_url] 
               [--max_date MAX_DATE] [--min_date MIN_DATE]

optional arguments:
  -h, --help                                  show this help message and exit
  -u URL, --url URL                           URL of the company's Glassdoor landing page.
  -f FILE, --file FILE                        Output file.
  --headless                                  Run Chrome in headless mode.
  --username USERNAME                         Email address used to sign in to GD.
  -p PASSWORD, --password PASSWORD            Password to sign in to GD.
  -c CREDENTIALS, --credentials CREDENTIALS   Credentials file
  -l LIMIT, --limit LIMIT                     Max reviews to scrape
  --start_from_url                            Start scraping from the passed URL.
  
  --max_date MAX_DATE                         Latest review date to scrape. Only use this option
                                              with --start_from_url. You also must have sorted
                                              Glassdoor reviews ASCENDING by date.
                                              
  --min_date MIN_DATE                         Earliest review date to scrape. Only use this option
                                              with --start_from_url. You also must have sorted
                                              Glassdoor reviews DESCENDING by date.</code></pre>
                                              
<p>Run the script as follows, taking Wells Fargo as an example. You can pass --headless to prevent the Chrome window from being visible, and the --limit option will limit how many reviews get scraped. The-f option specifies the output file, which defaults to glassdoor_reviews.csv.</p>                                              
