const seatsContainer = document.getElementById('seats');
const bookedSeats = new Map(); // key = seat number, value = person name
const message = document.getElementById('message');

// Create 50 seats
for (let i = 1; i <= 50; i++) {
  const seat = document.createElement('button');
  seat.textContent = i;
  seat.className = "btn btn-outline-success col-2 fw-bold";
  seat.id = `seat-${i}`;
  seat.addEventListener('click', () => bookSeat(i));
  seatsContainer.appendChild(seat);
}

function bookSeat(number) {
  const name = document.getElementById('name').value.trim();
  const date = document.getElementById('date').value;

  // Validate input
  if (!name || !date) {
    message.textContent = "Please enter your name and date first.";
    message.className = "text-warning fw-bold text-center";
    return;
  }

  // Check if person already booked a seat
  for (const [seatNum, bookedBy] of bookedSeats.entries()) {
    if (bookedBy.toLowerCase() === name.toLowerCase()) {
      message.textContent = ` ${name}, you already booked seat ${seatNum}.`;
      message.className = "text-danger fw-bold text-center";
      return;
    }
  }

  // Check if seat is already booked
  if (bookedSeats.has(number)) {
    message.textContent = `Seat ${number} is already booked!`;
    message.className = "text-danger fw-bold text-center";
    return;
  }

  // Book the seat
  bookedSeats.set(number, name);
  const seatElement = document.getElementById(`seat-${number}`);
  seatElement.className = "btn btn-secondary col-2 fw-bold";
  seatElement.disabled = true;

  message.textContent = ` ${name}, you booked seat ${number} on ${date}.`;
  message.className = "text-success fw-bold text-center";
}
