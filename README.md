# MIST-4610-Group-Project-1

# Team Name:
Team Query Wizards

# Team Members:
1. Conner MacDonald [@cmacdonald32](https://github.com/cmacdonald32)
2. Drew Kotanian [@drewkotanian](https://github.com/drewkotanian)
3. Luke Mulert [@lukemulert03](https://github.com/lukemulert03)
4. Patrick Gray [@pfg52386](https://github.com/pfg52386)

# Problem Description:
Our task is to model and build a relational database for the general operations of a golf club company. The primary entity is the golf resort, each physical golf course that the company owns and operates at different locations around the company (EX -> The Trump National Golf Resorts). The courses are run along with luxuries such as lessons, tee times, tournaments, retail opportunities, etc... that are offered to the guests that join or tag along with members of these clubs. We would like to model these relationships, input sample data, and populate each entity/attribute in an accurate manner. Lastly, we would like to write functional queries based on this database that provides important information for the Golf Resort and its daily operations.

# Data Model:
Our data model is designed around the framework of a hypothetical Golf Country Club Chain, which encompasses various golf courses operated by our company. At the core of this model is the GolfCourse entity, representing the individual golf courses spread across the country. Within these courses, a diverse community of members exists, and each member has the potential to be affiliated with multiple golf courses. We've established a many-to-many relationship between the GolfCourse and Member entities, utilizing the junction table Tournament_has_Member to facilitate this connection.

Members also maintain lists of approved guests who can access our facilities. These guests form one-to-many relationships with both the Member and GolfCourse entities, as each guest can associate with a single member and access a single golf course.
Moreover, members actively participate in various tournaments, and our data model accommodates this by establishing a many-to-many relationship between the Tournament and Member entities through the Tournament_has_Member junction table. In this context, we also identify tournament winners, who are recognized for each tournament.

Within the golf courses themselves, we've integrated entities like Finances and ProShop, each linked to GolfCourse through one-to-one relationships. Finances house financial reports, while the ProShop entity contains pertinent information about each course's pro shop, which is owned by the respective course. Furthermore, the ProShop entity maintains a many-to-many relationship with the ProShopInventory entity, allowing the overall inventory to seamlessly integrate with the pro shops of each golf course, facilitated by the junction table ProShopInventory_has_ProShop.

Additionally, every golf course operates with a schedule of tee times and offers golf lessons on a daily basis. These components are linked to the GolfCourse entity through one-to-many relationships.

In terms of amenities, every golf course includes a restaurant, and we've represented this relationship with a one-to-one connection between the Restaurant and GolfCourse entities. Furthermore, each of these facilities, including the restaurant, pro shop, and golf lessons, relies on employees for their daily operations. Employees maintain one-to-many relationships with the Restaurant, GolfCourse, and ProShop entities because many employees are involved in the various aspects of these facilities. However, the GolfLesson entity is connected to the Employee in the opposite direction, as only one employee (the Golf Instructor) can be associated with a specific golf lesson, although they may conduct multiple lessons.



![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/52ac3594-baad-4bd7-a52d-7833570aaf8c)

# Data Dictionary: 
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/2e253ef1-58a0-4c68-b735-bc8083c2d6ea)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/2075fd81-3099-4b7d-ba0a-c140d759e417)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/0bc39f59-e491-4428-ad95-4c4087447f24)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/965264a5-5685-404f-ab01-64ac5d9a908e)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/9529a9f5-7ba7-485d-bc39-aaf9046afbde)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/e93d1ac6-0681-4372-b753-c81a298ade91)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/b3d2ce22-483a-44d1-acff-26281812fe62)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/e2d376e7-cdd0-4d84-b722-d4ea5dd7581d)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/97a01cbb-b37f-44d8-81a3-597fa6de0d33)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/3226bc62-bc43-41fc-bf8d-b23bd89f4d5c)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/df38f8e8-f7c5-44ee-b222-ff6915fccb4b)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/357995d5-31a5-4252-8c57-091d3ffa64e0)
![image](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148248175/95357a88-fbd0-4b11-b582-1ba6c0acdbb7)

