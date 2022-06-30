# ASN Pool Fix
### The purpose of this project is to update the Pool ID and names in the XML files received from SPS commerce team.
---
Developed by Vikas Singh for Cirkul.


## Follow the below steps to use this program:
1. Create a virtual environment and install all the libraries
2. Go to **input** folder > Add the unedited files in the **current** folder
3. In the input folder > Update the file named **store_to_pool_lookup.csv** with the latest data.
4. Go to **src** folder and execute the script **main_Pool_Update**.

---
## Troubleshooting
**T01**. If you are getting error messages - "Match not found".\
**Sol.** Check the store_to_pool_lookup.csv file to see if there are zeroes in front of the store numbers. When you open a CSV file in MS-Excel, it strips away any leading zeros from the store numbers. When you run the script in this state, the store numbers in the XML files (e.g 0075) won't match the ones in the lookup table (e.g. 75).\
To fix this,
* open the CSV file > add a column to the right and use formula = TEXT(A2,"0000") to generate the correct store numbers.
* Drag it down to populate all of them > Then copy those and paste as value in column A. Now you should see zeros in front.
* Delete the column added > and save the file and run the script again.