import pandas as pd
from openpyxl import load_workbook

# read the file Excel
workbook = load_workbook(filename="Drug (1).xlsx")
sheet = workbook.active  # Chọn sheet làm việc mặc định

# read data from sheet to DataFrame
data = pd.DataFrame(sheet.values)

df = pd.read_excel("Drug (1).xlsx")

# filter duplicated datas of 4 collums of reviews, efective, ease of use, Satisfaction 
df = df.drop_duplicates(subset=['Reviews', 'Effective', 'EaseOfUse', 'Satisfaction'])

# display DataFrame after deleting duplicated rows
print(df)

# save the excel file(optional)
df.to_excel("Drug_cleaned.xlsx", index=False)