# Queries:
![Image 11-7-23 at 5 33 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/4f3409dc-8e6b-458f-b977-03cf19b543ca)

1. Query 1 calculates the total amount paid for each golf course and its location by joining the 'Finances' and 'GolfCourse' tables on the 'idFinances' and 'Finances_idFinances' columns, respectively. It then groups the results by 'courseName' and 'location'. The HAVING clause filters out results where the total amount paid is not greater than $1,000. The query provides a summary of the total amounts paid for each golf course in specific locations, highlighting those with substantial financial activity.
![Image 11-7-23 at 5 09 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/d82734fa-843d-4fac-973e-730913a02203)
Query 1 allows managers to see the amount of money spent on operations where the sum is over a thousand dollars at each Golf Course and it's respective location. The two golf courses returned, Oakwood and Sunset, show that they are spending a fair amount of money more than the other courses within the resort. As a result, this query allows for managers to see where higher amounts of money are spent at each location, helping them better track their financial records and allocate resources in a more efficient manner.

2. Query 2 retrieves data related to the ProShop's inventory. It combines information from the 'ProShop,' 'ProShopInventory_has_ProShop,' and 'ProShopInventory' tables. The query selects the 'idProShop,' 'ProShopAddress,' 'productName,' 'price,' and 'AmountinStock' columns. It filters the results to include items with a price exceeding $25 and an inventory level exceeding 20. This query allows you to view and manage inventory items in the ProShop, focusing on those that meet specific price and stock criteria.
![Image 11-7-23 at 5 17 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/eaf89a33-8388-4497-adfc-b307059b3f87)
Query 2 allows managers to see products in their pro shop inventory where the price is greater than 20 dollars, and the quantity in stock is greater than 20. The data returned shows items at four of our locations that exceed the price and inventory constraints listed in the query. Therefore, this allows managers to properly record sales. This helps give them a better idea when restocking is necessary, as well as how well an item sells based off price, helping each location operate in a lucrative manner.

3. Query 3 retrieves information about restaurants with fewer than 30 reservations. It specifically selects the 'idRestaurant', 'restaurantName', 'reservations', and 'occupancy' columns from the Restaurant table. The query applies a filter to only include restaurants with reservations below 30. Additionally, it uses a subquery to identify restaurants where employees' performance is considered "Excellent" based on a regular expression match. In summary, the query lists restaurant details for those with limited reservations and excellent employee performance.
![Image 11-7-23 at 5 17 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/e1f69f72-328a-4562-88e7-6f97fd840da5)
Query 3 allows managers to see which restaurants have reservations below 30, paired with each maximum occupancy. The restaurants listed all have reservations far below their occupancy numbers, signifying that they should increase the amount of reservations for more business. As a result, this data can help managers identify which locations lack business and need extra help for a better business model.

4. Query 4 retrieves the names and phone numbers of guests who have an active membership status. It combines the first and last names of the guests into a single 'GuestName' column and includes their phone numbers in the 'GuestPhoneNumber' column. This query uses a subquery to check the existence of active members and ensures that only guests with active memberships are included in the results.
![Image 11-7-23 at 5 18 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/c7f816ba-cdc6-4a79-a9f8-3552a99aa65a)
Query 4 helps managers see which members of the resort have active memberships, along with their phone number. This data helps give them a better idea of membership turnover as well as how to accurately bill active and inactive memberships. Furthermore, with member contacts provided, managers can easily communicate with members to discuss their future plans with the club. This is very beneficial in keeping track of the success of their locations, given that members with an inactive status are likely unsatisfied with their services.

