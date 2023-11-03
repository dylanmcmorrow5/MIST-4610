# MIST 4610 Group Project 1
## Team Name:
39217 Group 7
## Team Members:
1. Dylan McMorrow
2. Aafreen Anjum
3. Jack Drummond
4. Ishi Gupta
5. Miral Lakhani
## Problem Description:
Our primary goal is to create a relational database that significantly improves the efficiency and quality of a medical center's operations. The central entity in our database model is the "Visit Entity," representing each medical patient's visit. This "Visit Entity" is intricately linked with other key components, including the "Patient," "Visit Record," "Physician," "Room," and "Billing" entities. Our focus is on accurately modeling these relationships, generating realistic sample data, and populating these entities with relevant attributes.

Moreover, we aim to implement fully functional query capabilities on this data. These queries will not only facilitate day-to-day operations but also yield valuable business insights into the medical center's functioning. This enhanced database will provide us with a comprehensive and detailed view of patient visits, medical records, physician-patient interactions, room allocation, and billing processes. By effectively leveraging this database, we can drive informed decision-making, streamline operations, and ultimately enhance the overall performance and quality of care within the medical center.
## Data Model:
Data Model Explanation:

Our model is designed to represent the structure of a small to medium sized emergency healthcare clinic. The Patient entity stores information about all patients who come to the clinic to seek medical care, such as their name, contact information, and any relevant allergies to medications. Each patient will have one or more emergency contacts listed, which is represented by the 1 to many relationship between the Patient and Contact entities. The Contact table stores information about each emergency contact such as their name, address, phone number, email, and the relationship to the patient (e.g. mother, aunt, etc.).

We then have the Visit entity, which is central to the entire model. The Visit table is updated each time a patient comes to the front desk and fills out paperwork, regardless if any tests were performed. Each patient can have as many visits as needed, which is represented by the 1 to many relationship between the Patient and Visit entities. A visit is also associated with a particular physician, whose information is stored in the Physician table. Every visit is associated with one patient and one primary physician. A physician will have many visits over the course of their career, but each visit only has one physician, which can be seen by the one to many relationship between Physician and Visit.

Each visit also takes place in a particular room. Information about each room such as its number, name, and the wing it is located in (North, South, East, or West) is stored in the Room entity. Each visit is associated with one room, but a particular room will be associated with many visits, which can be seen in the one to many relationship between Room and Visit. It is important to note that while a patient may have tests done in multiple rooms on the same visit (X-ray in one room, MRI in another), each visit is assigned a primary room number where the Physician meets with them privately. 

The clinic also owns a lot of different pieces of medical equipment. Information about this equipment is stored in the Equipment table. The table stores the name of the equipment (e.g. an X-Ray machine), the date the equipment was purchased, and also the price. Additionally every piece of equipment is associated with a particular room. One room can have multiple pieces of equipment, but a particular piece of equipment can only belong to one room. This is shown by the one to many relationship between Room and Equipment. 

Additionally, the clinic can perform many different tests. The Test entity stores information about the different types of medical tests done on a patient. Examples include blood tests, MRIs, etc., and the visitRecord entity stores information about each visit and any potential tests performed. There is a one to many relationship between visitRecord and Test because a particular test can be done multiple times on the same patient, and therefore be found in multiple different visit records. There is also a one to many relationship between Visit and visitRecord because during each visit a patient can have multiple tests performed on them, which will each go into a separate visit record.

Each Visit is associated with one bill (also known as an invoice). This is represented by the one to one relationship between the Visit and Billing tables. While each visit can be associated with multiple visit records, it is important to note that a visit can only have one bill in total, regardless of the number of visit records associated with one visit. 

Each visitRecord then has the potential to generate a Prescription for the patient. One visitRecord can generate multiple prescriptions (E.g. a test revealing a broken bone may lead to multiple pain relief medications prescribed), and each prescription is only tied to one visitRecord. This is evident by the one to many relationship between visitRecord and Prescription. 

This clinic also stores many different medications, which we have organized in the Medications table. The clinic also maintains a list of approved suppliers for which they get their medications from. At this particular clinic, each medication is provided by only one supplier. This is represented by the one to many relationship between the Supplier and Medication tables, as one supplier can provide different medications, but each medication is tied to a particular supplier. Each prescription can only have one medication listed on it. That being said, a particular medication can be listed in multiple different prescriptions. This is evident in the one to many relationship between Medications and Prescriptions.
<img width="678" alt="Screenshot 2023-11-03 at 5 44 54 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/39fa62eb-710c-4e12-8e6b-7f0b1114b0c2">

## Data Dictionary:
## Queries:
<img width="710" alt="Query Matrix" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/38719c31-c030-440a-bc42-95b7d1faaa86">

<img width="927" alt="Query 1" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/2771356a-f2f2-45d3-b772-19ce114b9db4">

<img width="1200" alt="Query 2" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/9cc448b4-b172-422d-a24a-9b2b3c03afd2">

<img width="1153" alt="Query 3" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/6d4faa10-be0c-479b-b9e7-0d3fd1d03017">

<img width="843" alt="Query 4" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/aa53c606-5df4-450c-b0e6-51eabf1b8b69">

<img width="1027" alt="Query 5" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/5fc26b43-3c9b-4cfd-8acc-b58e45a4dd4e">

<img width="1042" alt="Query 6" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/6da72248-03ee-44d2-a2fb-6c084c5f3a07">

<img width="1200" alt="Query 7" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/839f89c0-09b7-41b3-b0ff-e698cc588f15">

<img width="1059" alt="Query 8" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/765640d4-106b-4b5b-8bc6-333030934a31">

<img width="810" alt="Query 9" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/8a9d16fa-d179-42a1-aacf-96286cc1de52">

<img width="1258" alt="Query 10" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/b18ee07c-0710-4e6b-a28d-64f756eccbae">


## Database Information:
