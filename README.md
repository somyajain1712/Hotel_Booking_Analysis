# Hotel_Booking_Analysis
Hotel booking analysis using HiveQL on cloudera


## About Data
1) hotel: hotel type(H1 = Resort Hotel or H2 = City Hotel) 
2) is_canceled: Value indicating if the booking was canceled (1) or not (0)
3) lead_time: Number of days that elapsed between the entering date of the booking into the PMS and the arrival date
4) arrival_date_year: Year of arrival date
5) arrival_date_month: Month of arrival date
6) arrival_date_week_number: Week number of year for arrival date
7) arrival_date_day_of_month: Day of arrival date
8) stays_in_weekend_nights: Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay at the hotel
9) stays_in_week_nights: Number of week nights (Monday to Friday) the guest stayed or booked to stay at the hotel
10) adults: Number of adults
11) children: Number of children
12) babies: Number of babies
13) meal: Type of meal booked. Categories are presented in standard hospitality meal packages: Undefined/SC – no meal package; BB – Bed & Breakfast; HB – Half board (breakfast and one other meal – usually dinner); FB – Full board (breakfast, lunch and dinner).
14) country: Country of origin. Categories are represented in the ISO 3155–3:2013 format.
15) market_segment: Market segment designation. In categories, the term “TA” means “Travel Agents” and “TO” means “Tour Operators”.
16) distribution_channel: Booking distribution channel. The term “TA” means “Travel Agents” and “TO” means “Tour Operators”.
17) is_repeated_guest: Value indicating if the booking name was from a repeated guest (1) or not (0)
18) previous_cancellations: Number of previous bookings that were cancelled by the customer prior to the current booking
19) previous_bookings_not_canceled: Number of previous bookings not cancelled by the customer prior to the current booking.
20) reserved_room_type: Code of room type reserved. Code is presented instead of designation for anonymity reasons.
21) assigned_room_type: Code for the type of room assigned to the booking. Sometimes the assigned room type differs from the reserved room type due to hotel operation reasons (e.g. overbooking) or by customer request. Code is presented instead of designation for anonymity reasons.
22) booking_changes: Number of changes/amendments made to the booking from the moment the booking was entered on the PMS until the moment of check-in or cancellation.
23) deposit_type: Indication on if the customer made a deposit to guarantee the booking. This variable can assume three categories: No Deposit – no deposit was made; Non Refund – a deposit was made in the value of the total stay cost; Refundable – a deposit was made with a value under the total cost of stay.
24) agent: ID of the travel agency that made the booking
25) company: ID of the company/entity that made the booking or responsible for paying the booking. ID is presented instead of designation for anonymity reasons.
26) days_in_waiting_list: Number of days the booking was in the waiting list before it was confirmed to the customer.
27) customer_type: Type of booking, assuming one of four categories: Contract - when the booking has an allotment or other type of contract associated to it; Group – when the booking is associated to a group; Transient – when the booking is not part of a group or contract, and is not associated to other transient booking; Transient-party – when the booking is transient, but is associated to at least other transient booking.
28) adr: Average Daily Rate as defined by dividing the sum of all lodging transactions by the total number of staying nights.
29) required_car_parking_spaces: Number of car parking spaces required by the customer
30) total_of_special_requests: Number of special requests made by the customer (e.g. twin bed or high floor)
31) reservation_status: Reservation last status, assuming one of three categories: Canceled – booking was canceled by the customer; Check-Out – customer has checked in but already departed; No-Show – customer did not check-in and did inform the hotel of the reason why.
32) reservation_status_date: Date at which the last status was set. This variable can be used in conjunction with the ReservationStatus to understand when was the booking canceled or when did the customer checked-out of the hotel.


## Steps to load the data into Hive

1. Used wget command to load the data into hive 
2. Removed header from the data by using 
    `tail -n 119389 hotel_bookings.csv > hotel_booking.csv` 
3. Loaded the file into HDFS using 
    `hdfs dfs -put hotel_booking.csv`
4. Created Schema into Hive
5. Created partioning on is_canceled, year and month
6. Inserted the data into Hive
