[https://apify.com/epctex/dnb-scraper](https://apify.com/epctex/dnb-scraper?fpr=yhdrb)

## Features

The [official Dun and Bradstreet API](https://directplus.documentation.dnb.com/) enables you to get data, but it also [enforces quotas and rate limiting](https://directplus.documentation.dnb.com/html/pages/UsingDplusAPIs.html). If you need to do more, this unofficial Dun and Bradstreet API will enable you to:

-   Scrape companies: extract data on companies listed in the DnB Business Directory by search term
-   Scrape articles: extract article content on the DnB website by search term
-   Scrape industries: extract industry insights by search term
-   Scrape URLs: scrape data from one or more specific URLs

## Why scrape Dun & Bradstreet?

[Dun & Bradstreet](https://www.dnb.com/) has been helping its clients and partners grow through the smart use of data and analytics [for over 200 years](https://www.dnb.com/about-us.html). The company offers a wealth of valuable data and insights.

The Dun & Bradstreet website has a [great section of use cases](https://developer.dnb.com/#/use-cases/All) to explain the benefits of using DnB data, covering areas such as:

-   Business due diligence
-   Buyer activity notifications
-   Buyer and influencer mapping
-   Portfolio monitoring
-   Segmentation and prospect identification

## Tutorial

The developer of DnB Scraper has created a [detailed step-by-step guide](https://blog.apify.com/dun-bradstreet-scraper-dnb-api/) to help you scrape Dun & Bradstreet.

If you're new to the world of web scraping, you should check out our [Beginner's Guide to Web Scraping](https://apify.com/web-scraping).

To learn more about using Apify, read our [quick start guide](https://docs.apify.com/tutorials/quick-start#run-an-actor) to using any [Apify actor](https://apify.com/actors).

## Tip
DnB has a geo-location-based protection system. That's why you should always use US-based proxies.

## Cost of usage

The DnB Scraper actor is optimized to run very quickly and scrape items efficiently. Depending on various factors, it should scrape 100 companies in 2 minutes and use approximately 0.07-0.1 compute units, at a cost of about $0.02.

## Input parameters

The input for the scraper should be in JSON. Possible fields are:

- `search`: (Optional) (String) The keyword that you want to search on Dun & Bradstreet with the selected mode.

- `mode`: (Optional) (String) Mode for the actor. Can be either `COMPANIES`, `ARTICLES` or `INDUSTRIES`. Will work in combination with the `search` parameter.

- `startUrls`: (Optional) (Array) List of DnB URLs. You should provide only company, article, or industry detail URLs.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as an argument and returns an object with data.

This scraper requires the use of **proxy servers**, either your own proxy servers or <a href="https://www.apify.com/docs/proxy">Apify Proxy</a>.

### DnB Scraper input example

```json
{
    "mode": "COMPANIES",
    "search": "apple",
    "maxItems": 5
}
```

## During the run

During the run, the actor will output messages letting you know what's going on and which page it's currently scraping.

When items are loaded from the page, you should see a message about this event with a loaded item count.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what went wrong.

## DnB Scraper export

During the run, the actor stores results into an Apify dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node.js/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Dun & Bradstreet actor.

## Output examples

### Scraped company result

The structure of each company scraped from DnB looks like this:

```json
{
    "Company Name": "NEXT BYTE PTY LTD",
    "Company Summary": "NEXT BYTE PTY LTD is located in Albion, QUEENSLAND, Australia and is part of the Retail Sector Industry. NEXT BYTE PTY LTD has 1,440 total employees across all of its locations and generates $505.96 million in sales (USD). There are 54 companies in the NEXT BYTE PTY LTD corporate family.\n\nD&B Hoovers provides sales leads and sales intelligence data on over 120 million companies like NEXT BYTE PTY LTD around the world, including contacts, financials, and competitor information. To witness the full depth and breadth of our data and for industry leading sales intelligence tools, take D&B Hoovers for a test drive. Try D&B Hoovers FreeNEXT BYTE PTY LTD is located in Albion, QUEENSLAND, Australia and is part of the Retail Sector Industry. NEXT BYTE PTY LTD has 1,440 total employees across all of its locations and generates $505.96 million in sales (USD). There are 54 companies in the NEXT BYTE PTY LTD corporate family.",
    "Company Type": "Proprietorship",
    "Company Role": "Subsidiary",
    "Website": "http://www.vitagroup.com.au",
    "Location": {
        "Street Address": "Vita Place 77 Hudson Rd",
        "City": "Albion",
        "Region": "QUEENSLAND",
        "Postal Code": "4010",
        "Country": "Australia"
    },
    "Phone": "+61-736246666\n                        \n                                        Call Us\n                                            \n                                            (866) 258-3217",
    "Description": "NEXT BYTE PTY LTD is located in Albion, QUEENSLAND, Australia and is part of the Retail Sector Industry. NEXT BYTE PTY LTD has 1,440 total employees across all of its locations and generates $505.96 million in sales (USD). There are 54 companies in the NEXT BYTE PTY LTD corporate family.",
    "Key Principal": "MAXINE JOAN HORNE",
    "Industry": [
        "Retail Sector",
        "Miscellaneous retail stores, nec",
        "Computer and software stores",
        "Computer related services, nec",
        "Services, nec"
    ],
    "Company Snapshot": {
        "Employees (This Site)": "",
        "Employees (All Sites)": "1,440",
        "Revenue": "505.96",
        "Year Started": "1997",
        "Incorporated": "1997",
        "Fiscal Year End": "JUN",
        "Assets": "",
        "Ticker Symbol": "",
        "Net Income Growth": "",
        "Sales Growth": ""
    },
    "Financial Statements": {
        "Cost Of Revenue": "",
        "Gross Profit": "",
        "Operating Income": "",
        "Income Before Tax": "",
        "Net income": "",
        "Diluted EPS": ""
    },
    "Competitors": [],
    "Principals": [
        {
            "Name": "MAXINE JOAN HORNE",
            "Position": "Director"
        },
        {
            "Name": "GEORGE EDWARD JAMES SOUTHGATE",
            "Position": "Director"
        }
    ],
    "Breadcrumbs": [
        "HOME",
        "BUSINESS DIRECTORY",
        "RETAIL",
        "AUSTRALIA",
        "QUEENSLAND",
        "ALBION"
    ]
}
```

### Scraped DnB article

The structure of each article scraped from DnB looks like this:

```json
{
    "Url": "https://www.dnb.com/perspectives/corporate-compliance/achieve-greater-fatca-and-crs-compliance.html",
    "Title": "Achieve Greater FATCA and CRS Compliance More Efficiently",
    "Breadcrumbs": ["Home", "Perspectives", "Corporate Compliance"],
    "Author": "David Bolner",
    "Date": "May 30, 2017",
    "Related Articles": [
        {
            "Name": "Six Degrees of Separation: Why You Need to Be Smarter with Data",
            "Link": "/perspectives/corporate-compliance/data-connectivity-relationships.html"
        },
        {
            "Name": "A Record Year for FCPA Fines",
            "Link": "/perspectives/corporate-compliance/2020-record-year-fcpa-settlement-amounts.html"
        },
        {
            "Name": "Beneficial Ownership",
            "Link": "/products/corporate-compliance/beneficial-ownership.html"
        },
        {
            "Name": "Direct for Compliance",
            "Link": "/products/corporate-compliance/direct-for-compliance.html"
        },
        {
            "Name": "D&B Compass",
            "Link": "/products/corporate-compliance/dnb-compass.html"
        },
        {
            "Name": "D&B Onboard",
            "Link": "/products/corporate-compliance/dnb-onboard.html"
        },
        {
            "Name": "",
            "Link": "/products.html"
        }
    ],
    "Cover Image": "https://www.dnb.com/content/dam/english/image-library/Modernization/workspaces/FACTA-and-crs-compliance.jpg",
    "Body": "\n\n                            <p>Foreign Account Tax Compliance Act (FATCA) 2016 deadlines may have passed, but financial institutions (FIs) can achieve Common Reporting Standards (CRS) and FATCA compliance more easily in 2017 using data and technology, as well as lessons learned from 2016.<b></b></p>\n<h2>Pre-existing Account Review Process Is People-Intensive</h2>\n<p>FIs were expected to review their pre-existing accounts (a financial account opened prior to July 1, 2014) to document their account holders' FATCA status during 2016. Once the accounts' FATCA statuses are established, FIs would monitor the accounts for any change in circumstances. Many organizations went to great expense and effort to meet this goal with varying results.&nbsp;</p>\n<p></p>"
}
```

### Scraped DnB industry result

The structure of each industry scraped from DnB looks like this:

```json
{
    "url": "https://www.dnb.com/business-directory/industry-analysis.commercial_and_industrial_machinery_and_equipment_rental_and_leasing.html",
    "type": "Industry",
    "title": "Commercial and Industrial Machinery and Equipment Rental and Leasing IndustryInsights from D&B Hoovers\n                        Industry Analysis\n                                            Geographic Segmentation",
    "Description": "This industry group comprises establishments primarily engaged in renting or leasing commercial-type and industrial-type machinery and equipment.  Establishments included in this industry group are generally involved in providing capital or investment-type equipment that clients use in their business operations.  These establishments typically cater to a business clientele and do not generally operate a retail-like or storefront facility.",
    "Industry Activities": "Aircraft rental or leasing without operator\n                                \n                                            Airplane rental or leasing without operator\n                                \n                                            Barge rental or leasing without crew\n                                \n                                            Boat rental (except pleasure) without crew\n                                \n                                            Boat rental or leasing, commercial\n                                \n                                            Railroad car rental or leasing\n                                \n                                            Ship rental or leasing without crew\n                                \n                                            Steamship rental or leasing without crew\n                                \n                                            Tanker (boat) rental or leasing without crew\n                                \n                                            Towboat rental or leasing without crew\n                                \n                                            Tugboat rental or leasing without crew\n                                \n                                            Bulldozer rental or leasing without operator\n                                \n                                            Construction form rental\n                                \n                                            Construction machinery and equipment rental or leasing without operator\n                                \n                                            Crane rental or leasing without operator\n                                \n                                            Earthmoving equipment rental or leasing without operator\n                                \n                                            Forestry machinery and equipment rental or leasing\n                                \n                                            Heavy construction equipment rental without operator\n                                \n                                            Logging equipment rental or leasing without operator\n                                \n                                            Mining machinery and equipment rental or leasing\n                                \n                                            Oil field machinery and equipment rental or leasing\n                                \n                                            Oil well drilling machinery and equipment rental or leasing\n                                \n                                            Welding equipment rental or leasing\n                                \n                                            Well drilling machinery and equipment rental or leasing\n                                \n                                            Cash register rental or leasing\n                                \n                                            Computer peripheral equipment rental or leasing\n                                \n                                            Computer rental or leasing\n                                \n                                            Copier rental or leasing\n                                \n                                            Duplicating machine (e.g., copier) rental or leasing\n                                \n                                            Facsimile machine rental or leasing\n                                \n                                            Fax machine rental or leasing\n                                \n                                            Furniture, office, rental or leasing\n                                \n                                            Mailing equipment rental or leasing\n                                \n                                            Office furniture rental or leasing\n                                \n                                            Office machinery and equipment rental or leasing\n                                \n                                            Agricultural machinery and equipment rental or leasing\n                                \n                                            Audio visual equipment rental or leasing\n                                \n                                            Carpentry equipment rental or leasing\n                                \n                                            Carpet and rug cleaning equipment rental or leasing\n                                \n                                            Compressor, air and gas, rental or leasing\n                                \n                                            Farm equipment rental or leasing\n                                \n                                            Farm tractor rental or leasing\n                                \n                                            Floor sanding machine rental or leasing\n                                \n                                            Floor waxing equipment rental or leasing\n                                \n                                            Furniture, institutional (i.e. public building), rental or leasing\n                                \n                                            Garden tractor rental or leasing\n                                \n                                            Generator rental or leasing\n                                \n                                            Industrial truck rental or leasing\n                                \n                                            Lawnmower rental or leasing\n                                \n                                            Manufacturing machinery and equipment rental or leasing\n                                \n                                            Material handling machinery and equipment rental or leasing\n                                \n                                            Medical equipment (except home health furniture and equipment) rental or leasing\n                                \n                                            Metalworking machinery and equipment rental or leasing\n                                \n                                            Mobile office building rental or leasing, off-site\n                                \n                                            Modular building rental or leasing, off-site\n                                \n                                            Motion picture equipment rental or leasing\n                                \n                                            Pallet rental or leasing\n                                \n                                            Plumbing equipment rental or leasing\n                                \n                                            Power washer rental or leasing\n                                \n                                            Public address system rental or leasing\n                                \n                                            Renting coin- or card-operated amusement devices (except concession operators)\n                                \n                                            Sawmill machinery rental or leasing\n                                \n                                            Scaffolding rental or leasing\n                                \n                                            Scenery, theatrical, rental or leasing\n                                \n                                            Skid rental or leasing\n                                \n                                            Sound and lighting equipment rental or leasing\n                                \n                                            Telecommunications equipment rental or leasing\n                                \n                                            Textile machinery rental or leasing\n                                \n                                            Theatrical equipment (except costumes) rental or leasing\n                                \n                                            Tractor, farm, rental or leasing\n                                \n                                            Tractor, garden, rental or leasing\n                                \n                                            Traffic control equipment (e.g., barricades, cones, traffic signs) rental or leasing\n                                \n                                            Truck, industrial, rental or leasing\n                                \n                                            TV broadcasting and studio equipment rental or leasing\n                                \n                                            Vending machine rental\n                                \n                                            Woodworking machinery and equipment rental or leasing\n                                \n                                            View 76 industry activities"
}
```

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/dnb-scraper/issues).

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
