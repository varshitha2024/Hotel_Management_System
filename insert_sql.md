INSERT INTO `admin` (`admin_id`, `hotel_id`, `admin_name`, `admin_email`, `admin_password`) VALUES
(1, 1, 'Jhon', 'jhon@gmail.com', '1234');


INSERT INTO `customer` (`cust_id`, `cust_name`, `cust_email`, `cust_phone`, `cust_password`) VALUES
(1, 'Sudeep Manasali', 'sudeepmanasali@gmail.com', 974005462, '1234'),
(4, 'Manas Adiki', 'manasadiki@gmail.com', 974004054, 'manas'),
(9, 'Mahesh', 'mahesh@gmail.com', 2147483647, '123456');


INSERT INTO `facilities` (`facility_id`, `facility`, `facility_cost`) VALUES
(5, 'WI-FI', 250),
(19, 'Writting Table', 100);

INSERT INTO `hotel` (`hotel_id`, `hotel_name`, `hotel_addr`, `hotel_email`, `hotel_phone`) VALUES
(1, 'The Royal HouseGuard s-star', '2 Whitehall Court, London SW1A 2EJ England', 'royalguards@gmail.com', '869745912');

INSERT INTO `room` (`room_id`, `type_id`, `facility_id`, `status_id`, `hotel_id`, `images`) VALUES
(4, 1, 5, 2, 1, ' https://i.pinimg.com/236x/03/c3/3d/03c33d548b61a544ec8abeb76cfca3e4.jpg'),
(15, 2, 8, 2, 1, 'http://localhost:8000/profile/profile_1609230934360.jpg'),
(22, 2, 10, 2, 1, 'http://localhost:8000/profile/profile_1609312006994.jpg');


INSERT INTO `room_status` (`status_id`, `availability`) VALUES
(2, 'AVAILABLE'),
(3, 'NOTAVAILABLE');



INSERT INTO `room_type` (`type_id`, `type_name`, `cost`) VALUES
(1, 'AC', 1500),
(2, 'NON AC', 750);