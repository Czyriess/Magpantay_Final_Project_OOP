# Magpantay_Final_Project_OOP
I. Brief Project Overview
The Medical Appointment Management System is a simple Java-based application designed to help individuals and small healthcare clinics manage appointments. It allows users to add, view, and cancel appointments, providing an easy-to-use interface to streamline the scheduling process. The system is designed with efficiency and simplicity in mind, offering key features like appointment management and real-time schedule updates. It is built using Java and applies object-oriented programming (OOP) principles to ensure flexibility and maintainability.

II. Explanation of How OOP Principles Were Applied

Encapsulation:
The system uses the Appointment class to encapsulate key appointment details such as the patient’s name, doctor’s name, date, and time. These details are stored as private fields, and access is controlled via constructors and getter/setter methods. This ensures that appointment data is handled securely and consistently.

  
    class Appointment {
    private String patientName;
    private String doctorName;
    private String date;
    private String time;

    public Appointment(String patientName, String doctorName, String date, String time) {
        this.patientName = patientName;
        this.doctorName = doctorName;
        this.date = date;
        this.time = time;
    }
    
    @Override
    public String toString() {
        return "Patient: " + patientName + ", Doctor: " + doctorName + ", Date: " + date + ", Time: " + time;
    }
}

Inheritance:
Inheritance is implemented by allowing future extensions of the system, such as specialized appointment types (e.g., online appointments). A new class, like OnlineAppointment, can inherit from Appointment and extend its functionality while reusing the core properties.


    class OnlineAppointment extends Appointment {
    private String meetingLink;

    public OnlineAppointment(String patientName, String doctorName, String date, String time, String meetingLink) {
        super(patientName, doctorName, date, time);
        this.meetingLink = meetingLink;
    }
    
    @Override
    public String toString() {
        return super.toString() + ", Meeting Link: " + meetingLink;
       }
    }

Polymorphism:
The system utilizes polymorphism, allowing the toString() method to be overridden in subclasses like OnlineAppointment. This enables different representations of appointments, even though they all share the same base class.


Appointment appt = new OnlineAppointment("John Doe", "Dr. Smith", "2024-12-13", "10:00");
System.out.println(appt.toString());  // Output: Patient: John Doe, Doctor: Dr. Smith, Date: 2024-12-13, Time: 10:00,

Abstraction:
The program hides the complex details of how appointments are stored and managed, allowing users to interact only with a simple menu. The user simply selects an option to add, view, or cancel appointments without needing to understand the underlying code logic.

public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    int choice;

    do {
        System.out.println("1. Add Appointment");
        System.out.println("2. View Appointments");
        System.out.println("3. Cancel Appointment");
        System.out.println("4. Exit");
        choice = scanner.nextInt();
        scanner.nextLine(); // Consume newline

        switch (choice) {
            case 1 -> addAppointment(scanner);  
            case 2 -> viewAppointments();
            case 3 -> cancelAppointment(scanner);
            case 4 -> System.out.println("Goodbye!");
        }
    } while (choice != 4);

    scanner.close();
    }

III. The Medical Appointment Management System aligns with Sustainable Development Goal (SDG) 3: Good Health and Well-Being. This goal aims to ensure healthy lives and promote well-being for all at all ages.

Contribution to SDG 3:

Enhances Healthcare Efficiency: By organizing appointments and schedules, the system helps reduce patient wait times and ensures that healthcare providers can offer more timely services.
Improves Access to Medical Care: Simplifies appointment management for patients, ensuring that they can easily schedule and attend their appointments, improving overall access to healthcare.
Supports Small Clinics: The system offers an affordable and easy-to-use solution for small clinics or independent healthcare providers who may not have access to more complex systems.
Promotes Mental Well-Being: By reducing the stress and confusion around managing appointments, the system helps both patients and doctors stay organized and focused, contributing to better mental well-being.
