# Laurea Booking App Documentation
Welcome to our booking app, designed for the [Laurea Digital Living Lab](https://www.laurea.fi/en/research/digital-living-lab/). This app is designed so that users within the Laurea ecosystem can browse items in the lab checkout items for use in their studies and research. It’s also intended as a canvas app for administrators of the lab, allowing them to add/edit/remove items, adjust their availability, as well as edit and remove individual bookings. 

## Credit
This application is a group project for the Modeling a Digital Service course at Laurea University of Applied Sciences and is brought to you by:

- [Kimberly Ruohio](https://github.com/kimintime)
- [Eshaq Safi](https://github.com/esafi23)
- [Salla Seppälä](https://github.com/sasepp)

The project is currently in its second iteration, and full credit goes to the team who came before us.

## Features
When the project fell into our hands it had the following features:

- Browsing items
- Viewing individual items
- Making a booking landing the user on a success page
- The required Equipment and Bookings list

In our iteration we added:

- User authentication and authorization
- User roles (admin and client)
- The User list that goes with the above
- Search and sort of items
- Showing item availability
- Automated setting of item availability at booking
- Showing own bookings
- Showing admin all bookings
- Allowing admin edit of bookings
- Allowing admin edit and adding items
- Item return is handled through the admin bookings editing process

### Future ideas

- A graphical calendar where the user can tap the day, and it shows the block of time selected.
- Allow setting different default booking durations for given items
- Allow the user to edit or remove future bookings
- Automated mail confirmation
- Automated return process
- Automated archiving of past bookings

## How to Use
Whether a normal user or admin, you’re greeted with the same front page. The login system is connected to your Laurea account, so it should always be you, but there is the option to logout and try again. Tap on the grey dialogue box showing your name and profile picture to continue into the booking system.

### Browse Items
Once inside the booking system, you’re presented by the main screen, from where you should see the product listing. At the top of the listings, there’s a search bar, and the ability to sort items alphabetically, as well as refresh the list.

#### Admin Mode
The admin has the ability to add items by tapping on the + button, which will add a new item to the Equipment list. The Add Items screen can also accept image uploads. The item can be edited or deleted anytime through its individual page.

---

### Navbar
At the bottom of every screen is the ability to navigate between the items list (Home icon), your bookings (Calendar icon), and back to login (Person icon).

---

### Item Description
Taping on a given item takes you to that item’s description page, where you can learn more about it, check its availability, and book the item. If the item is not available, you can see the due date for its expected return.

#### Admin Mode
Additionally, the admin will be able to set availability of an item, by selecting yes or no, and tapping the checkbox icon. Yes means the item is available, No means it isn’t. There’s a few use cases for this. For example, an item may be out of service, and needs to be set as unavailable to prevent checking out. There might have been an error where an item is returned but was not set back to available, or there might be some other unforeseen circumstance, but this is why we have an admin mode.

Tap the pencil icon to edit the item, and delete to delete the item, updating the Equipment list.

##### Note!
For both client and admin, the booking button disappears of an item is unavailable. Admin cannot check out an item that is unavailable, but can manually set availability.

---

### Booking an Item
When you tap the Book button on the Item Description screen, you’re taken to the Booking screen. Booking defaults to 14 day blocks of time, and is not editable at this time. You may choose the time of start, and therefore the time that it’s due, by typing on the Calendar drop-down, selecting the date, and then selecting the time from the dropdown below it. Once you’ve selected a time suitable for you, tap on the Book button to book the item. You’re directed to a screen informing you of a successful booking, and then directed to your own bookings.

#### Admin Mode
When booking in admin mode, you are taken directly to editing that booking. The pencil icon allows you to edit that booking, while the trash can icon allows the admin to remove the booking. As the booking disappears at that point, we recommend setting the item back to available before deleting the booking. If you forget though, you can always go find the item and set it back to available on its description page. Admins are not limited by 14 days, and may extend or shorten bookings, or delete any booking made in the app. Tap on the Own Bookings button to see all of your own current bookings. 

---

#### About Returns
Setting an item as Available, either in the Item Page or in the Booking is essentially a return. It’s up to the administration as to how to handle returns, but our recommendation would be to archive old bookings, and delete them from the Canvas app. The implications of storing all bookings and sorting through all of them from the app would be to slow down the app, and would not be best practice, but it is up to the admins.

---

### Bookings
The list of your own bookings is not editable, but they should all be on this list. To modify a booking, contact the administrators. If you’re not seeing your bookings, tap the  refresh icon before contacting the administrators.

#### Admin Mode
The initial view of your own bookings is much the same, however tap the Admin bookings button to view and edit all bookings in the system. You can browse the bookings by scrolling through, but to edit a booking, select it from the dropdown menu. When editing a booking, you might need to navigate away from the screen and back to, if the page is not showing an update, or appears frozen during update, but you should find that updating and deleting bookings works as expected.

## About Admin Mode
Admins are recognized according to the UserRoles list. To add or remove an admin, the list needs to be manually updated.

## Setting up the app for your own use

### Sharepoint Lists
In order for the app to run, you need to create Sharepoint lists for UserRoles, Equipment, and bookings. (List names are case sensitive)

The bookings list contains the following columns:
- id - Single line of text
- itemName (Title) - Single line of text (required)
- Start Date - Date and Time
- End Date - Date and Time
- User - Person or Group

The Equipment list contains the following columns:
- Title - Single line of text (required)
- Image - Thumbnail
- Description - Multiple lines of text
- Website/Manual - Hyperlink or Picture
- isAvailable - Yes/No

The UserRoles list contains the following columns:
- Title - Single line of text (required)
- AdminName - Person or Group

---

### Running the application for your own purposes
As user login, and user object in the booking process is connected to Laurea’s administrative setup, I’m sure there will be some tweaking to run this code for your own purposes, and it’s not something we can support.
