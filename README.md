# Twilio_based_VT_dining_hall_real-time_notification
![image](https://user-images.githubusercontent.com/71536778/201508084-c06634d9-6072-4bed-890f-1f28fcf686d8.png)

**Android side project:** 
> https://github.com/yingchenxing/Twilio_based_VT_dining_hall_real-time_notification_Android-side

**Server side project:**
> https://github.com/yingchenxing/Twilio_based_VT_dining_hall_real-time_notification_server-side

**YOLOv5 project:**
> https://github.com/yingchenxing/Twilio_based_VT_dining_hall_real-time_notification_YOLOv5

## Inspiration
Virginia Tech has tens of thousands of students on campus. During the usual lunch and dinner rush, the dining halls can become very crowded. However, students have no way of knowing in advance how many people are in each dining hall. The only software that students can use to find out the number of people in the dining halls is Grubhub, but it only shows the number of people who have ordered online. And it's often not up-to-date enough. So it's not uncommon for you only to find out when you get to the cafeteria that you have to spend several minutes in line and what's worse is that you have a very early afternoon class to attend.

## What it does
Based on this situation, we have developed a system that can monitor the number of people in the dining halls in real-time. This system will identify the number of customers through surveillance cameras deployed with the yolov5 model and send the real-time data to the server. The server receives the data and stores it in a local SQL database. At the same time, users can register their cell phone numbers through the mobile application and make a reservation to send a message about the dining hall status. When the time set by the user comes, the server will send the real-time information of the canteen to the user's cell phone through the SMS service provided by Twilio.


## Project Innovation
This project integrates yolov5, Springboot, Android application and Twilio service. Users are able to customize the time they receive canteen information according to their own schedule, making full use of the Twilio service. The system also provides a full restful api for more detailed customization needs.

## Project Preview


## How I built it
### Server side
For the server part, I applied SpringBoot framework to build the backend and used MySQL as my database. My first step was to design the database. Based on our functionality, we only need two tables. One for canteen data and the other for user data. Then I connected my java application and database through MyBatis. At the same time, I wrote templates for the code generator in the MyBatis-plus plugin. It generated the corresponding restful api and controller, mapper and other files for me based on the database I designed. Finally, I wrote a thread for sending SMS messages using the Timer provided by SpringBoot. This thread is executed every 30 seconds. It iterates through all the users and checks if the SMS needs to be sent at the current time. For the function of sending SMS, I called the interface provided by Twilio. When receiving the incoming data from users, the system will first check if there are duplicate registered cell phone numbers to ensure that no duplicate registration problem occurs.

### Android side
On the android side, due to time constraints, I completed an activity. I called the EditTextView and TimePicker provided by Google to read the user's phone number and the time they wanted to receive the message. Then, I implemented a crud operation for the user's information by sending an http request.

### YOLOv5
For computer vision, I did not have time to train a model, so I used the official demo directly. we added a piece of code to maintain an asynchronous thread in the main crowd recognition application. This thread is able to update the canteen count data in real time. Again, it sends the data to the server via an http request.


Challenges I ran into
Accomplishments that I'm proud of
What I learned
