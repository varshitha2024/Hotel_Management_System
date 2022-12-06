use hotelmanagement

CREATE TABLE `admin` (
  `admin_id` int(11) NOT NULL,
  `hotel_id` int(11) DEFAULT NULL,
  `admin_name` varchar(20) NOT NULL,
  `admin_email` varchar(20) NOT NULL,
  `admin_password` varchar(20) NOT NULL
)



CREATE TABLE `customer` (
  `cust_id` int(11) NOT NULL,
  `cust_name` varchar(20) NOT NULL,
  `cust_email` varchar(30) NOT NULL,
  `cust_phone` int(10) NOT NULL,
  `cust_password` varchar(20) NOT NULL
)

CREATE TABLE `facilities` (
  `facility_id` int(11) NOT NULL,
  `facility` varchar(20) NOT NULL,
  `facility_cost` float DEFAULT NULL
)


CREATE TABLE `hotel` (
  `hotel_id` int(11) NOT NULL,
  `hotel_name` varchar(45) NOT NULL,
  `hotel_addr` varchar(130) NOT NULL,
  `hotel_email` varchar(30) NOT NULL,
  `hotel_phone` varchar(15) NOT NULL
)


CREATE TABLE `reservation` (
  `r_id` int(11) NOT NULL,
  `cust_id` int(11) DEFAULT NULL,
  `room_id` int(11) DEFAULT NULL,
  `booking_date` date NOT NULL,
  `start_date` date NOT NULL,
  `end_date` date NOT NULL,
  `amount` float NOT NULL
)


CREATE TABLE `room` (
  `room_id` int(11) NOT NULL,
  `type_id` int(11) DEFAULT NULL,
  `facility_id` int(11) DEFAULT NULL,
  `status_id` int(11) DEFAULT NULL,
  `hotel_id` int(11) DEFAULT NULL,
  `images` varchar(3000) NOT NULL
)


CREATE TABLE `room_status` (
  `status_id` int(11) NOT NULL,
  `availability` varchar(20) DEFAULT NULL
)


CREATE TABLE `room_type` (
  `type_id` int(11) NOT NULL,
  `type_name` varchar(10) NOT NULL,
  `cost` float DEFAULT NULL
)


CREATE TABLE `servents` (
  `s_id` int(11) NOT NULL,
  `hotel_id` int(11) DEFAULT NULL,
  `s_name` varchar(20) NOT NULL,
  `s_phone` int(11) NOT NULL,
  `s_adhar` varchar(20) NOT NULL,
  `s_age` int(11) NOT NULL,
  `s_salary` float NOT NULL
) ;