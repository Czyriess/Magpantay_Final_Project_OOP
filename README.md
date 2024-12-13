# Magpantay_Final_Project_OOP
I. Brief Project Overview
The Medical Appointment Management System is a simple Java-based tool designed to help individuals and small healthcare clinics manage appointments. It allows users to easily add, view, and cancel appointments with an intuitive interface, making scheduling straightforward. The system is efficient, using object-oriented programming (OOP) principles to ensure flexibility and ease of maintenance.

II.How OOP Principles Were Applied

Encapsulation:
The Appointment class stores patient and appointment details privately, controlling access through methods to ensure secure and consistent data handling.

  
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
The system allows for future extensions, like specialized appointment types (e.g., online appointments), by creating subclasses that inherit from the base Appointment class.


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
By overriding the toString() method in subclasses, the system can display different representations of appointments while maintaining a unified structure.

Appointment appt = new OnlineAppointment("John Doe", "Dr. Smith", "2024-12-13", "10:00", );
System.out.println(appt.toString());  // Output: Patient: John Doe, Doctor: Dr. Smith, Date: 2024-12-13, Time: 10:00,

Abstraction:
The system hides complex logic behind a simple menu, allowing users to interact with the program without worrying about the details of appointment management.

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

III. The Medical Appointment Management System aligns with Sustainable Development Goal (SDG) 3: Good Health and Well-Being. This goal aims to ensure healthy lives and promote well-being.

Contribution to SDG 3:

*Improves Efficiency: Reduces wait times and ensures healthcare providers can offer timely services.

*Enhances Access: Simplifies appointment scheduling, making healthcare more accessible.

*Supports Small Clinics: Provides an affordable, easy-to-use solution for small healthcare providers.

*Promotes Well-Being: Helps reduce stress by keeping appointments organized and manageable for both patients and healthcare workers.
