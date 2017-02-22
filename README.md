# Project-DA
# Nahravani a spojovani dat

import pandas as pd
import requests as req
import matplotlib.pyplot as plt
import json
import numpy as np

testData1 = pd.read_csv('/Users/Kamila/Desktop/DA_PROJECT/Data/Test/CodingOk/feedback_jedna.csv', encoding = "windows-1250", delimiter = ";")
testData2 = pd.read_csv('/Users/Kamila/Desktop/DA_PROJECT/Data/Test/CodingOk/feedback_dva.csv', encoding = "windows-1250", delimiter = ";")

# V tabulkach vytvorim novy sloupec kurz
dfTest1 = pd.DataFrame(testData1)
dfTest1["Kurz"]=1
dfTest1.head(4)

dfTest2 = pd.DataFrame(testData2)
dfTest2["Kurz"]=2
dfTest2.head(4)

# Spojím obe tabulky
tables = [dfTest1, dfTest2]
data = pd.concat(tables)
data.shape

# Vytvorim novy index ve nove tabulce feedbacku ke kurzum
data = data.reset_index()
data
