SELECT * FROM admin;


SELECT * FROM customer;

SELECT * FROM facilities;

SELECT * FROM hotel;

SELECT * FROM reservation;

SELECT * FROM room;

SELECT * FROM room_status;

SELECT * FROM room_type;


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


delete from hotelmanagement.room_type where type_id=1;


delete from customer where curs_id=2;	


delete from hotel where hotel_name like 'aa%';



delete from room where hotel_id=2;




ALTER TABLE `admin`
  ADD PRIMARY KEY (`admin_id`),
  ADD KEY `hotel_id` (`hotel_id`);

ALTER TABLE `customer`
  ADD PRIMARY KEY (`cust_id`);

ALTER TABLE `facilities`
  ADD PRIMARY KEY (`facility_id`);


ALTER TABLE `hotel`
  ADD PRIMARY KEY (`hotel_id`);


ALTER TABLE `reservation`
  ADD PRIMARY KEY (`r_id`),
  ADD KEY `cust_id` (`cust_id`),
  ADD KEY `room_id` (`room_id`);


ALTER TABLE `room`
  ADD PRIMARY KEY (`room_id`),
  ADD KEY `hotel_id` (`hotel_id`),
  ADD KEY `type_id` (`type_id`),
  ADD KEY `facility_id` (`facility_id`),
  ADD KEY `status_id` (`status_id`);

ALTER TABLE `room_status`
  ADD PRIMARY KEY (`status_id`);

ALTER TABLE `room_type`
  ADD PRIMARY KEY (`type_id`);


ALTER TABLE `servents`
  ADD PRIMARY KEY (`s_id`),
  ADD KEY `hotel_id` (`hotel_id`);

ALTER TABLE `admin`
  MODIFY `admin_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=2;

ALTER TABLE `customer`
  MODIFY `cust_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=10;

ALTER TABLE `facilities`
  MODIFY `facility_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=20;

ALTER TABLE `hotel`
  MODIFY `hotel_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=2;

ALTER TABLE `reservation`
  MODIFY `r_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=22;

ALTER TABLE `room`
  MODIFY `room_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=25;

ALTER TABLE `room_status`
  MODIFY `status_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=4;

ALTER TABLE `room_type`
  MODIFY `type_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=3;

ALTER TABLE `servents`
  MODIFY `s_id` int(11) NOT NULL AUTO_INCREMENT;

ALTER TABLE `admin`
  ADD CONSTRAINT `admin_ibfk_1` FOREIGN KEY (`hotel_id`) REFERENCES `hotel` (`hotel_id`) ON DELETE CASCADE;

ALTER TABLE `reservation`
  ADD CONSTRAINT `reservation_ibfk_1` FOREIGN KEY (`cust_id`) REFERENCES `customer` (`cust_id`) ON DELETE CASCADE,
  ADD CONSTRAINT `reservation_ibfk_2` FOREIGN KEY (`room_id`) REFERENCES `room` (`room_id`) ON DELETE CASCADE;

ALTER TABLE `room`
  ADD CONSTRAINT `room_ibfk_1` FOREIGN KEY (`hotel_id`) REFERENCES `hotel` (`hotel_id`) ON DELETE CASCADE,
  ADD CONSTRAINT `room_ibfk_2` FOREIGN KEY (`type_id`) REFERENCES `room_type` (`type_id`) ON DELETE CASCADE,
  ADD CONSTRAINT `room_ibfk_3` FOREIGN KEY (`facility_id`) REFERENCES `facilities` (`facility_id`) ON DELETE CASCADE,
  ADD CONSTRAINT `room_ibfk_4` FOREIGN KEY (`status_id`) REFERENCES `room_status` (`status_id`) ON DELETE CASCADE;


ALTER TABLE `servents`
  ADD CONSTRAINT `servents_ibfk_1` FOREIGN KEY (`hotel_id`) REFERENCES `hotel` (`hotel_id`) ON DELETE CASCADE;