5. Query 5 retrieves a list of golf lessons that meet specific criteria. It selects the 'idGolfLesson', 'lessondate', 'Instructor', 'student', and 'price' columns from the GolfLesson table. The query filters the results to include only lessons with a price less than $75 and where the 'lessondate' is before June 1, 2023. Additionally, it uses a subquery to ensure that these lessons are associated with golf courses by comparing their 'GolfCourse_idGolfCourse' with the 'idGolfCourse' in the GolfCourse table. In essence, the query provides information about affordable golf lessons conducted before a specific date, taking into account their connection to golf courses.
![Image 11-7-23 at 5 18 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/39b69534-d8a9-4802-bda2-609faa00b3e8)
Query 5 helps managers keep track of lessons provided at each golf course, along with the date, instructor, student, and price. This data shows lessons that took place prior to June 1st, allowing for managers to access transactions with clients in the necessary time period. As a result, they can use this information to schedule future lessons in an organizational manner. This can also greatly help instructor/student relations as well, so they can see which of the employees have worked with clients previously. This can help improve the overall experiences that the club provides.

6. Query 6 retrieves the name of the 'Head Chef' and the 'restaurantName' for a specific restaurant, 'The Rustic Spoon.' It achieves this by combining data from the 'Employee' and 'Restaurant' tables where the 'Restaurant_idRestaurant' in the 'Employee' table matches the 'idRestaurant' in the 'Restaurant' table. Additionally, it filters the results to include only those with the role 'Head Chef.' The query utilizes the CONCAT function to display the full name of the head chef by combining their first and last names. The results provide information about the head chef and the restaurant where they work, specifically for 'The Rustic Spoon.'
![Image 11-7-23 at 5 20 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/891c09c6-34ea-4bbf-ba74-ab5a8de03e3a)
Query 6 allows managers to quickly find employees and their specific roles for any restaurant at their courses. In this example a manger could identify the Head Chef of the restaurant ‘The Rustic Spoon’ as John Servine. This query is useful to managers for many reasons. It can allow managers to see the amount of staff they have at each position and at each restaurant, which is especially important for hiring purposes. 

7. Query 7 calculates the total quantity of specific items available in the Pro Shop's inventory. It uses a CASE statement to sum the quantities of three products: 'Golf Tees,' 'Golf Umbrella,' and 'Golf Shorts.' The query filters the ProShopInventory table to include only these products. The result provides the sum of available 'Golf Tees,' 'Golf Umbrellas,' and 'Golf Shorts' in stock as 'GolfTeesInStock,' 'GolfUmbrellasInStock,' and 'GolfShortsInStock,' respectively.
![Image 11-7-23 at 5 21 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/08e7b077-c306-4fd5-8e4e-1a901923d3d5)
Query 7 allows managers to see the inventory quantity of specific products within their pro shop. Managers can use this query for inventory management, helping them stay on top of their count for each product. This will ensure managers can order replacement inventory before a given product sells out.

8. Query 8 retrieves all records from the 'TeeTime' table where the 'date' is set to '2023-01-01' and the 'time' follows the format of a 12-hour clock in the morning ('AM') with hours ranging from 00 to 11 and minutes from 00 to 59. It filters and retrieves tee times scheduled for the morning of January 1, 2023.
![Image 11-7-23 at 5 22 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/0773ced4-2379-4266-ba89-d01834f4e710)


9. Query 9 retrieves and groups data from the 'GolfCourse' table based on 'location' and 'availability.' It does this by joining the 'Guest' and 'Restaurant' tables with the 'GolfCourse' table. The result is a summary of golf course locations and their availability, allowing users to see how many courses are available in different locations. This query provides an overview of golf course data, making it easier to analyze and compare golf course options based on location and availability.
![Image 11-7-23 at 5 22 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/17c91a72-7d8c-4840-a2b4-7b2eb944c282)
10. Query 10 retrieves tournament information from the 'Tournament' table. It filters and retrieves records with the 'tournamentName' and 'tounamentDate' columns for tournaments that occurred after the latest 'The Spring Open' tournament. It uses a subquery to find the maximum date of 'The Spring Open' tournaments and compares it to the 'tounamentDate' in the main query. The query effectively returns tournament details for events that happened after the last 'The Spring Open' tournament, allowing you to track subsequent tournaments beyond that reference point.
![Image 11-7-23 at 5 23 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/b4208107-34a8-4b05-871c-a6d09b05c79b)








# Database Information:
Name of the database: cs_g3p1
