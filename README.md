# UFOs

## Project Overview
The following repository includes files for creating a UFO website which displays UFO sightings in a table. To enhance the readability and overall user experince, the ability to filter UFO sighting table was included. Users can filter by date, city, state, country, and shape.

![]()

## Resources
* Data Sources: data.js
* Langauges: JavaScript ES6+,  HTML5, CSS, Bootstrap
* Software: Visual Studio Code 1.43.0, Chrome 81.0.4044.138

## Method
The app was coded using the following steps:

1. Import the data (data.js) and reference the HTML table using d3.
2. Write a function **buildTable** to:
    * Clear out any existing data.
    * Loop through each object in the data and append a row and cells (*dataRow*) to the table body.
        * Loop through each field in *dataRow* and add each value in the row as a table cell.
3. Write a function **updateFilters** to:
    * Use d3 to save the HTML element, value, and id of the filter that was changed (i.e. has user input).
    * Write if-else statements to determine whether a user entry exists in the the following input html boxes:
        * Date
        * City
        * State
        * Country
        * Shape
            * When a user entry exists for any given filter, in the object *filters*, create a key for that filter with the user input as the value.
    * Call the function **filterTable** to apply all filters when rebuilding the table (see step 4.).
4. Write a function **filterTable** to:
    * Set the *tableData* to equal *filteredData*.
    * Convert *filters* object into an array of entries, *filterEntries*.
    * Create a for loop to destructure each *filterEntries* array entry into a key (*filterName*) and a value (*inputValue*).
    * Use JS .filter() to find rows that match (*filterName*, *inputValue*) and assign that data to the variable *filteredData*.
5. Pass *filteredData* to the **buildTable** function to build table with only the filtered data.
6. Use d3.selectAll to run *updateFilters* when the user clicks the filter button.
7. Call **buildTable** function with *tableData* passed in.
NOTE: Since buildTable() takes *tableData*, the raw data is passed in on loading the page (since *tableData* is set to equal 'data'); and the filtered data is passed in when the user clicks the filter button since when the button is clicked, *tableData* is set to equal *filteredData*.

## Recommendations
Recommendations for future enhancements to this webapp are as follows:
* Add webscraping capability to pull in recent data (in lieu of static data)
* Add drop-down lists to the filter input boxes so they aren't free-form text
* Add sorting functionality to the table
* Add links to pages where users can log UFO sightings (assuming that scraping for recent data is implemented)