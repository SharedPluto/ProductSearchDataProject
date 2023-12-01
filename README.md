# ProductSearchDataProject
How I used data to create my business

# Background
When I entered the workforce, I always had the goal to have something on the side, with extra income, I could actually focus on working at where I want to work and what I wanted to do.
This is why I got started with thinking how to build a business on my own.
As I just started my job at the time, I did not have the resources to make mistakes, which is why I started to apply data analysis to the process, to direct myself to the best possible business decision.
This is how I used data to set up my store on Amazon USA.
Trading card collecting is a big hobby of mine, so I already had a niche, now I needed my first product to start selling

# Objective
## To leverage on a product with:
1. Low barrier of entry
2. High search volume and demand
3. Weak use of SEO and Pay-per-click (PPC) advertising

## To fulfill these categories these datasets of top products in their category will be pushed through a funnel with this set of criteria:
1. Average revenue of top 10 competitors < $15,000
2. Number of usable and actionable keywords > 100. Usable keywords are:
   - Monthly Search Volume (SV) > 250
   - Organically ranked between 1 and 45 (First page of Amazon searches) among top 10 competitors

# Data acquisition and preparation
Data on specific products are taken using the software, Helium10, that scrapes Amazon's product database to give me data needed to derive insights from.

## Step 1 of funnel
The process of collecting:
1. Using Helium10 to scrape the top 10 competitors of a product category
2. Export .csv of datasets that pass the initial criteria (Average revenue < $15,000, Keywords (KWs) > 100)

### Example of exported data
![image](https://github.com/SharedPluto/ProductSearchDataProject/assets/100516730/123d71b4-eb96-434c-bb10-f2aab076f8ae)


## Step 2 of funnel
From this data, we only need these fields:
1. Search volume
2. Significance
   - New field derived from count of records of ranking <45 for each KW
4. Title Density
5. Product 1-10 organic rankings

This new table is created with this query
```

```




