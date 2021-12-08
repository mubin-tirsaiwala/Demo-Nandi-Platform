![Nandi logo](/assets/nandi_logo.png)
---
# Nandi Platform for Cattle Biometrics and Valuation
This repo is only for demonstrating Nandi platform. Development codes are kept confidential.

### Project Description :
---
This project is aimed to develop a platform for
- Enabling Digital Identitiy of livestock to enable tracing and logging of everyday data.
- Performing Valuation based on body condition scoring from parameters extracted using images of the animals.  

Currently, eartags are used for logging daily data and registering livestock in government database. Once the tag gets ruptured or thrown away, all the collected data is lost. Our platform utilizes images of animals and creates a digital identity for them using their own intrinsic features. With this project, we are developing largest available cattle database containing about **400 million** dairy animals.  

Currently, further field validation is going on for the biometrics part and Data collection phase is ongoing for cattle valutaion part.

### Results and Recognitions :
---
* Demonstrated Few shot learning capabilities with 92% on-field top-1 identification accuracy on cross breed, indigenous cows and buffaloes.
* Completed Pilot phase for Government of India with data collection of more than 1000 animals from 4 states and 12 regions across India, including both cows and buffaloes.  

### Components :
---
Entire stack consists of an android app, an admin webapp and a backend Restful API which connects everything together. Everything is bundled into docker containers and deployed as microservices on Azure Cloud.

#### Android App:
---
An android app is built for users which has a `.tflite` quality check model deployed on it. This model checks for several parameters for the quality of image and only lets through the images which pass the QC. Using the app, users can register new animals as well as perform identifications on previously onboarded animals. An Admin WebApp is built which is used to monitor incoming data. A Restful API is built which manages the entire stack.

<a href="url"><img src="/assets/nandi_app.jpg" height="480" ></a>  

#### Admin WebApp:
---
Admin webapp is built using [wordpress](https://wordpress.com/). Admins can monitor incoming data, verification logs and analytics graphs based on metadata collected.

![Nandi Admin Webapp](/assets/nandi_webapp.png)

#### Backend API:
---
This api is built using [FastAPI](https://fastapi.tiangolo.com/) and holds the entire stack together. It stores the incoming data from the app into the Azure blob storage and metadata to mongoDB. It runs all the models and retrieves the verification results and sends it to the app as well.

![Nandi Backend](/assets/nandi_backend.png)
