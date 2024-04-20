# Functionalities
- output `functionName` (input)
  > _description_

### Backend
- user-flow-change `userLogin` (void)
   > Admin or customer

### Staff
- struct `airplane`
  > Stores details of airplanes with the order signifying priority based on order of arrival
  > Stores details of airplanes with the order signifying priority based on order of departure(including all maintainance check details)
- void `priorityChange`(Airplane-order, tag of airplane having emergency)
  > Changes priority order of airplanes when called baded on emergency
- bool `flightClearanceForAirspace`(airspace-traffic-details)
  > Permits or denies entry to airport airspace(Both arriving and departing planes)
- char `flightDockingClearance`(dock-details, plane-details)
  > Assigns entry into docks based on availability and size of plane
- bool `flightClearanceForRunways`(runway-traffic-details,boolean output of Airspace func, string value of Docking func)
  > (Arriving planes) Permits entry to land and assigns runways based on availability of runways and docks and proximity to assigned dock
  > (Departing planes) Permits entry to land and assigns runways based on availability of runways and airspace as well as proximity to current dock
- char `gateAssignment`(dock of plane location, gate locations and availability)
  > Finds and assigns closest available gate
  > calls bus if necessary 

### User
- ticket-file `ticketBooking` (void)
   > Customer will input a lot of relevant info.
   > Different flight classes (first, business, prem-economy, economy ...)
- void `customerEnter` (user-entry-time?)
- bool `luggageScan` (customer-luggage-info)
   > Just a small independent function to improve simulation, no real use
   > How would he enter luggage content info? Should we make it random with less chances?
- luggage-queue `luggageCheckin` (void)
   > Ask customer for no. of luggages and each luggage's weight, check conditions.
   > The luggage should also be tagged with its customer details and flight details.
- boarding-pass `customerCheckin` (customer-info-from-ticket-booking)
   > Boarding pass has info like - Passenger details, assigned seat, assigned gate, luggage info ...
- stack `loadingLuggage` (luggage-queue)
   > Loads the luggage into airplane
- bool `securityCheckin` (void)
   > Ask customer for their hand baggage details, like is there sharp objects? etc., also check their boarding pass.
- queue `boardingQueue` (?)
   > Forms a queue outside the gate, first come first board. After security checkin, come order decided how?
- reordered-queue `priorityAssignment` (queue)
   > Certain people come front based on age, disabilities etc.
- rereordered-queue `reorderQueue` (reordered-queue)
   > The queue is split into 2 halves based on seat number for boarding and then boarding happens
- ? `boardingProcedure` (rereordered-queue)
  > Boarding happened, flight took off?, reduce count of people in airport.
