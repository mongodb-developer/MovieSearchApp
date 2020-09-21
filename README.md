# MovieSearch
Basic movie search engine for MongoDB Atlas Search .

For a full tutorial, visit: https://www.mongodb.com/blog/post/lets-build-a-movie-search-engine-using-full-text-search-indexes-in-ten-minutes

Giving your users the ability to find exactly what they are looking for in your application is critical for a fantastic user experience. With MongoDB Atlas’s new Atlas Search feature, we have made it easier than ever to integrate simple but sophisticated search capabilities into your MongoDB applications. 
Harnessing the power of Apache Lucene for efficient search algorithms, static and dynamic field mapping for flexible, scalable indexing, all
while using the same MongoDB Query Language (MQL) you already know and love, `spoken in our very best Liam Neeson impression <https://youtu.be/jZOywn1qArI>`__ MongoDB now has a very particular set of skills. Skills we have acquired over a very long career. Skills that make MongoDB a DREAM for developers like you.

To demonstrate just how easy it is, we will build a simple movie search engine in less that 10 minutes!
![](assets/movie.gif)

  Armed with a basic knowledge of HTML and Javascript, here are the tasks we will accomplish in tutorial:
#### TO-DO LIST
###### ▢ &nbsp; Spin up an Atlas cluster and load sample movie data
###### ▢ &nbsp; Create a Search Index
###### ▢ &nbsp; Write an aggregation pipeline with $search operator
###### ▢ &nbsp; Create a RESTful API to access data
###### ▢ &nbsp; Call API from a web application front-end


  Before we get started, we will need:
1. A MongoDB Atlas cluster running a minimum 4.2. 
2. Atlas Sample Data loaded into the Atlas cluster directly from the Atlas UI. You can get this by clicking the &nbsp; <button style="border-radius: 5px; width:35px;">...</button>&nbsp; button and **Load Sample Dataset**.

## The Front End
This application consists of a single html file. Download the following [ index.html file](http://bit.ly/MDB_FTS_MovieSearch) and open in your browser. You will see a simple search bar:

![image alt text](assets/image_29.png)

Entering in the search bar makes a single call from the Fetch API to retrieve data from Atlas. Entering data in the search bar will bring you movie search results because the application is currently pointing to an existing API.

Now open the html file with your favorite text editor and familiarize yourself with the contents. You’ll note the **<body>** contains a very simple container and 2 javascript functions:

* Line 82 **userAction()** will execute when the user enters a search. If there is valid input in the search box and no errors, we will call the **buildMovieList()** function.

* Line 125 -**buildMovieList()** is a helper function for **userAction()** which will build out the list of movies, along with their scores and highlights from the fullplot field. Notice in line 146 that if the **highlight.texts.type === "hit"** we highlight the **highlight.texts.value** with the **<mark>** tag.

### **Modify the Front End Code to Use Your API**

In the **userAction() **function, we grab the input from the search form in line 83 and append it to the webhook URL before calling the fetch API in line 92.  My data webhook URL from the FTSDemo Stitch application is on line 88. Replace that **webhook_url** variable with your own API from your Stitch HTTP Service. 🤞

Now save these changes, and open the** index.html** file once more in your browser et voilà! You have just built your movie search engine Atlas Search indexes. 🙌 What kind of movie do you want to watch?!

*For a detailed tutorial with screenshots and sample code, visit: https://www.mongodb.com/blog/post/lets-build-a-movie-search-engine-using-full-text-search-indexes-in-ten-minutes . This tutorial will guide you through how to build a web application to search for movies based on a topic using Atlas’ sample movie data collection. We will create an Search index on that sample data. Then we will query on this index to filter, rank and sort through those movies to quickly surface movies by topic.*

Built on Apache Lucene, Atlas Search adds document data to a search index to make that data searchable in a highly performant, scalable manner. 
