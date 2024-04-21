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
- void `priorityChange` (airplane-order, tag of airplane having emergency)
  > Changes priority order of airplanes when called based on emergency
- bool `flightClearanceForAirspace` (airspace-traffic-details)
  > Permits or denies entry to airport airspace (Both arriving and departing planes)
- char `flightDockingClearance` (dock-details, plane-details)
  > Assigns entry into docks based on availability and size of plane
- bool `flightClearanceForRunways` (runway-traffic-details,boolean output of Airspace func, string value of Docking func)
  > (Arriving planes) Permits entry to land and assigns runways based on availability of runways and docks and proximity to assigned dock
  > (Departing planes) Permits entry to land and assigns runways based on availability of runways and airspace as well as proximity to current dock
- char `gateAssignment` (dock of plane location, gate locations and availability)
  > Finds and assigns closest available gate
  > calls bus if necessary
- void `FlightDetailsDisplay`(plane-details)
  > Displays the real time status(on-tie, delayed, cancelled) and information(destination, time, gate) of each flight
- int `AddFlight`(void)
  > Adds a flight to the list and returns flight number
- void `DeleteFlight`(flight number)
  > Deletes Flight fom the list
- void `ModifyFlight`(flight number)
  > Can modify details of an existing flight
- int `AddRunway`(location)
  > Adds runway to list and returns runway number
- void `DeleteRunway`(runway number)
  > Removes runway to the list
-



### User
- ticket-file `ticketBooking` (bool from domestic/internaltional)
   > Asks the user if their flight is domestic or international and uses it to add things like visa requirement to ticket booking,etc
   > Customer will input a lot of relevant info.
   > Different flight classes (first, business, prem-economy, economy ...)
- void `customerEnter` (user-entry-time?)
- char `parkingspot`(if coustomer used own car)
  > Returns parking spot
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
   > Forms a queue outside the gate, first come first board. After security checkin, come order decided how?\
- reordered-queue `priorityAssignment` (queue)
   > Certain people come front based on age, disabilities etc.
- rereordered-queue `reorderQueue` (reordered-queue)
   > The queue is split into 2 halves based on seat number for boarding and then boarding happens
- ? `boardingProcedure` (rereordered-queue)
  > Boarding happened, flight took off?, reduce count of people in airport.




- void `DeboardPlane`
  > passenger deboard plane based on the seat number
- int `LuggageArea`(void)
  > Returns baggage claim area number to a plane
- void `LuggageLoadAndCollect`(luggage stack, )
  > Put luggage on conveyour belt on last in first out basis and have passangers that have arrived collect them(delay random passangers in bathroom breaks)
- int `customs`(void)
  > Gives amount to be paid in tarriffs
- bool `immigration`(void)
  > checks immigration details and give approval/disapproval

