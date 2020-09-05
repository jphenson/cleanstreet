# cleanstreet
A Stata command for cleaning up common mistakes in street address data that prevent the same physical address from being associated identifiable across years. The original purpose of the program was to help in identifying hospital locations across several dataset over time.

## Simple Example 
The 6 addresses below are of the same physical address, but they were recorded differently each time making matching difficult  
1. "N 2nd St" Consider this the base case
2. "North 2nd St" N is now North 
3. "N second Street" 2nd is now second and St is now Street
4. "N 2nd STRT" St is now STRT
5. "N 2nd  St" A double space between 2nd an St exists
6. " N 2nd ST " A space was place in the front of the string and St is now ST

## Primary Steps the programs takes
1. Converts all strings to lower case.
2. Checks add spaces around common seperators " , / - ()" and the start and end of addresses for proper identification. 
3. Uses the United States Postal Service list of address name abbreviations to the common written form. For example, ave -> avenue. 
4. Converts all  abbreviated cardinal directions to the full form version. For example, n. -> north or n-> north. 
5. Converts shorten versions of 1st-9th to first-ninth. 
6. Corrects the different version of "po box" to only be written as "po box"
7. Removes excess spaces in street address. 

## Reasons you might use the program
1. Cleanup address information before attemping to submit addresses for geolocation information requests at Census Tiger, Google Maps, Mapbox, or Bing Maps
2. Checking addresses across time for indications of opening/closures of organization or businesses.
3. Prevent gaps or losing observation in datasets across time if a constant permanent address is needed for analysis. 
