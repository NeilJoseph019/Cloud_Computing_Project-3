# Cloud_Computing_Project-3

This application is a replica of the social-networking site Twitter, and it portraits the following mechanisms:

1. Login and Logout mechanism.
2. Add username and bio for first-time login users.
3. Add, edit and delete tweets.
4. Edit user information except username which will remain constant throughout the application.
5. Search for a user or a post.
6. Follow another user.
7. Display of tweets in the timeline.
---
#  Application Overview :
For this project the following directories were created:

* app.yaml
* myuser.py
* tweet.py
* main.html
* editprofile.html
* main.py
* editprofile.py
* services.py
* uploadhandler.py
* viewhandler.py

1)	app.yaml:
* The app.yaml code keep the Google App Engine informed about the various libraries , runtime , handlers and the version of python needed to run the application.
* It directs where the requests are routed among the various files in the application.
* The runtime keeps the App Engine informed as to which version or python the application requires and if its latest or not.
* The threadsafe state helps the application to launch multiple instances on the same server using synchronized threads and also avoid loss of data during the process.
* The Jinja2 library is mentioned that helps to generate html templates that can render content to the user.

2)	Myuser.py:
* In this file the user model is created, that stores various user information such as username,location, date of birth, bio, number of tweets and the number of followers.
* The ndb client library is imported from the Google App Engine .ext package, as its used for data store.
* The class takes in ‘ndb.Model’ as argument which enables the various data store operation such as store and retrieve class. It also handles conversions within python and its representation in the data store of the App Engine.
* The string property is user for storing string values and the integer property for integer values.

3)	Tweet.py
* In this file another model is created that stores the tweets , date and time of tweet , username and the image for the tweet.
* The time variable uses datetime property as it stores the date and time from the users system into the data strore in a specific format.
* The variable for image takes in blobkey property which uses the blob storage in-order to store large files that usually don’t fit in the ndb NoSQL database.

4)	Main.html
* This file displays the UI to the user using html and CSS. 
* This file also uses input tags that take in the required user input and also various other tags used to display the information.

5)	Editprofile.py
* This file displays the users timeline or profile page which contains the users tweets and the users information.
* All the user information except the username can be edited and updated. This page is also responsible for the display of other users timeline and also provides a button to either follow or unfollow the particular user.

6)	Main.py
* This file contains various classes that have get methods and post method that helps with the retrival and display of information with the help of html pages.
* The get method helps in creating a new user for first time users , retrieve the user input with the help of .request.get() method and contains various conditional statements and operations such as queries to retrieve the tweets and then display them.

7)	Editprofile.py 
* This file the user tweet query is used to retrieve all the tweets of the user and also various user details.
* It also contains method that’s helps to edit and upload the user information.
The follow and unfollow functionality is also implemented in this file, which appends the users key whom the user clicks and wishes to follow.

8)	Services.py
* This file contains various user specific methods that help in retrieving the user-id, search the twerts by username , search tweets by posts, share a tweet and delete a tweet.
* In this file the classes of other models are imported and also the ndb and user classes of the App Engine are imported.

9)	Uploadhandler.py 
* This file contain the post method that contains “blobstore.BlobInfo(upload_file.key())”which allows to upload the image file with the help of a key.
* It then uses datetime.datetime.now method that helps to get the current system date and time and the its appended along with the tweet in the tweet model.

10)	Viewhandler.py
* This file contains blobstore.get(photo_key)  that helps to retrieve particular picture and display.
