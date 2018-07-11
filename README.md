# Python Practice

import requests
from bs4 import BeautifulSoup
#import pandas as pd

WIKI_URL = "https://en.wikipedia.org/wiki/List_of_copper_alloys"

req = requests.get(WIKI_URL)

#scrapy

soup = BeautifulSoup(req.content, 'lxml')

tables = soup.findAll("table", { "class" : "wikitable" })


for table in tables:
    mech=soup.find(string="Mechanical properties of common copper alloys")
    print(table)