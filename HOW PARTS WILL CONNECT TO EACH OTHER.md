# HOW PARTS WILL CONNECT WITH EACH OTHER 

The system is built using three main layers: the robot hardware, Firebase backend, and mobile application. Each layer communicates with the others through clearly defined data paths to ensure smooth operation and real-time updates.

## 1. Robot (ESP32) to Firebase

The ESP32 acts as the main controller of the robot. It connects to the internet using Wi-Fi and communicates directly with Firebase Realtime Database.

Sensor data such as obstacle distance, IR readings, and delivery status is sent from the ESP32 to Firebase.

When the robot reaches a patient and dispenses medicine, it updates the medicine stock in Firebase.

If stock goes below a defined limit, the ESP32 triggers a low-stock status update in Firebase.

This allows the backend to always maintain the latest state of the robot and medicine inventory.

## 2. Firebase as the Central Hub

Firebase Realtime Database works as the central communication layer between the robot and the mobile application.

It stores medicine stock levels, delivery status, and scheduling data.

Any update made by the ESP32 is instantly reflected in the database.

Firebase Authentication ensures that only authorized users and devices can access or modify data.

Firebase handles synchronization automatically, so both the robot and the app always see the same data.

## 3. Mobile Application to Firebase

The mobile application is developed using Flutter and stays connected to Firebase in real time.

The app listens for changes in medicine stock, delivery updates, and alerts.

When the database changes, the app UI updates instantly without manual refresh.

The app can also send commands or schedule data to Firebase, which the ESP32 reads and acts upon.

This allows remote monitoring and control of the robot through the mobile application.




<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/dbf771b0-b4e8-4d28-97f0-1315bc3f8d0f" />
