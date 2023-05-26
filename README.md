# Crowdfunding ETL

## Overview
Building an ETL pipeline using Python, Pandas, and Pandas dictionary methods to extract and transform data collected from crowdfunding projects.

### Extract
Import data into Jupyter Notebook

    `crowdfunding_info_df = pd.read_excel('Resources/crowdfunding.xlsx', engine = 'openpyxl')
    crowdfunding_info_df.head()`

### Transform
Transform data into readable sections to be reorganized

   `# Iterate through the contact_info_df and convert each row to a dictionary.
    import json
    dict_values = []

    for index, row in contact_info_df.iterrows():
        data = row['contact_info']
        convert = json.loads(data)
        newlist = []
        for i,j in convert.items():
            newlist.append(j)
        dict_values.append(newlist)

    # Print out the list of values for each row.
    print(dict_values)`

### Load
Transofmred Data is then exported to a clean CSV file. 

    `# Export the DataFrame as a CSV file. 
    contacts_df_clean.to_csv("Resources/contacts.csv", encoding='utf8' index=False)`
## Resources
- VS Code
- Jupyter Notebook
- QuickDBD
- PgAdmin4

