# firstGO
hi 
The goal  of this scraper API will be to fetch an Amazon result page, loop through the different articles, parse the data we need, go to the next page, write the results in a CSV file and… repeat.
In order to do this, we’ll use a library called Colly. Colly is a scraping framework written in Go. It’s lightweight but offers a lot of functionalities out of the box such as parallel scraping, proxy switcher, etc.
In Colly, you need first to implement a Collector. A Collector will give you access to some methods allowing you to trigger callback functions when a certain event happens. In order to implement a Collector
The callback function passed to the ForEach method gives us access to each product one by one. From there, we can simply access the value we want with the CSS selectors we discovered in the first part
Saving our data to JSON
We import the ioutil package so we can to write to a file
We import the os package
The OS package provides an interface to operating system functionality
Inside the function body, let’s use MarshalIndent to marshal the data we pass in
The MarshalIndent method returns the JSON encoding of data and also returns an error
Some error handling. If we get an error here, we will just print a log message saying we were unable to create a JSON file
Now if we go back to the terminal and run the command go run main.go, all our scraped rhino facts will be saved in a JSON file called productdetails.json
