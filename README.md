AmbitionBox Company Data Scraper

This Python script scrapes company information (names, ratings, reviews, etc.) from AmbitionBox's "List of Companies" page and saves it as a CSV file.

How I Did It:

Installation of Required Libraries:
I first ensured that I had the necessary libraries installed by using the following pip install commands:
bash
Copy code
pip install requests beautifulsoup4 pandas numpy
Creating the Script:
I saved the script as a Python file, naming it ambitionbox_scraper.py.
Running the Script:
I executed the script from the command line using:
bash
Copy code
python ambitionbox_scraper.py
Output: The script created a CSV file named ambitionbox_data.csv, containing company information retrieved from all pages (up to a limit, which I adjusted in the loop in the code).

How It Works:

Imports: The script imports necessary libraries for making HTTP requests, parsing HTML, creating dataframes, and (optionally) handling missing values.
Fetching and Parsing:
It fetches the HTML content of each page (up to a specified limit) from AmbitionBox's "List of Companies" using requests.get.
The HTML content is parsed into BeautifulSoup objects for easier navigation.
Extracting Company Data:
The script identifies individual company blocks within the parsed HTML using the class company-content-wrapper.
For each company block, it attempts to extract various data points such as Name, Rating, Number of Reviews, Company Type, Headquarters Location, Company Age, and Number of Employees.
It uses try-except blocks to handle potential situations where specific elements might be missing on the website. In such cases, np.nan is used to indicate missing data.
Creating DataFrame:
Extracted data for all companies on each page is stored in a pandas DataFrame.
Combining Data (Optional):
The script iterates through multiple pages (up to a limit) and creates a DataFrame for each page.
These DataFrames are then potentially concatenated (using append) to create a single DataFrame containing data from all scraped pages.
Saving Results:
The final DataFrame containing company information is saved as a CSV file.
