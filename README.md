# Healthcare in Tennessee: A Rural vs. Non-Rural Comparison

## Table of Contents
* [Motivation](#Motivation)   
* [Data Questions](#Data-Questions)
* [Data Sources and Tools](#Data-Sources-and-Tools)
* [Analytic Process](#analytic-process)
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

## Analytic Process  
#### Acquiring the data  
-Note about qcor challenges, Selenium used  
-Note about attempt to obtain API for HRSA site
-Note about API for SAHIE providing older data only
-Challenges narrowing down what to include

## Link to the Site
Explore [the details and dashboards](https://sites.google.com/view/tnhealthcaremetrics/home) by clicking and hovering to your heart's content!
