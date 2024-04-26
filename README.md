AmbitionBox Company Data Scraper
This Python script scrapes company information (names, ratings, reviews, etc.) from AmbitionBox's "List of Companies" page and saves it as a CSV file.

Requirements:

Python 3.x
requests library (pip install requests)
beautifulsoup4 library (pip install beautifulsoup4)
pandas library (pip install pandas)
numpy library (optional, for handling missing data) (already installed in your code)
Instructions:

Install Libraries: Ensure you have the required libraries (requests, beautifulsoup4, pandas, and optionally numpy) installed using pip install commands.

Run the Script: Save the script as a Python file (e.g., ambitionbox_scraper.py) and execute it from the command line using python ambitionbox_scraper.py.

Output: The script will create a CSV file named "ambitionbox_data.csv" (or a user-defined name) containing company information retrieved from all pages (up to a limit, adjust the loop in the code).

How it Works:

Imports: The script imports necessary libraries for making HTTP requests, parsing HTML, creating dataframes, and (optionally) handling missing values.

Fetching and Parsing:

It fetches the HTML content of each page (up to a specified limit) from AmbitionBox's "List of Companies" using requests.get.
The HTML content is parsed into BeautifulSoup objects for easier navigation.
Extracting Company Data:

The script identifies individual company blocks within the parsed HTML using the class company-content-wrapper.
For each company block, it attempts to extract various data points:
Name (from <h2> tag)
Rating (from p tag with class rating)
Number of Reviews (from text within a tag with class review-count)
Company Type (from the first p tag with class infoEntity)
Headquarters Location (from the second p tag with class infoEntity)
Company Age (from the third p tag with class infoEntity)
Number of Employees (from the fourth p tag with class infoEntity)
The script uses try-except blocks to handle potential situations where specific elements might be missing on the website. In such cases, np.nan is used to indicate missing data.
Creating DataFrame:

Extracted data for all companies on each page is stored in a pandas DataFrame.
Combining Data (Optional):

The script iterates through multiple pages (up to a limit) and creates a DataFrame for each page.
These DataFrames are then potentially concatenated (using append) to create a single DataFrame containing data from all scraped pages.
Saving Results:

The final DataFrame containing company information is saved as a CSV file.


