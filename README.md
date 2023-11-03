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

We have attached screenshots from the initial conversation with our client. As evident in our data model below, we adjusted some of the entities originally proposed by our client to better suit their needs and boost efficiency.
<img width="783" alt="Screenshot 2023-11-03 at 5 55 51 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/4258493f-0a15-47cd-8773-8c673afe26d3">
<img width="684" alt="Screenshot 2023-11-03 at 5 56 07 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/4cb9ca18-3efd-4078-8000-1b34aea046ee">
<img width="592" alt="Screenshot 2023-11-03 at 5 58 12 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/3beb6ea4-0b78-45f6-b9aa-7bba098a903c">

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
<img width="656" alt="Screenshot 2023-11-03 at 6 13 34 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/77ae8788-8ddf-4e88-85dc-1591fcf8d3b7">
<img width="640" alt="Screenshot 2023-11-03 at 6 13 39 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/c4170ef9-4c8e-4e0c-a8ea-7355b6f30975">
<img width="667" alt="Screenshot 2023-11-03 at 6 13 44 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/8ea5400d-ca41-4a7f-8c9f-ccba379cd699">
<img width="663" alt="Screenshot 2023-11-03 at 6 13 49 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/171fbd98-f444-489d-b81f-c21be0715f62">
<img width="647" alt="Screenshot 2023-11-03 at 6 14 00 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/417eef07-6750-46e8-88d2-faae31ef08f4">
<img width="649" alt="Screenshot 2023-11-03 at 6 14 05 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/b72742c7-abc0-42cd-b0fd-26c7229c2516">
<img width="601" alt="Screenshot 2023-11-03 at 6 14 11 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/20f6d0a2-cee4-427f-b816-3475a28cb74c">
<img width="644" alt="Screenshot 2023-11-03 at 6 14 16 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/1feebafa-7e0f-43a5-b59b-3be77e1bff59">
<img width="627" alt="Screenshot 2023-11-03 at 6 14 20 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/e0a8c55e-d2fc-47ef-8f73-966fc3f1bc94">
<img width="634" alt="Screenshot 2023-11-03 at 6 14 25 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/d6ece9ed-4d6f-47eb-b4f3-24bf0447cae5">
<img width="649" alt="Screenshot 2023-11-03 at 6 14 32 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/0be4b4c5-a642-48b4-90a1-069cff4a67c3">
<img width="653" alt="Screenshot 2023-11-03 at 6 14 40 PM" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/65273281-c99c-4b1a-9af1-d003aa6374e7">


## Queries:

<img width="710" alt="Query Matrix" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/38719c31-c030-440a-bc42-95b7d1faaa86">


Query 1 lists the equipment ID and name of equipment that is not currently assigned to a room.
<img width="927" alt="Query 1" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/2771356a-f2f2-45d3-b772-19ce114b9db4">

Query 1: The provided query is essential for management to identify equipment that is not currently assigned to any room, enabling efficient resource allocation and cost control. It would help managers identify which equipment could be allocated into rooms to ensure that they are maintaining operational efficiency within the medical center.


Query 2 lists physicians’ names who did not have any visits on April 29, 2023.
<img width="1200" alt="Query 2" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/9cc448b4-b172-422d-a24a-9b2b3c03afd2">

Query 2: This query can allow managers to quickly identify which physicians did not see any patients on a particular day. This will help them when they are scheduling the physicians for the upcoming weeks.


Query 3 lists all physicians and the total number of visits they have conducted.
<img width="1153" alt="Query 3" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/6d4faa10-be0c-479b-b9e7-0d3fd1d03017">

Query 3: This query allows managers to monitor physician progress and could be used for Employee of the Week purposes. This would also enable managers to assess the productivity and contributions to patient care of the physicians.By tracking how frequently physicians have patient visits and identifying any underperformance and potential discrepancies.


Query 4 calculates the average price of equipment in each room.
<img width="843" alt="Query 4" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/aa53c606-5df4-450c-b0e6-51eabf1b8b69">

Query 4: This query allows the clinic managers to see which rooms they have invested the most money into for equipment, and which rooms they have invested the least in. It gives an idea of which rooms could use further investment in equipment in order to improve the care and treatment for patients.


Query 5 lists the patients with a total billing amount exceeding 3000 dollars.
<img width="1027" alt="Query 5" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/5fc26b43-3c9b-4cfd-8acc-b58e45a4dd4e">

Query 5: This query enables clinic managers to find which patients have spent $3000 or more on a single bill for a visit, in case the the managers would like to decide to give a future discount or rebate to those patients.


Query 6 lists the patient names and the number of visits they have whose status is not ‘Canceled’.
<img width="1042" alt="Query 6" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/6da72248-03ee-44d2-a2fb-6c084c5f3a07">

Query 6: This query permits clinic managers to identify the number of visits a patient has scheduled and actually attended. Canceled appointments are frequent occurrences for clinics. Therefore it is important for managers to have the ability to omit them when finding the number of appointments a patient has had.


Query 7 displays the name (last name and first name concatenated) of the physician and the amount of billing he has generated. Order results in a descending value of dollars’ worth of billing.
<img width="1200" alt="Query 7" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/839f89c0-09b7-41b3-b0ff-e698cc588f15">

Query 7: This query grants the clinic the capability to find the total billing amount each doctor has generated. There are numerous reasons this is valuable. For instance, a physician could be overcharging patients accidentally, or maybe the clinic is interested in seeing the physicians who have produced the most revenue so that the clinic can give them a salary bonus.


Query 8 lists the five suppliers that have supplied the most medications, and the number of medications have they have supplied
<img width="1059" alt="Query 8" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/765640d4-106b-4b5b-8bc6-333030934a31">

Query 8: This query also offers a valuable overview of the suppliers that have consistently provided the highest number of medications, allowing managers to make informed decisions regarding supplier relationships, when to negotiate better terms, and to enhance the clinic's overall medication inventory management.

Query 9 lists the visit with the highest number of tests performed.
<img width="810" alt="Query 9" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/8a9d16fa-d179-42a1-aacf-96286cc1de52">

Query 9: This query allows managers to identify the highest amount of tests conducted during one visit. Perhaps they are considering adding an additional charge if a certain number of tests are conducted, and they wish to see the largest number in order to help them make a more informed decision.


Query 10 lists the number of bills of each patient with an amount that is greater than their own average bill amount
<img width="1258" alt="Query 10" src="https://github.com/dylanmcmorrow5/MIST4610GroupProject1/assets/148798141/b18ee07c-0710-4e6b-a28d-64f756eccbae">

Query 10: This query allows the clinic staff to give more detailed information on billing to their patients. A patient who has had numerous visits may want to know the number of visits that have exceeded the average billing amount of one of their own visits.


## Database Information:
Name of Database: ns_F2339217Group7
