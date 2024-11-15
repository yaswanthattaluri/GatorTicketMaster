# Seat Reservation System

## Overview
This project is a Python-based seat reservation system with a priority waitlist. It allows users to reserve, cancel, and update their seat reservation priorities. If seats are unavailable, users are added to a waitlist, and seats are allocated based on priority when available.

## Features
- **Initialize Seats**: Set up an initial number of available seats.
- **Reserve Seats**: Reserve a seat for a user, considering their priority level.
- **Cancel Reservations**: Cancel a user's reservation and reassign the seat to the next waitlisted user if available.
- **Priority Update**: Adjust the priority of a user in the waitlist.
- **Add Seats**: Increase the number of available seats and assign them to waitlisted users if needed.
- **Release Seats**: Release seats within a specified user ID range.

## Project Structure
- **gatorTicketMaster.py**: Main script to run the seat reservation system. Processes commands like initialization, reservation, cancellation, and waitlist management.
- **Reservation_controller.py**: Handles reservation and waitlist management, interacting with other components to allocate seats and update priorities.
- **Binary_Min_Heap.py**: Implements a priority queue with a binary min-heap, managing waitlisted users by priority.
- **Red_Black_Tree.py**: Implements a Red-Black Tree for efficiently storing and sorting reservations by user ID.
- **seat_allocation_manager.py**: Interface class for managing seat reservations, cancellations, and updates.
- **seats.py**: Defines the `Seat` class, representing each seat with attributes like seat number and reservation status.
- **users.py**: Defines the `User` class with user ID and priority level, allowing updates and comparisons based on priority.

## Setup and Execution

1. **Initialize and Run the System**:
   Use the following command to run the program with an input file:
   ```bash
   python3 gatorTicketMaster.py <input_file>
   ```

   
   
2. **Command Guide**:
- Initialize(<seat_count>): Sets up the initial number of seats.
- Reserve(<user_id>, <priority>): Attempts to reserve a seat for the user with the specified priority.
- Cancel(<seat_id>, <user_id>): Cancels the reservation for the specified seat and user.
- UpdatePriority(<user_id>, <new_priority>): Updates the waitlist priority for the specified user.
- AddSeats(<count>): Adds more seats and assigns them to waitlisted users if available.
- PrintReservations: Outputs the list of current reservations.
- ReleaseSeats(<user_id_start>, <user_id_end>): Releases seats for users within the given ID range.
- Quit: Terminates the program

**Example**
Input file (test5.txt):
 ```bash
Initialize(5)
Available()
Reserve(1, 1)
Reserve(2, 1)
Cancel(1, 1)
Reserve(3, 1)
PrintReservations()
Quit()
 ```


Expected Output (test5_output_file.txt):
 ```bash
5 Seats are made available for reservation
Total Seats Available : 5, Waitlist : 0
User 1 reserved seat 1
User 2 reserved seat 2
User 1 canceled their reservation
User 3 reserved seat 1
Seat 1, User 3
Seat 2, User 2
Program Terminated!!


 ```
