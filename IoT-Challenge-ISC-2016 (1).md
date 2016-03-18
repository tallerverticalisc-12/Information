IoT Challenge: Vertical Workshop ISC 2016 
===================================
![Logo](https://scontent-lax3-1.xx.fbcdn.net/hphotos-xpa1/v/t1.0-9/11082635_1142656242435140_6924336588796990133_n.jpg?_nc_eui=ARgr1fJmu8i39UMsHUzyE5DcC61Ee8_TAQoGu1pWpSz4IKqwQtDbHg&oh=4a79beb8e95d1dc25f3900c119c3fd1b&oe=574F2197)
 <p align="center">
**"PARKING WAS NEVER SO EASY" **</p>
-----------------------------------------------------------
Members of the Team:
-------------------------------   
<p align="center"> 
 <img src="https://scontent-atl3-1.xx.fbcdn.net/hphotos-xla1/v/t1.0-0/s526x395/1913887_10207591680645242_3465465095399222194_n.jpg?_nc_eui=ARhWkIMDsG70IFIZZLNdk_G_sCjWojUyLY-pk6CuECM7G398qaRUog&oh=ee6d3f864efd423c66eda06117e4087e&oe=57511CFF" width="200"></p>

> - Ariadna Hérnandez                                              
> - Jésus Alberto Matínez
> - Marysol Sánchez
> - Juan Antonio Olvera
> - Samuel Osuna                                   
> - Eutimio Machuca
> - Luis Bobadilla 
> - Gabriel Trujillo 
> - David Medina
> - José Manuel Salazar
> - Julio Carbajal
> - Ernesto Suárez  

#### <i class="icon-file"></i> Overview

In this Vertical Workshop, a problem was shown to us and we had to give a solution for it by the end of the week, having 4 complete days to work on it. 
The information given for all the students was the next one: we needed to create a mobile app so that users could find a place in a parking lot. In order to do this, the algorithm should be based in zones and not in specific spots. Some specifications were that the app must be able to read a CSV text or use a “Grove-Button” sensor. Our final product, should work with both, hardware to check the status of the parking lot using the Grove: led and LCD RGB Backlight; and the Software, to verify the same status, but without using anything else more than the app (working with IOS or Android). 
For the Final Presentation, our team should present a simple model of our final work, however it must use sensors in the entry and exit. Another specification, is that we must use “Hot Wheels” cars for this model. Additional to this, we must present a YouTube video, no longer than 2 minutes. With this in mind, the pitch of our project must be 5 minutes as maximum.  


----------


Additional Points
-------------------------------
We were given more additional points for the final evaluation. Such as: 

> - Recognition of license plates.
> - Use of sensors to identify Buses, Cars, and Motorcycles.
> - Software to give the status of the parking lot, to the user as well to the administrator. 
> - Ideas to identify special spots for pregnant women and for visitors. 


In order to develop this project, we needed to divide the work depending on the abilities that each member of the team had, or with the things that each of us felt comfortable with. But of course, we supported each and every member of the team in case any of us needed help with something. 

###Working Tools 
####In order to get this challenge done, as said above, we needed to divide the work. So the division of labors were as follows: 
Must deliver:
:  *Working with the Intel Edison Boards (Sensors).
	*Data bases y parse.
	*Model with the “Hot Wheels”.
	*Video
	*Documentation
	*Pitch and presentation.
#### <i class="icon-hdd"></i> Sensors with Intel´s Edison Boards

All of our team members is taking the Major in computer science program. Therefore, not a lot of us were able to work with this kind of boards without the fear of burning any of them. Nevertheless some of the younger members of our team did know a little bit of the subject, thanks to a class that was improved along the semesters. So they decided to take care of this hardware matter. 
To start working with this cards, we were given 2 sets of the “Grove- starter kit plus” from Intel. Additional to this, a lot of investigation was needed for this hardware to start working as it should. Therefore, the more we investigated about the complexity of this cards, the more decisions needed to be taken. For instance, at the beginning of the Vertical Workshop, the programming part was stablished in Java, since is the Language in which most of us is stronger. But, as we were making progress, the language was needed to be changed to Python, since it is easier than Java, and has more paths for the work to be a little bit easier. Java just has a lot of barriers. 
Once this was settled, we needed help from the [Intel Software documentation Page][src] itself. Along with this, another important and big help, was the Intel´s Edison guide that we can find in the next link: https://software.intel.com/en-us/iot/hardware/edison.
[src]: https://software.intel.com/en-us/iot/documentation
Once the idea was clearer, and following the instructions that were given from the beginning, the use of the two Groves were needed.

> - Grove- Button
>It´s a momentary button (rebounds after pressed) being the most common input module we can see. 
> - Grove- Touch Sensor
>Button that can sense the touch of the finger.


----------


#### <i class="icon-hdd"></i> Data Base and Parse

Since the beginning of the planning, the main objective was to make this app as functional as it could be. At first it was decided to make the Data Base using the [Mongo][src] language, but we noticed that it was going to get a little bit tricky. Therefore, we choose to use [MySQL][src2] in order to make it simple and functional, allowing us to fully understand it. 
In order to get comunication between the Data Base and the app, a library Node was necesary. Basically the main communication is based between: 

> - MySQL.
> MySQL is lightweight middleware that provides transparent routing between your application and any backend MySQL Servers. It can be used for a wide variety of use cases, such as providing high availability and scalability by effectively routing database traffic to appropriate backend MySQL Servers. 
> - Node.js
> Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine.  It is an open-source, cross-platform runtime environment for developing server-side Web applications. 

Talking about the dataBase itself, it was implemented to work with only two zones of the parking lot at the beginning of the tests (as we can see in the model mock-up), with the option of working with more if the Data Base is bigger. 
Since the testing was done while thinking on the Tecnologico de Monterrey Campu's parking lot, the data manipulation works with the students enrollment ID. Each and every one of the spots has it´s own ID. That inmediately tells the students if there´s a place available or not , posible thanks to the flags within the program were 1 is available, 0 is not available, and later on a number 2 was stablished to book an especific place (for no longer than 5 minutes). Within the software, we have additional attributes to either tell if a spot is for regular cars, for disability people or for the firetrucks. 
The data base works in relation with the app and the sensors, as we already mentioned. Therefore there´s a strict comunication with the App that at the same time, has a relation with both sensors and their process so the user/student, can have a simple and functional app running and working as it should. 

[src]: https://www.mongodb.org/
[src2]: https://www.mysql.com/

----------


#### <i class="icon-mobile"></i>App & Server
For the final but also very important step, we had to make the application for the final users/students.
In order to make it work, our application was done with the following software:
> - [API Rest][src3]: 
Is a type of web development architecture that fully supports the HTTP standard. REST allows us to create services and applications that can be used by any device or client who understands HTTP, so it is incredibly simple and conventional.
> - [Node][src4]:
Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine.  It is an open-source, cross-platform runtime environment for developing server-side Web applications. 
> - [FrameWork Express][src5]:
Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.
> - [Ionic Framework][src6] for the App:
 Ionic is a powerful HTML5 SDK that helps you build native-feeling mobile apps using web technologies like HTML, CSS, and Javascript. Ionic is focused mainly on the look and feel, and UI interaction of your app. simply fits in well with these projects in order to simplify one big part of your app: the front end.
 > - [Apache Cordova][src7]: 
An open-source mobile development framework. It allows you to use standard web technologies - HTML5, CSS3, and JavaScript for cross-platform development. Applications execute within wrappers targeted to each platform, and rely on standards-compliant API bindings to access each device's capabilities such as sensors, data, network status, etc.

[src3]: http://asiermarques.com/2013/conceptos-sobre-apis-rest/
[src4]: https://nodejs.org/en/
[src5]: http://expressjs.com/
[src6]: http://ionicframework.com/
[src7]: http://cordova.apache.org/

All of this software was needed in order to get a nice and working application in our mobile phones. So basically, the API rest, the FrameWork express, the Ionic Framework, and Cordova, they all run with the Node.js since they need to in constant comunication with the Data Base and the App, which is what the Node does, with the code done in MySQL. 
The App can work with both, IOS and Android operating systems. This main app was done with Ionic Framework as well as with Apache Cordova. The Data Base was implemented using a Node.js Library to get in comunication with the API Rest, which runs with this same Nodel.js. And finally, the relation and comunication of The Edison´s Board with the Data Base and the Application with the Base, is thanks to the API Rest. 
The time given to us was good for the specifications that were given. however some of our ideas to implement in a future are: 
>  *Have the same Log-in as Tec.
>	*Have a Match with the schedule to find a place near to your next class.
>	*Add stadistics to know at which hour is better to find a free spot.
>	*Bluetooth sensor for beacons.
>	*Add a counter to know how many cars are parked in that moment.
>	*Reminder to know where you parked your car. 
>  *Give voice guidance to the place in the parking lot.


----------


#### <i class="icon-flag"></i> Mock-up Model
This part of the Challenge was very specific for us to develop. It needed to be simple but good enough to position the sensors on it, just to make a simulation, were the Grove-Button must be placed in the entrance so the user can press it and they will get an output with a display to know about the places available; in other hand, the Grove-Touch Sensor is going to be stablished in a parking spot, so once the car is in top of it, that place is not longer available for other users, and when the car retrieves, the place changes it's status in the database to available again.
 In addition we were told to use "Hot Wheels" cars for the demonstration. 

![Mock up](https://scontent-lax3-1.xx.fbcdn.net/hphotos-xpt1/v/t1.0-9/12821392_1261037787243950_4431777105054496935_n.jpg?_nc_eui=ARjzWlN5Bi9eu_PhXVuWIbhjV8-hOLgORtyDdBI0uCq7ase7yo2f-g&oh=d2145a0967f9de78d9d9c63e70da6c7a&oe=57861956)

----------

#### <i class="icon-play-circled"></i>Video
Another of the main objectives was to create a video about our project, having as maximum 2 minutes long, and afterwards, upload it to the well known video-sharing website: "You Tube"

> **You Tube Link:** Check out the [<i class="icon-upload"></i> Smart Parking] [src8] video, directly on the You Tube website, or down here:
<iframe width="600" height="480" src="https://www.youtube.com/embed/fKBUEsq4S5w" frameborder="0" allowfullscreen></iframe>

[src8]: https://www.youtube.com/watch?v=fKBUEsq4S5w&feature=youtu.be


---------


#### <i class="icon-male" ></i>Pitch
The Pitch of each team was set to the last day of the Vertical Workshop, in this ocasion on Friday 18 of March. This presentation would help the judges by the end of Friday afternoon, to choose the winning teams. 
The Pitch doesn´t have any rules about how many of us could present our solution or project to the judges, the only point mentioned in the initial documentation, was that the Pitch couldn´t last more than 5 minutes. 

----------


#### <i class="icon-folder-open"></i>Documentation
Finally but not least, at the end of the project we should upload the Documentation to Github. This documentation needs to include: 

* All the code we developed for the App to work properly.
* The information of our Project using the Markdown syntax.


----------






