# Functionalities
- output `functionName` (input)
  > _description_

## Backend
- user-flow-change `userLogin` (void)
  > Admin or customer

## Departure
### Customer
- ticket-file `ticketBooking` (bool from domestic/internaltional)
  > Asks the user if their flight is domestic or international and uses it to add things like visa requirement to ticket booking,etc
  > Customer will input a lot of relevant info.
  > Different flight classes (first, business, prem-economy, economy ...)
- char `parkingspot`(if coustomer used own car)
  > Returns parking spot
- void `customerEnter` (void)
  > Just a filler function to basically start simulation
- customer-luggage-content-info `luggageSecurityScanInfo` (void)
  > Will be called by customer enter
- customer-luggage-info `luggageCheckinInfo` (void)
  > Ask customer for no. of luggages and each luggage's weight, check conditions.
- answer-to-questions `securityCheckinEnquiry` (void)
  > Ask stuff like name, where going, is there anything in your pockets? (frisking emulation)
- bool `getAskedEmergencySeat` (void)
  > Say yes or no if willing to perform emergency actions if you are on emergency seat

### Staff
- bool `luggageSecurityScan` (customer-luggage-info)
  > How would he enter luggage content info? Should we make it random with less chances?
- luggage-queue `luggageCheckin` (luggage-info)
  > The luggage will be tagged with its customer details and flight details.
- boarding-pass `customerCheckin` (customer-info-from-ticket-booking)
  > Boarding pass has info like - Passenger details, assigned seat, assigned gate, luggage info ...
- stack `loadingLuggage` (luggage-queue)
  > Loads the luggage into airplane
- bool `securityCheckin` (ask-customer-questions)
  > Ask customer for their hand baggage details, like is there sharp objects? etc., also check their boarding pass.
- queue `boardingQueue` (?)
  > Forms a queue outside the gate, first come first board. After security checkin, come order decided how?\
- reordered-queue `priorityAssignment` (queue)
  > Certain people come front based on age, disabilities etc.
- split-queue `splitQueue` (reordered-queue)
  > The queue is split into based on seat number for boarding
- bool `isBusRequired` (plane-gate-no)
  > If no gate assigned to plane, call bus.
- bus-gate `callBus` (is-bus-required)
  > Returns gate number of bus.
- cut-queue `boardBus` (split-queue)
  > Run this function many times till all passengers dropped off and keep decreasing the passneger queue size as bus takes specified amount away.- int `addRunway` (location)
  > Adds runway to list and returns runway number
- void `deleteRunway` (runway number)
  > Removes runway to the list
- void `emergencyBreifing` (void)
  > Will be called in flow
- change-seats `changeSeatsForEmergency` (void)
  > Ask customer if they are wiling to perform emergency actions
- `snacksFunction`?

## Arrival
### Customer
- queue `deboardPlane` ()
  > passenger deboard plane based on the seat number
- int `luggageArea` (void)
  > Returns baggage claim area number to a plane
- queue-of-washroom-people `washroomTime` (void)
  > Asks user if they wanna go washroom
- circularly-linked-list `luggageLoad` (luggage stack)
  > Put luggage on conveyour belt on last in first out basis and have passangers that have arrived collect them
  > keep rotating the belt
- struct-customer-and-luggage `collectLuggage` (luggage-circularly-linked-list, deboarded-queue, washroom-break-people)
  > Match circularly linked list and customer queue, if position of owner and bag same, pick it up.
  > Washroom break people come late and randomly get in middle of circularly linked list of people.
- int `customs`(void)
  > Gives amount to be paid in tarriffs
- bool `immigration`(void)
  > checks immigration details and give approval/disapproval
- void `customerExit`(void)
- int `Taxi`(void)
  > returns Taxi plate number if needed

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

##### Staff seperate functions
- void `flightDetailsDisplay` (plane-details)
  > Displays the real time status(on-tie, delayed, cancelled) and information(destination, time, gate) of each flight
- int `addFlight` (void)
  > Adds a flight to the list and returns flight number
- void `deleteFlight` (flight number)
  > Deletes Flight fom the list
- void `modifyFlight` (flight number)
  > Can modify details of an existing flight
- int `addRunway` (location)
  > Adds runway to list and returns runway number
- void `deleteRunway` (runway number)
  > Removes runway from the list
- int `addGate` (void)
  > Adds gate to list and returns gate number
- void `deleteGate` (gate number)
  > Removes gate from the list




