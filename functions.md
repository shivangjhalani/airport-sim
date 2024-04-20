# Functionalities
- output `function` (input)
  > _description_

### Backend
1. user-flow-change `user_login` (void)
   > Admin or customer

### User
1. ticket-file `ticket_booking` (void)
   > Customer will input a lot of relevant info.
   > Different flight classes (first, business, prem-economy, economy ...)
2. bool `security_luggage_check` (customer-luggage-info)
   > Just a small independent function to improve simulation, no real use
   > How would he enter luggage content info? Should we make it random with less chances?
4. stack `luggage_checkin` (void)
   > Ask customer for no. of luggages and each luggage's wright, check conditions.
5. boarding-pass `customer_checkin` (customer-info-from-ticket-booking)
   > Boarding pass has info like - Passenger details, assigned seat, luggage info ...
6. 

### Admin
