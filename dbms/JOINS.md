# Joins

<ins>Why joins</ins>    
Student and Batch are two separate tables, if you want to get the student names along with their batch name, without joins,     
we need to fetch all students, iterate over the students, use the batch id in the students table, make another network call to get batch details from batch table,      

> two network calls is costly, instead we can join at the database end itself and get joined data   

[Latency Numbers](https://gist.github.com/jboner/2841832)

![Screenshot 2022-12-09 at 12 13 44 PM](https://user-images.githubusercontent.com/16437905/206965641-dabf92ee-011c-485a-8aed-ca05078adbd8.png)


![Screenshot 2022-12-09 at 12 13 52 PM](https://user-images.githubusercontent.com/16437905/206965651-2575b6d1-3324-4603-96bb-23e9a0d98266.png)
