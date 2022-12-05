### Prerequisites

This is an example of how to list things you need to use the software and how to install them.

- pip
- Python
- Chromedriver
- Selenium

### Installation

1. Get selenium chromedriver for your version of chrome [https://chromedriver.chromium.org/downloads](https://chromedriver.chromium.org/downloads)
2. Clone the repo
   ```sh
   git clone https://github.com/davidallenr/KinderCareImgScrape.git
   ```
3. Install Pip packages

   ```sh
   pip install selenium
   pip install python-decouple
   ```

4. Create .env file in root directory with these values

   ```sh
   WEBDRIVER_PATH = "path_to_chrome_driver"
   LOGIN_URL = "https://classroom.kindercare.com/login"
   DEBUG = True
   HEADLESS = True
   USERNAME = "your_login"
   PASSWORD = "your_password"
   WAIT_TIME = 5
   CHILDS_NAME = "your_kids_name"
   ```

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->

## Usage
Forked from davidallenr repo. The original python script was very helpful and save me alot of time. I modifed this to accomodate videos that were uploaded. I also changed the way the files were labeled, namely I added an iso standard date into the filename. I also added a try in case there were any issues with the download. 

ex. 2022-12-25-xxx-CHILDS_NAME.jpg or mov

xxx represents the page that the file came from. There might be some need to know this.

I ran into one problem pulling the files, in some cases it seems that instead of a thumbnail image, the actual image is in the alt src field and there isn't a "big_" image. This will cause a 404 error from S3 saying the file doesn't exist. I haven't found a way around that error yet, but I did put in a try/exception to flag an error during the download process. The page name in the filename helps to find the missing images. When I ran this I only had about a .5-1% error rate with this particular problem. 

<p align="right">(<a href="#top">back to top</a>)</p>
````
