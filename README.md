# Zillow Data Scraper

## Overview

The Zillow Data Scraper is a Python-based web scraping tool designed to extract real estate data from Zillow listings. It utilizes Selenium with an undetected Chrome driver to navigate the website and gather information such as property prices, addresses, features, and images. The collected data is then saved into a CSV file for further analysis.

## Features

- **Web Scraping**: Automatically navigates Zillow property listings and extracts relevant data.
- **Geocoding**: Converts addresses into geographic coordinates (latitude and longitude) using the ArcGIS geocoding service.
- **Dynamic Element Handling**: Uses Selenium's WebDriverWait to handle dynamic content loading.
- **Data Storage**: Saves the extracted data into a CSV file for easy access and analysis.
- **Error Handling**: Includes basic error handling to manage issues during the scraping process.

## Requirements

To run this project, you need to have the following installed:

- Python 3.x
- pip (Python package installer)

### Required Python Packages

You can install the required packages using pip:

```bash
pip install undetected-chromedriver selenium webdriver-manager geopy pygame pandas
```

## Usage

1. **Prepare the Environment**: Ensure you have all the required packages installed as mentioned above.

2. **Run the Script**: Execute the script to start scraping data from Zillow.

   ```bash
   python zillow_data_scraper.py
   ```

3. **Output**: The scraped data will be saved in a file named `ZillowAllData.csv` in the same directory.

## Code Structure

### Classes

- **SilentSupporter**: A base class that provides utility methods for finding elements on the webpage, handling geocoding, and managing the Selenium WebDriver.

  - **Methods**:
    - `simple_finding(xpath)`: Finds a single element by XPath.
    - `simple_findings(xpath)`: Finds multiple elements by XPath.
    - `dynamic_finding(xpath, duration)`: Waits for an element to be present on the page.
    - `get_geocodes(address)`: Retrieves latitude and longitude for a given address.

- **ZillowData**: Inherits from `SilentSupporter` and contains methods specific to scraping data from Zillow.

  - **Methods**:
    - `land_target_page(page_url)`: Navigates to the specified Zillow listing URL.
    - `get_zillow_data(city, id)`: Extracts detailed information from the Zillow listing, including price, address, features, and images.

### Main Execution

The script defines a dictionary `real_estate_urls` containing various cities and their corresponding Zillow listing URLs. It then creates an instance of `ZillowData` and iterates through the URLs to scrape data, which is saved to a CSV file.

## Error Handling

The script includes basic error handling to catch exceptions that may occur during the scraping process. If an error occurs while processing a URL, it will print an error message along with the problematic URL.

## Notes

- **Sound Notification**: The script plays a sound notification if access to a page is denied.
- **Dynamic Content**: The script is designed to handle dynamic content loading, ensuring that it waits for elements to be present before attempting to interact with them.
- **Image Handling**: The script scrolls through the image gallery to collect all available images for the property.

## Limitations

- The script may not work if Zillow changes its website structure or if it implements measures to block scraping.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.

## Acknowledgments

- [Selenium](https://www.selenium.dev/) - For web automation.
- [Undetected ChromeDriver](https://github.com/ultrafunkamsterdam/undetected-chromedriver) - To bypass bot detection.
- [Geopy](https://geopy.readthedocs.io/en/stable/) - For geocoding services.
- [Pandas](https://pandas.pydata.org/) - For data manipulation and CSV handling.
  
## Thank You
