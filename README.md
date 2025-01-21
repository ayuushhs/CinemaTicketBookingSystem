# Movie Ticket Booking System

## Project Description
This project is a simple **Movie Ticket Booking System** built using HTML, CSS, and JavaScript. The system allows users to select a theatre, movie, date, time, screen type, and food options for their booking. Users can view a detailed summary of their booking and cancel it if needed.

## Features
- **Select Theatre**: Choose a theatre from the available options (PVR, INOX, CINEPOLIS).
- **Select Movie**: Pick a movie from the available list (Interstellar, Donkey Kong, Revenant).
- **Select Date and Time**: Specify the date and time for the booking.
- **Screen Options**: Choose from VIP, Gold, or Regular screen types with different prices.
- **Food Options**: Add or remove food items (e.g., popcorn) and view the total cost.
- **Booking Details**: View a summary of the booking, including a unique Booking ID.
- **Cancel Booking**: Cancel the booking and reset the form.

## Technologies Used
- **HTML**: For structuring the webpage.
- **CSS**: For styling the webpage and improving the user interface.
- **JavaScript**: For interactive functionality and calculations.

## How to Use
1. Clone or download the project files.
2. Open the `index.html` file in a web browser.
3. Follow these steps:
   - Select a theatre, movie, date, and time.
   - Choose a screen type by clicking one of the available buttons.
   - Add food items using the "Add" button and adjust the count with the "Remove" button.
   - Click the **Book Ticket** button to confirm the booking.
   - View the booking summary in the booking details box.
   - If needed, cancel the booking using the **Cancel Booking** button.

## Code Highlights
### Booking ID Generation
The `generateBookingId` function creates a unique 6-digit booking ID for each transaction:
```javascript
function generateBookingId() {
    return Math.floor(100000 + Math.random() * 900000);
}
```

### Total Calculation
The total cost is dynamically calculated based on the screen type and food items:
```javascript
function updateTotal() {
    totalAmount = screenPrice + foodPrice;
    document.getElementById("total").innerText = `Total: $${totalAmount}`;
}
```

### Booking Confirmation
When a user clicks the **Book Ticket** button, all selected details are displayed in a formatted box:
```javascript
function bookTicket() {
    const theatre = document.getElementById("theatre").value;
    const movie = document.getElementById("movie").value;
    const date = document.getElementById("date").value;
    const time = document.getElementById("time").value;

    if (!theatre || !movie || !date || !time || !selectedScreen) {
        alert("Please fill out all fields and select a screen.");
        return;
    }

    bookingId = generateBookingId();
    document.getElementById("booking-id").textContent = bookingId;
    document.getElementById("selected-theatre").textContent = theatre;
    document.getElementById("selected-movie").textContent = movie;
    document.getElementById("selected-date").textContent = date;
    document.getElementById("selected-time").textContent = time;
    document.getElementById("selected-screen").textContent = selectedScreen;
    document.getElementById("selected-food").textContent = `${foodCount} Popcorn`;
    document.getElementById("final-total").textContent = `$${totalAmount}`;

    document.getElementById("booking-box").style.display = "block";
}
```

### Cancel Booking
The **Cancel Booking** button clears all selected details and resets the form:
```javascript
function cancelBooking() {
    if (confirm("Are you sure you want to cancel this booking?")) {
        document.getElementById("booking-box").style.display = "none";
        bookingId = null;
        resetForm();
    }
}
```

## Future Improvements
- Add more food options and dynamic pricing.
- Integrate with a backend system for real-time bookings.
- Include seat selection and availability.
- Provide payment gateway integration.

## License
This project is free to use and modify for educational or personal purposes.

## Author
**Ayush**

