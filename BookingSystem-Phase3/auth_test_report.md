# Authorization test report

Items in **bold** indicate behaviour that deviates from the specification.

The id numbers given in paths such as `/reservation?id=1` are examples.

## Guest

### ✅ Can do

- Register new account (if over 15 years old) `/register` (spec 2)
- Login after registering `/login` (spec 2)
- View all reservations but not see who reserved `/` (spec 8)
- **Add new resource** `/resources` (spec 4)
- **View all users** `/api/users` (spec 9)

### ❌ Cannot do

- Update a resource `/resources?id=1` (spec 4)
- Delete a resource `/resources?id=1` (spec 4)
- Add a new reservation `/reservation` (spec 4/6)
- Update a reservation `/reservation?id=1` (spec 4)
- Delete a reservation `/reservation?id=1` (spec 4)


## Reserver

### ✅ Can do

- **Add a new resource** `/resources` (spec 4/6)
- Add a new reservation &ndash; **The system allows for creating reservations in the past but gives an error if the date is less than 15 years after the users given birthdate** `/reservation` (spec 6)
- Update a reservation `/reservation?id=1` (spec 6)
- **Update another user's reservation through browser** `/reservation?id=2` (spec 4)
- Delete a reservation `/reservation?id=1`
- **Delete another user's reservation by finding required information through API and sending a POST request** `/reservation`, `/api/reservations`, `api/users` (spec 4)
- **Update a resource** `/resources?id=1` (spec 4)
- **Delete a resource (if no reservations are connected to it)** `/resources?id=1` (spec 4)
- **View all users** `/api/users` (spec 9)


### ❌ Cannot do

- Delete a resource if reservations are connected to it `/resources?id=1` (spec 4)

## Administrator

### ✅ Can do

- Add a new resource `/resources` (spec 4)
- Add a new reservation `/reservation` (spec 4)
- Update a resource `/resources?id=3` (spec 4)
- Delete a resource (if no reservations are connected to it) `/resources?id=3` (spec 4)
- Update a reservation `/reservation?id=3` (spec 4)
- Delete a reservation `/reservation?id=3` (spec 4)
- Update another user's reservation through the browser `/reservation?id=4` (spec 4)
- Delete another user's reservation through the browser `/reservation?id=4` (spec 4)
- **View all users** `/api/users` (spec 4)


### ❌ Cannot do

- Delete a resource if reservations are connected to it `/resources?id=3` (spec 4)