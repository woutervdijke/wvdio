# Our World In Data bookmarklets

These bookmarklets make it easy to download data from the fantastic repository [Our World In Data](http://www.ourworldindata.org). It only downloads the data from the graph that you see on your screen, instead of the entire data set.

### Installation
Drag the links below to your bookmarks bar. That's it!

### Usage
1. Go to the page you're interested in
2. Set up the graph to your liking, adjusting the timeline and the selected countries
3. Click the bookmarklet to download the data or copy it to your clipboard.

There are two versions of the bookmarklets:
## US version
[Download data to csv]() | [Copy data to clipboard]()
- periods are used as decimal separator
- columns in the csv are separated with commas

## Europe version
[Download data to csv]() | [Copy data to clipboard][1]
[1]:javascript:(function()%7Bfunction%20getOwidData()%7Bvar%20filteredCountry%20%3D%20%5B%5D%3Bvar%20filteredTime%20%3D%20%5B%5D%3BfilteredCountry%20%3D%20grapher.mappableData.filter((obj)%20%3D%3E%20Object.values(grapher.selection.selectedEntityNames).indexOf(obj.entityName)%20%3E%20-1)%3BfilteredTime%20%3D%20filteredCountry.filter((obj)%20%3D%3E%20obj.time%20%3E%3D%20grapher.minTime%20%26%26%20obj.time%20%3C%3D%20grapher.maxTime)%3BfilteredTime.forEach(x%20%3D%3E%20x.time%20%3D%20grapher.formatTime(x.time))%3BfilteredTime.forEach(x%20%3D%3E%20x.value%20%3D%20x.value.toString().replace('.'%2C'%2C'))%3Breturn%20filteredTime%3B%7Dfunction%20jsonToExcel(json)%20%7Bvar%20fields%20%3D%20Object.keys(json%5B0%5D)%3Bvar%20replacer%20%3D%20function(key%2C%20value)%20%7B%20return%20value%20%3D%3D%3D%20null%20%3F%20''%20%3A%20value%20%7D%20%3Bvar%20csv%20%3D%20json.map(function(row)%7Breturn%20fields.map(function(fieldName)%7Breturn%20JSON.stringify(row%5BfieldName%5D%2C%20replacer)%3B%7D).join('%5Ct')%3B%7D)%3Bcsv.unshift(fields.join('%5Ct'))%3Bcsv%20%3D%20csv.join('%5Cr%5Cn')%3Breturn%20csv%3B%7Dfunction%20copyStringToClipboard%20(str)%20%7Bvar%20el%20%3D%20document.createElement('textarea')%3Bel.value%20%3D%20str%3Bel.setAttribute('readonly'%2C%20'')%3Bel.style%20%3D%20%7Bposition%3A%20'absolute'%2C%20left%3A%20'-9999px'%7D%3Bdocument.body.appendChild(el)%3Bel.select()%3Bdocument.execCommand('copy')%3Bdocument.body.removeChild(el)%3B%7Dif%20(window.location.href.split('%2F')%5B2%5D%20%3D%3D%20'ourworldindata.org')%7Bvar%20owidData%20%3D%20getOwidData()%3Bvar%20excelData%20%3D%20jsonToExcel(owidData)%3BcopyStringToClipboard(excelData)%3Bvoid(alert('Data%20copied%20to%20clipboard'))%3B%7D%20else%20%7Balert('This%20bookmarklet%20only%20works%20on%20ourworldindata.org')%7D%7D)()
- commas are used as decimal separator
- columns in the csv are separated with semicolons

## Known bugs
- When used twice in a row, the bookmarklet generates an error. Refresh the page before using a second time.
