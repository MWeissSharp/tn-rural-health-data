# Healthcare in Tennessee: A Rural vs. Non-Rural Comparison

## Table of Contents
* [Motivation](#Motivation)   
* [Data Questions](#Data-Questions)
* [Data Sources and Tools](#Data-Sources-and-Tools)
* [The Process](#The-Process)
* [Link to the Site](#Link-to-the-Site)

## Motivation
<details>
  <summary>You mean the opportunity to wade through government websites isn't reason enough?</summary>   


  In all seriousness, when first thinking through possible topics for my capstone, I kept returning to the hope that my work would provide a benefit to someone other than myself. I reached out to friends who work in the nonprofit world, one of whom worked for the Rural Health Association of Tennessee. She immediately told me how much value there would be in pulling together the different data sources that she regularly reached for in her work. After taking a look at the websites she sent me, it seemed like an ideal combination of being a challenge for my new skills paired with the chance to have a real, practical application once finished to keep my motivation high in those moments when the frustrating structure of government data was trying every last ounce of my patience.

  While my background is in veterinary, rather than human, medical care, the challenges of providing high-quality, accessible care in rural areas are similar in both worlds. Additionally, my experience with social work served to solidify an interest in exploring and counteracting inequities of all types, and the health threats of the past 2 years have underlined just how critical, and often fragile, our healthcare infrastructure is. I learned a lot on so many levels. As if using new methods in Python, more elaborate elements in Tableau, and a brand new platform for me (Google Sites came to the rescue when I realized a key feature of my map visualizations doesn't work in Tableau stories) weren't enough, I can now claim competence with a lengthy list of new (to me) government acronyms and at least a basic grasp of the complex federal structures at work to incentivize improved health care access for vulnerable populations.
</details>

## Data Questions
1. What does a geospatial analysis of the locations of Rural Health Clinics (RHCs), Federally Qualified Health Centers (FQHCs), and Critical Access Hospitals (CAHs) overlayed with Health Professional Shortage Area (HPSA) designations (geographic, population, and facility) reveal?  
2. What relationships can be uncovered when incorporating additional county-level data alongside the HPSA designations?

## Data Sources and Tools  
#### Data Sources
* [Qcor.cms.gov](https://qcor.cms.gov/)
* [data.hrsa.gov](https://data.hrsa.gov/)
* [census.gov/data](census.gov/data)
    * [Small Area Health Insurance Estimates](https://www.census.gov/data/datasets/time-series/demo/sahie/estimates-acs.html)
    * [American Community Survey Poverty data](https://www.census.gov/acs/www/data/data-tables-and-tools/supplemental-tables/)

#### Technology Tools
* Python
  * [Jupyter Notebooks](https://jupyter.org/)
  * [pandas](https://pandas.pydata.org/)
  * [requests](https://requests.readthedocs.io/en/latest/)
  * [Selenium WebDriver](https://www.selenium.dev/documentation/webdriver/)
* [Tableau](https://www.tableau.com/)
* [Google Sites](https://workspace.google.com/products/sites/)

## The Process  
<details>
  <summary>Acquiring the data</summary>

The first real challenge for this project was scraping details about the healthcare facilities that have met specific, federally defined criteria and serve as major players in providing rural (and other vulnerable populations) with care. Most of the data about most of the facilities could actually be obtained fairly easily from the Health Resources and Services Administration (HRSA) data site, but one key element, the ownership type for each facility, is not included in their data sets. To get that detail, along with information about a few additional facilities, I had to go to qcor.cms.gov. This site provides data about facilities certified by the Centers for Medicare and Medicaid Services (CMS), and let's just say it is not the most streamlined system I've ever encountered with details about each facility only available via individual pop-up windows.

This challenge provided the opportunity to use python along with Selenium web driver to navigate to each pop-up then scrape all relevant information before moving on to the next facility. Once I had this script up and running, it was easy to iterate through all the facility types of interest and grab the details I was after.

I had hoped to use APIs to obtain the bulk of the rest of my data, but I ran into a few hurdles. First, HRSA never responded to my requests to obtain an API, so I ended up just utilizing the tools on the site to search for and download additional data about healthcare facilities to pair with what I scraped from Qcor, and also to obtain details about Health Care Provider Shortage(HPSA) designations. The HRSA uses specific US Census poverty data as part of the process for scoring HPSAs, so for consistency, I also pulled this dataset from the HRSA site.

While I did find a way to obtain health care insurance coverage data via API, the data available using this method was a few years out of date, so again I ended up finding and downloading more current data from the US Census Bureau.

There are many other demographic and health metrics I was (and still am) curious to explore and potentially incorporate, but in the interest of maintaining a focus on the key pieces emphasized by my friend who works in this realm, I leave those additional pieces to possible future versions!
</details>  

<details>
  <summary>Cleaning and organizing the data</summary>

The main challenge related to cleaning the data involved making sure that all facility and HPSA entries included correct and consistent information about the county in which each was located and the rural status of that county. I found a data set listed a county name for every zip code, created a dictionary, and utilized it to fill in any missing county entries. From there, I used the rural status information defined for all HPSAs to fill in any missing/inconsistent facility-level data. There was also some work to most effectively combine the facility data sets from both Qcor and the HRSA site.

Once those pieces were in place, the focus was on consistent formatting for all three facility-level tables and filtering the other data sets down to just the those entries that are relevant for Tennessee.

</details>

<details>
  <summary>Loading data to Tableau, building dashboards</summary>

After moving data into Tableau, my first step was to begin building maps. A major element that my friend emphasized to me was her wish to be able to see the distribution of healthcare facilities, ideally layered with other relevant pieces of data. From there, I looked at a variety of options, and ultimately decided that to maximize flexibility for users via filtering options while also balancing clarity and ease-of-use, I would build separate dashboards for each major data element (facilities, HPSA designations, health insurance coverage rates, ) along with an overview comparing rural and non-rural areas on these metrics. I also added additional 

</details>

## Link to the Site
Explore [the details and dashboards](https://sites.google.com/view/tnhealthcaremetrics/home) by clicking and hovering to your heart's content!
