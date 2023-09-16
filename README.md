classDiagram
  class User {
    +Username: String
    +Password: String
    +Email: String
    +FirstName: String
    +LastName: String
    +MakeReservation(): void
    +CancelReservation(): void
  }

  class Hotel {
    +HotelName: String
    +Location: String
    +NumberOfRooms: int
    +Room[] Rooms
  }

  class Room {
    +RoomNumber: int
    +RoomType: String
    +PricePerNight: float
    +IsAvailable: boolean
    +Reserve(): void
    +CancelReservation(): void
  }

  class Reservation {
    +ReservationID: int
    +CheckInDate: Date
    +CheckOutDate: Date
    +TotalPrice: float
    +IsConfirmed: boolean
    +ConfirmReservation(): void
    +CancelReservation(): void
  }

  User -- Hotel : Makes Reservation
  User -- Reservation : Makes Reservation
  Hotel "1" -- "*" Room : Contains
  Room "0..1" -- "1" Reservation : Reserved In
