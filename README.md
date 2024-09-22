# Hospital Management System

The code I have provided is a Java-based implementation of a simple Hospital Management System that uses MySQL for database management. The application provides essential functionalities such as adding patients, viewing patients and doctors, and booking appointments between patients and doctors. Here's an explanation of the key components of this system:

## Package Structure and Class Overview
The code is organized into three main classes within the HospitalManagementSystem package: Patient, Doctor, and HospitalManagementSystem. Each class plays a specific role in managing the hospital's operations.

### Patient Class: 
This class handles all operations related to patients, such as adding new patients and viewing the list of existing patients. It connects to the database using a Connection object and uses PreparedStatement to execute SQL queries. It also validates patient information by checking if a patient exists in the database using getPatientById().
### Doctor Class: 
This class manages operations related to doctors, such as viewing the list of doctors and verifying doctor details. The viewDoctors() method retrieves all doctors from the database, and the getDoctorById() method checks if a doctor exists based on their ID.
### HospitalManagementSystem Class:
This is the main class that serves as the entry point for the application. It sets up the database connection, initializes instances of the Patient and Doctor classes, and handles the application's user interface using a command-line interface. The class offers options to add patients, view patients, view doctors, and book appointments.

## Database Connection and Configuration
The application connects to a MySQL database named "hospital" using JDBC (Java Database Connectivity). The database connection details, including the URL, username, and password, are hard-coded into the application. When the application starts, it attempts to load the MySQL JDBC driver and establish a connection to the database. If the connection is successful, the application proceeds to interact with the database using SQL queries.

## Adding and Viewing Patients
The addPatient() method in the Patient class prompts the user to enter the patient’s name, age, and gender. This data is then inserted into the database using a PreparedStatement to avoid SQL injection, which is a way to protect the database from harmful inputs.
The viewPatients() method retrieves patient information from the database and displays it in a nicely formatted table, making it easy to see all the details at once.

## Viewing Doctors and Booking Appointments
The viewDoctors() method in the Doctor class lists all doctors in the system, showing their ID, name, and specialization.
The bookAppointment() method, defined in the HospitalManagementSystem class, allows users to schedule appointments by entering patient and doctor IDs along with the desired date.
Before booking, it checks if the patient and doctor exist and whether the doctor is available on that date using the checkDoctorAvailability() method. If all checks pass, the appointment is booked by inserting a new record into the "appointments" table.

## Conclusion
This Hospital Management System provides a basic but functional way to manage patient and doctor information, and schedule appointments. It’s a great example for students to learn about Java programming, database interactions using JDBC, and simple command-line interface design. By expanding upon this foundation, you can develop more complex and real-world applications.
