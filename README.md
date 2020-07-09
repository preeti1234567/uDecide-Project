# uDecide
The upcoming election on Nov 3, 2020 is one of the most critical in our lifetimes. A clear choice is offered on the direction of the country. However, voter participation and knowledge of their choices for representation could be improved. In such a critical time in our history, education of the voter base will be key in order to make appropriate choices. 

UDecide helps voters get to know their current federal representatives for the  election cycle. We provide a "single pane of glass" for users to know who their four representatives are (President, two Senators, and House member). We display this information in a user friendly way using UI Semantic cards element. 

Once the user has been introduced to their representative, then we dynamically display a button to see what legislation they have sponsored (usually a good indicator of their priorities in office). We hope users can then use this information to decide if their values are being appropriately represented by their current federal official. If not, Nov 3, 2020 is the day to make your opinion matter!

## User Story

* As a citizen I would like to be informed about the choices for the Federal Election in Nov 2020 for my location. 
* I want a  slick interface to quickly tell me, who represents me in the Federal government
* Openweather icon pictures for more visual weather data



### Technologies used
- HTML
- CSS
- Semantic UI
- Javascript
- JQuery
- Datatables Library
- Google Civic API
- proPublica API

#### Code Strategy

UI Semantic had unique elements such as cards and cubes that we used JQuery to animate
```
UI semantic cube element
<div class="ui cube shape ">
                    <div class="sides">
                        <div class="side">
                            <div class="content">

jQuery timer
//set interval to rotate cube display.
var rotate = setInterval(() => $('.shape').shape('flip up'), 3000);
```
For Adding datas to rows
```
$("#billInformationTable").DataTable()
            .rows.add(dataSet)
            .draw();
```
We also experimented with using the APIs to consume the appropriate data we were seeking:

```
// url to get election information from google civic API
var electionURL = `https://www.googleapis.com/civicinfo/v2/elections?key=${civicKey}`;

// url to get voter information from google civic API
var voterURL = `https://www.googleapis.com/civicinfo/v2/voterinfo?key=${civicKey}&address=${address}&electionId=${electionId}&returnAllAvailableData=true`

// url to get all the names of officials and positions from google civic API
var representativesInfoByAddressURL = `https://www.googleapis.com/civicinfo/v2/representatives?key=${civicKey}&address=${address}`
```


#### Link to APIs consumed

[Google Civic API](https://developers.google.com/civic-information)
[Pro Publica](https://www.propublica.org/datastore/api/propublica-congress-api) 

##### Future features
Our initial aim was to use the clean interface to get to know your current federal officials as an introduction into the current election. We were ulimately trying to solve the "California Problem" which is how Californians will play a marginal role in this election with their votes. Of course, California has 55 electoral votes but in reality swing states will decide the Presidential election. Also, with no Senator races in this election cycle, California will not play a role in determining the composition of the new Senate. 

We hope to update this applicatin in the future, and provide a comparison of candidate official running agains the current four federal officials. Also, on a seperate tab, we would like to rank the most competitive races and provide links to donate to those races. We feel that the size of Californias populiation, ~40 million, could play a decisive role in those competitive elections if Californians knew how and where to donate (and we are able to solve the API data feeds to render this information in a clean way). 

###### Author Links
[LinkedIn](linkedin.com/in/joel-mathen/)
[GitHub](https://github.com/crackedsnowboard)
