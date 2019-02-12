# Exio3-to-bw2

Import Exiobase v3 into brightway2

This is an attempt to import tables of the Multi-Regional Input-Output database Exiobase version 3 into the python-baseed Brightway2 LCA framework. It works, but it is slow (1h on my computer) and there are certainly better ways to do it.

# Run the code
With the official “exiobase_3.3.15_hsut_2011” **folder** ( downloaded [here](https://www.exiobase.eu/index.php/data-download/exiobase3hyb))in your working directory. 
This is what the code does:

1. Import the HIO sheet from xlsb file
2. Create a dict with activities and exchanges
3. Write the dict as bw database
4. Import final prod sheet from xlsb file
5. Add the final prod to existing bw database
6. Import emissions from another xlsb file
7. Match emissions with biosphere3 codes (only 3 of them as a test)
8. Add the emissions to the existing bw database
9. Do calculations.
 
Important notes and limitations
- Steps 1 and 3 take quite long time. Step 8 might take some time too when done for all emissions.
- This code is exclusively for the supply and use table in hybrid units.
- A mapping of exiobase emissions to biosphere3 exchange codes is needed to extend the import to all environmental exchanges
- I haven’t imported the final demand either. These are activities so would need to be done just before step 3 I think (and will make step 3 even more time consuming).
 
Any feedback is truly appreciated.


