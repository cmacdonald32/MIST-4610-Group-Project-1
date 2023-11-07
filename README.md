# MIST-4610-Group-Project-1

# Team Name:

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

![Image 11-7-23 at 5 09 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/d82734fa-843d-4fac-973e-730913a02203)
![Image 11-7-23 at 5 17 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/eaf89a33-8388-4497-adfc-b307059b3f87)
![Image 11-7-23 at 5 17 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/e1f69f72-328a-4562-88e7-6f97fd840da5)
![Image 11-7-23 at 5 18 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/c7f816ba-cdc6-4a79-a9f8-3552a99aa65a)
![Image 11-7-23 at 5 18 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/39b69534-d8a9-4802-bda2-609faa00b3e8)
![Image 11-7-23 at 5 20 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/891c09c6-34ea-4bbf-ba74-ab5a8de03e3a)
![Image 11-7-23 at 5 21 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/08e7b077-c306-4fd5-8e4e-1a901923d3d5)
![Image 11-7-23 at 5 22 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/0773ced4-2379-4266-ba89-d01834f4e710)
![Image 11-7-23 at 5 22 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/17c91a72-7d8c-4840-a2b4-7b2eb944c282)
![Image 11-7-23 at 5 23 PM](https://github.com/cmacdonald32/MIST-4610-Group-Project-1/assets/148258205/b4208107-34a8-4b05-871c-a6d09b05c79b)








# Database Information:
