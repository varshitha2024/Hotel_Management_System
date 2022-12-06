Table:- admin
attributes:- admin_id, hotel_id, admin_name, admin_email, admin_password
pk:- admin_id
key:- hotel_id
fk:- hotel_id

INSERT INTO `admin` (`admin_id`, `hotel_id`, `admin_name`, `admin_email`, `admin_password`) VALUES
(1, 1, 'Jhon', 'jhon@gmail.com', '1234');





Table:- customer
attributes:- cust_id, cust_name, cust_email, cust_phone, cust_password
pk:- cust_id

INSERT INTO `customer` (`cust_id`, `cust_name`, `cust_email`, `cust_phone`, `cust_password`) VALUES
(1, 'Sudeep Manasali', 'sudeepmanasali@gmail.com', 974005462, '1234'),
(9, 'Mahesh', 'mahesh@gmail.com', 2147483647, '123456');





Table:- facilities
attributes:-facility_id, facility, facility_cost
pk:- facility_id


INSERT INTO `facilities` (`facility_id`, `facility`, `facility_cost`) VALUES
(5, 'WI-FI', 250),
(19, 'Writting Table', 100);



Table:- hotel
attributes:- hotel_id, hotel_name, hotel_addr, hotel_email, hotel_phone
pk:- facility_id

INSERT INTO `hotel` (`hotel_id`, `hotel_name`, `hotel_addr`, `hotel_email`, `hotel_phone`) VALUES
(1, 'The Royal HouseGuard s-star', '2 Whitehall Court, London SW1A 2EJ England', 'royalguards@gmail.com', '869745912');



Table:-reservation
attributes:- r_id, cust_id, room_id, booking_date, start_date, end_date,amount
pk:- r_id
fk:-  cust_id, room_id

Table:- room
attributes:- room_id, type_id, facility_id,status_id, hotel_id, images
pk:- room_id
fk:- type_id, facility_id,status_id, hotel_id



INSERT INTO `room` (`room_id`, `type_id`, `facility_id`, `status_id`, `hotel_id`, `images`) VALUES
(4, 1, 5, 2, 1, ' https://i.pinimg.com/236x/03/c3/3d/03c33d548b61a544ec8abeb76cfca3e4.jpg'),
(22, 2, 10, 2, 1, 'http://localhost:8000/profile/profile_1609312006994.jpg');





Table:- room_status
attributes:-  status_id, availability
pk:- status_id

INSERT INTO `room_status` (`status_id`, `availability`) VALUES
(2, 'AVAILABLE'),
(3, 'NOTAVAILABLE');





Table:-root_type
attributes:- type_id, type_name cost
pk:- type_id


INSERT INTO `room_type` (`type_id`, `type_name`, `cost`) VALUES
(1, 'AC', 1500),
(2, 'NON AC', 750);


Table:-servents
attributes:- s_id, hotel_id, s_name, s_phone, s_adhar, s_age, s_salary
pk:- s_id
fk:- hotel_id