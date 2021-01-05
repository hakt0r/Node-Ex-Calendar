# Calendar Application

Seems like we just need two Databases,
Users and Events.

## Users

We'll probably need this, else we could write
a localStorage / frontend only app... this
is not what the client wants.

### Auth System

  - Register
  - Login
  - Unregister
  - Logout

### Data Model

Nothing to add we're fine because of our super smart
data-model for events :D

## Calendar

  - Upcoming Appontments
  - Reminders ?

### Database Structure

Events
    - Type ( ? )
    - Title
    - Color
    - DateTime (fixed)
  - Appointment
    - Address/
    - Notes
  - Reminder
    - Priority
    - DateTime (fixed)
    - Alarm
    - Notification
  - Todo
    - Priority
    - DateTime (due date)
    - DateTime (date of todo)

Try to simplify these aspects by using one Database,
reflecting the different functionalities in terms of
Item-Type and fields specific to different sub-functions.

### Data Model: Events

  - owners : [User] ( value := private event, null := public event )
  - participants : [User]
  - type : Enum : ['appointment'|'reminder'|'todo']
  - title : String
  - description : String (notes, links, free-text)
  - notification : String
  - color : String
  - date : Date
  - location : String
  - priority : Number | enum : ['low'|'average'|'high']
  - repeat : enum : ['daily'|'weekly'|'monthly'|'yearly']
  - alarm : Date

### Actions
  - List (many)
      - Filter events by any field
      - Protect private events !
  - Get (one)
      - Protect private events !
  - Create
      - Protect private events !
  - Edit
      - Protect private events !
  - Delete
      - Protect private events !
