# **Amazon Price Tracker & Web Scraper**

A lightweight Python tool that keeps an eye on Amazon product prices for you. It automatically scrapes live price updates, logs historical data into a local CSV file, and fires off an email alert whenever a price drops below your target threshold.

_**Why I Built This**_

Keeping track of price changes on Amazon manually can be tedious. I put this script together to automate the process—letting it run periodically in the background to log price trends over time and notify me immediately when it's a good time to buy.

_**Key Features**_

- **Smart Scraper**: Pulls product titles and real-time prices using custom headers and CSS fallback selectors to handle dynamic layouts.
- **Local Data Logging**: Automatically creates and updates a local "AmazonWebScraperDataset.csv" file with current timestamps every time the check runs.
- **Email Notifications**: Integrates with Gmail's SMTP server to send an automated alert direct to your inbox when a price target is hit.
- **Scheduled Checks**: Includes a loop setup to continuously monitor prices at set intervals.

_**Repository Structure**_

```text
.
├── Amazon Web Scraping Project.ipynb  # Main Jupyter Notebook
├── requirements.txt                   # Required Python libraries
├── .gitignore                         # Configured to exclude local datasets & temp files
├── LICENSE                            # MIT License
└── README.md                          # Project documentation
```

> **Note**: The ".csv" dataset file is generated automatically when you run the notebook on your local machine and is intentionally excluded from git tracking to keep the repository clean.

_**Tech Stack & Libraries**_

- **Python 3.x**
- [**requests**](https://requests.readthedocs.io/): Sending HTTP requests with custom headers.
- [**beautifulsoup4**](https://www.crummy.com/software/BeautifulSoup/bs4/doc/): Parsing HTML content and extracting product details.
- [**pandas**](https://pandas.pydata.org/): Inspecting and reading the generated dataset.
- **smtplib & datetime**: Standard Python modules used for email automation and timestamping.

_**How to Get Started**_

   **1. Prerequisites**
   
   Make sure you have Python 3 installed on your machine.
   
   **2. Setup**
   
   Clone the repository and install the dependencies:
   
   ```bash
   git clone https://github.com/your-username/amazon-price-tracker-scraper.git
   cd amazon-price-tracker-scraper
   pip install -r requirements.txt
   ```
   
   **3. Configuration & Usage**
   
      1. Open the Jupyter Notebook:
         ```bash
         jupyter notebook "Amazon Web Scraping Project.ipynb"
         ```
      2. Replace the placeholder URL with the Amazon product link you want to track.
      3. Update the target price threshold and set your email credentials inside the `send_mail()` function (use an App Password if    using Gmail).
      4. Run the notebook cells. A local CSV file named `AmazonWebScraperDataset.csv` will be created automatically in your working directory.
   
_**License**_

This project is licensed under the [MIT License](LICENSE).
