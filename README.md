# Dataiku-team-webscrape

> Author: Alex Lau

<img src="./images/team-1920x296.jpg" width="800px">


## Table of Contents
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Conclusion](#Conclusion)

## Problem Statement
We will build a simple web-scrape to view all team members on Dataiku website and look for any anomalies. If an end user wants to match a name and role of an employee to a face, they should be able to do so seemlessly. It is important for the website to show the most updated information, without errors, missing data, or duplicate records. We will check for correctness to the best of our abilities.

## Executive Summary

We begin with a webscrape of the website: https://www.dataiku.com/company/team/ by using Python library called requests to retrieve HTML from the url, and library BeautifulSoup to pull data out of HTML. After inspecting the HTML of the website, we found that the names were inside tags "h5" and their roles were inside tags "p", both inside a div class = "team-card" for each employee, which made up a single div class = "team-listing". We iterated through all records to pull the names and roles of each employee and created a dataframe using the pandas library. 

While exploring the data, we found 376 names, 362 of them unique and also 170 unique positions. Names on the website are listed as first name, and initial of last name. There is a possibility that 2 or more people have the same first name and intial of last name so we did a check for duplicate names and roles. We found 2 examples of names that more than 1 person shared, but were in different roles. A manual check of their photos on the website confirmed they were indeed separate people. The remaining duplicates, however, appeared to be true duplicates, where the same person, role, and nearly the same image were repeated. 

## Conclusion
We believe we have found errors on the website for the team. We identified 1 employee, who does not have a role assigned, even though we found them on Linkedin with a role. We also identified 12 employees who have their records duplicated, with one of their photos as a zoomed in version of the other. In some cases, the first instance is zoomed in, in others it is the second instance. We recommend updating the site to ensure all roles are populated, and duplicate records removed, although which to remove is up to Dataiku, as all photos look beautiful.

## Source
- [Dataiku Team](https://www.dataiku.com/company/team/)