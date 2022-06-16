# smartsheets Sheet IDs. Found on file -. properties page for each sheet:

sheet1_id = 'insert number here'
sheet2_id= 'insert number here' # if more than one sheet is needed. We can had as many as we like

# sheet1's Smart sheet APIs:

sheet1_API = smartsheet.Smartsheet('insert API here') #API will need to be created on your account. click account -> personal settings -> API Acess
sheet1_API.errors_as_exceptions(True) # Make sure we don't miss any errors

# sheet2's API:

sheet2_API = smartsheet.Smartsheet("insert API here") # API
sheet2_API.errors_as_exceptions(True) # Make sure we don't miss any errors

# load in Smartsheets to pandas data frame - A FUNCTION IS NEEDED
# Function to read in column titles and row values and output data frames:

def smartsheet_loadup(sheet):
    """Runs through the smartsheets collection of values and create a Pandas data frame"""
    columns = [col.title for col in sheet.columns]
    rows = []
    for row in sheet.rows:
        cells = []
        for cell in row.cells:
            cells.append(cell.value)
        rows.append(cells)
    df = pd.DataFrame(rows, columns=columns)
    return df

# Callssmartsheet_loadup function to creat out DataFrame:

sheet1_df = smartsheet_loadup(Central.Sheets.get_sheet(sheet1_id))
sheet2_df = smartsheet_loadup(South.Sheets.get_sheet(sheet2_id))


# (Optional) Concat both data frames. This will only work if your sheets are set up with teh same column headers

df_both = pd.concat([Central_SS,South_SS])
