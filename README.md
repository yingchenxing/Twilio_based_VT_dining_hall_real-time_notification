# Twilio_based_VT_dining_hall_real-time_notification
![image](https://user-images.githubusercontent.com/71536778/201508084-c06634d9-6072-4bed-890f-1f28fcf686d8.png)

**Android side project:** 
> https://github.com/yingchenxing/Twilio_based_VT_dining_hall_real-time_notification_Android-side

**Server side project:**
> https://github.com/yingchenxing/Twilio_based_VT_dining_hall_real-time_notification_server-side

**YOLOv5 project:**
> 

## Background
Virginia Tech has tens of thousands of students on campus. During the usual lunch and dinner rush, the dining halls can become very crowded. However, students have no way of knowing in advance how many people are in each dining hall. The only software that students can use to find out the number of people in the dining halls is Grubhub, but it only shows the number of people who have ordered online. And it's often not up-to-date enough. So it's not uncommon for you only to find out when you get to the cafeteria that you have to spend several minutes in line and what's worse is that you have a very early afternoon class to attend.

Based on this situation, we have developed a system that can monitor the number of people in the dining halls in real-time. This system will identify the number of customers through surveillance cameras deployed with the yolov5 model and send the real-time data to the server. The server receives the data and stores it in a local SQL database. At the same time, users can register their cell phone numbers through the mobile application and make a reservation to send a message about the dining hall status. When the time set by the user comes, the server will send the real-time information of the canteen to the user's cell phone through the SMS service provided by Twilio.


## Project Innovation
