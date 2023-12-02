# Product Search Project
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

### Example of exported data (Data was then cleaned to let it import into MySQL Workbench easily)
![image](https://github.com/SharedPluto/ProductSearchDataProject/assets/100516730/123d71b4-eb96-434c-bb10-f2aab076f8ae)


## Step 2 of funnel
From this data, we only need these fields:
1. Search volume
2. Significance
   - New field derived from count of records of ranking <45 for each KW
4. Title Density
5. Product 1-10 organic rankings

Creating the Significance field was done in Excel with a simple COUNTIF()
```
=COUNTIF(Z2:AI2,"<=45")
```

This new table with the fields we require is created with this query
```
SELECT "keyword_phrase", "search_volume", "significance"
FROM asin_research.cardholder
ORDER BY "significance" DESC;
```
From the table created we can see the KWs and their general strength to get a good feel if this is something we can leverage during a product launch

From here on my analysis will be using Excel and Tableau.

Exporting this data and joining it back with the rankings of each ASIN, we get a table like this example:
![image](https://github.com/SharedPluto/ProductSearchDataProject/assets/100516730/3bb39ecc-55cc-4235-acc7-7ca5d55be09f)

We can now proceed to find out the relative strength of these products' ranking and PPC marketing efforts

## Step 3 of funnel

To analyse commpetitor strength, calculations are made to find out each competitors':
1. Number of KWs with search volume > 250 and organic ranking < 45 (=COUNTIF(F3:F96,"<45")) converted to % of total
2. Search volume that ASIN garners with their ranked keywords in the first page of Amazon (=SUMIF(F4:F97,"<45",B4:B97)) converted to % of total

After applying these formulas across the ASINs we get this result
![image](https://github.com/SharedPluto/ProductSearchDataProject/assets/100516730/f605c218-dff3-45ef-a631-f4863148c1e2)

I then use conditonal formatting to help visualise the strength and share that a product has in its respective market
The criteria is as follows:
1. Very strong = 81-100% (Red)
2. Strong = 61-80% (Orange)
3. Moderate = 41-60% (Yellow)
4. Weak = 21-40% (Green)
5. Very weak = 1-20% (Light green)

![image](https://github.com/SharedPluto/ProductSearchDataProject/assets/100516730/fb431555-faba-4b8e-aea0-598839756778)


**No strong competition is a GO!**

## Step 4 of funnel

If the product niche passes the 3rd step, we move on to the other steps and push the niche through more requirements:
1. Product seasonality check (Google analytics and search trends)
2. Manufacturing cost and budget calculations
3. Differentiation
4. Profit margin calculation
5. Patent checks

# Results

This is how I use data to make the best business decisions possible and give myself an edge over the competition with my first product

Link to my product: https://www.amazon.com/dp/B0C89SKLDN?ref=myi_title_dp

First month performance of launch:
![image](https://github.com/SharedPluto/ProductSearchDataProject/assets/100516730/2fd0b3bd-8d3c-4c03-8261-1fdefcd13457)

Product ranking on first page of Amazon on important keywords:
![image](https://github.com/SharedPluto/ProductSearchDataProject/assets/100516730/878a8afd-4f87-4ef4-99d3-1aebaa81c6d4)

This is how I acquired, manipulated and gained insights from data that helped drive my business decisions!
