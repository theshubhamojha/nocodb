---
title: "Rollup"
description: "Understanding Rollup Column!"
position: 560
category: "Product"
menuTitle: "Rollup"
---

## Rollup

Sample Organization structure:

- 5 Departments, each department has a team name & associated team code
- 5 employees working at different Departments
- Teams **has many** Employees : relationship has been defined

![Screenshot 2022-09-09 at 12 57 32 PM](https://user-images.githubusercontent.com/86527202/189296162-536185f1-31ed-40df-b668-deed7ad630aa.png)


### RollUp AGGREGATION functions supported

- Count
- Minimum
- Maximum
- Average
- Sum
- Count Distinct
- Sum Distinct
- Average Distinct

Now, we can explore how to extract employee count information per team using **"ROLLUP"** columns

## Adding a rollup column

#### 1. Add new column

Click on '+' icon to the left of column headers in Departments table

<!-- ![1](https://user-images.githubusercontent.com/86527202/144236273-484edc5b-7f5f-4041-b480-db08d4459d07.png) -->

#### 2. Feed column name

<!-- ![2](https://user-images.githubusercontent.com/86527202/144236279-41904955-4990-4a23-bec6-b0953002eac6.png) -->

#### 3. Select Column type as 'Rollup'

<!-- ![3](https://user-images.githubusercontent.com/86527202/144236283-4596e3e1-3bf8-488f-bc9b-8ec1466a35c6.png) -->

#### 4. Choose Child Table

Table Employee in our example

<!-- ![4](https://user-images.githubusercontent.com/86527202/144236284-301178d8-f452-4d1e-9dff-80dd9570c280.png) -->

#### 5. Choose on ​Child column

Pick appropriate column for aggreagation

<!-- ![5](https://user-images.githubusercontent.com/86527202/144236286-28547d74-feb8-4ad8-a872-7ba809e5db1e.png) -->

#### 6. Select ​Aggregate function

Aggregate function will be "count" in our case

<!-- ![6](https://user-images.githubusercontent.com/86527202/144236288-34a567d5-a5e9-4a1e-b074-5ea633e799a3.png) -->

#### 7. Click on Save


![Screenshot 2022-09-09 at 1 03 49 PM](https://user-images.githubusercontent.com/86527202/189297619-4d5c815b-6c97-41fa-978e-9b645448e508.png)


<!-- ![7](https://user-images.githubusercontent.com/86527202/144236289-5872529a-ba47-428d-979e-fdefb92a1039.png) -->

Column `Employee Count` is populated with appropriate information
  
![Screenshot 2022-09-09 at 1 07 45 PM](https://user-images.githubusercontent.com/86527202/189297662-c7ff1e3e-eec7-4108-a089-6c945b90b867.png)


<!-- ![8](https://user-images.githubusercontent.com/86527202/144236291-52855f92-ad8b-4be1-aa98-b5cfdb1ee108.png) -->
