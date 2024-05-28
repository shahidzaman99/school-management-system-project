/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package school.management.systemss;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

/**
 *
 * @author shahidzaman
 */

interface Person {
    void displayinfo();
    void greet();
}

class Student implements Person {
    private String name;
    private int age;
    private String department;
    private String grade;
    private int idcardnumber;

    public Student(String name, int age, String department, String grade, int idcardnumber) {
        this.name = name;
        this.age = age;
        this.department = department;
        this.grade = grade;
        this.idcardnumber = idcardnumber;
    }

    public void setGrade(String grade) {
        this.grade = grade;
    }

    public String getGrade() {
        return grade;
    }

    public void setDepartment(String department) {
        this.department = department;
    }

    public String getDepartment() {
        return department;
    }

    @Override
    public void displayinfo() {
        System.out.println("Student name is " + name);
        System.out.println("Student age is " + age);
        System.out.println("Student grade is " + grade);
        System.out.println("Student department is " + department);
        System.out.println("Student ID card number is " + idcardnumber);
    }

    @Override
    public void greet() {
        System.out.println("Hello, I am a student of this school.");
    }
}


class Teacher implements Person {
    private String name;
    private int age;
    private String subject;
    private int idnumber;

    public Teacher(String name, int age, String subject, int idnumber) {
        this.name = name;
        this.age = age;
        this.subject = subject;
        this.idnumber = idnumber;
    }

    @Override
    public void displayinfo() {
        System.out.println("Teacher name is " + name);
        System.out.println("Teacher age is " + age);
        System.out.println("Teacher subject is " + subject);
        System.out.println("Teacher ID number is " + idnumber);
    }

    @Override
    public void greet() {
        System.out.println("Hi, I am a teacher at this school.");
    }
}


class School {
    private String name;
    private List<Student> students;
    private List<Teacher> teachers;

    public School(String name) {
        this.name = name;
        this.students = new ArrayList<>();
        this.teachers = new ArrayList<>();
    }

    public void addStudent(Student student) {
        students.add(student);
    }

    public void addTeacher(Teacher teacher) {
        teachers.add(teacher);
    }

    public List<Student> getStudents() {
        return students;
    }

    public List<Teacher> getTeachers() {
        return teachers;
    }

    public void displayinfo() {
        System.out.println("School name: " + name);
        System.out.println("Students:");
        for (Student student : students) {
            student.displayinfo();
        }
        System.out.println("Teachers:");
        for (Teacher teacher : teachers) {
            teacher.displayinfo();
        }
    }
}


class Exam extends School {
    private String papername;
    private int paperdate;
    private String examtype;
    private String hallname;

    public Exam(String schoolName, String papername, int paperdate, String examtype, String hallname) {
        super(schoolName);
        this.papername = papername;
        this.paperdate = paperdate;
        this.examtype = examtype;
        this.hallname = hallname;
    }

    @Override
    public void displayinfo() {
        super.displayinfo();
        System.out.println("Paper name: " + papername);
        System.out.println("Paper date: " + paperdate);
        System.out.println("Exam type: " + examtype);
        System.out.println("Hall name: " + hallname);
    }
}

class Classroom extends School {
    private int roomnumber;
    private int roomcapacity;

    public Classroom(String schoolName, int roomnumber, int roomcapacity) {
        super(schoolName);
        this.roomnumber = roomnumber;
        this.roomcapacity = roomcapacity;
    }

    @Override
    public void displayinfo() {
        super.displayinfo();
        System.out.println("Room number: " + roomnumber);
        System.out.println("Room capacity: " + roomcapacity);
    }
}

class Course extends School {
    private String coursename;
    private int coursecode;

    public Course(String schoolName, String coursename, int coursecode) {
        super(schoolName);
        this.coursename = coursename;
        this.coursecode = coursecode;
    }

    @Override
    public void displayinfo() {
        super.displayinfo();
        System.out.println("Course name: " + coursename);
        System.out.println("Course code: " + coursecode);
    }
}

class Schedule extends School {
    private String dayofweek;
    private String starttime;
    private String endtime;

    public Schedule(String schoolName, String dayofweek, String starttime, String endtime) {
        super(schoolName);
        this.dayofweek = dayofweek;
        this.starttime = starttime;
        this.endtime = endtime;
    }

    @Override
    public void displayinfo() {
        super.displayinfo();
        System.out.println("Day of week: " + dayofweek);
        System.out.println("Start time: " + starttime);
        System.out.println("End time: " + endtime);
    }
}
public class SchoolManagementSystemss {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter the school name: ");
        String schoolName = scanner.nextLine();
        School school = new School(schoolName);

        System.out.println("Enter the number of students to add: ");
        int numStudents = scanner.nextInt();
        scanner.nextLine();
        for (int i = 0; i < numStudents; i++) {
            System.out.println("Enter the student name: ");
            String studentName = scanner.nextLine();
            System.out.println("Enter the student age: ");
            int studentAge = scanner.nextInt();
            scanner.nextLine();
            System.out.println("Enter the student department: ");
            String studentDepartment = scanner.nextLine();
            System.out.println("Enter the student grade: ");
            String studentGrade = scanner.nextLine();
            System.out.println("Enter the student ID card number: ");
            int studentIdCardNumber = scanner.nextInt();
            scanner.nextLine();
            Student student = new Student(studentName, studentAge, studentDepartment, studentGrade, studentIdCardNumber);
            school.addStudent(student);
            
            
        }

        System.out.println("Enter the number of teachers to add: ");
        int numTeachers = scanner.nextInt();
        scanner.nextLine();
        for (int i = 0; i < numTeachers; i++) {
            System.out.println("Enter the teacher name: ");
            String teacherName = scanner.nextLine();
            System.out.println("Enter the teacher age: ");
            int teacherAge = scanner.nextInt();
            scanner.nextLine();
            System.out.println("Enter the teacher subject: ");
            String teacherSubject = scanner.nextLine();
            System.out.println("Enter the teacher ID card number: ");
            int teacherIdCardNumber = scanner.nextInt();
            scanner.nextLine();
            Teacher teacher = new Teacher(teacherName, teacherAge, teacherSubject, teacherIdCardNumber);
            school.addTeacher(teacher);
              teacher.displayinfo();

        }

        System.out.println("Enter the exam details: ");
        System.out.println("Enter the paper name: ");
        String paperName = scanner.nextLine();
        System.out.println("Enter the exam date: ");
        int examDate = scanner.nextInt();
        scanner.nextLine();
        System.out.println("Enter the exam type: ");
        String examType = scanner.nextLine();
        System.out.println("Enter the hall name: ");
        String hallName = scanner.nextLine();
        Exam exam = new Exam(schoolName, paperName, examDate, examType, hallName);
        System.out.println("Exam information: ");

        System.out.println("Enter the classroom details: ");
        System.out.println("Enter the room number: ");
        int roomNumber = scanner.nextInt();
        scanner.nextLine();
        System.out.println("Enter the room capacity: ");
        int roomCapacity = scanner.nextInt();
        scanner.nextLine();
        Classroom classroom = new Classroom(schoolName, roomNumber, roomCapacity);
        System.out.println("Classroom information: ");
      

        System.out.println("Enter the course details: ");
        System.out.println("Enter the course name: ");
        String courseName = scanner.nextLine();
        System.out.println("Enter the course code: ");
        int courseCode = scanner.nextInt();
        scanner.nextLine();
        Course course = new Course(schoolName, courseName, courseCode);
        System.out.println("Course information: ");

        System.out.println("Enter the schedule details: ");
        System.out.println("Enter the day of the week: ");
        String dayOfWeek = scanner.nextLine();
        System.out.println("Enter the start time: ");
        String startTime = scanner.nextLine();
        System.out.println("Enter the end time: ");
        String endTime = scanner.nextLine();
        Schedule schedule = new Schedule(schoolName, dayOfWeek, startTime, endTime);
        System.out.println("Schedule information: ");

        System.out.println("School information: ");
        school.displayinfo();
        System.out.println("Exam information: ");
        exam.displayinfo();
        System.out.println("Classroom information: ");
        classroom.displayinfo();
        System.out.println("Course information: ");
        course.displayinfo();
        System.out.println("Schedule information: ");
        schedule.displayinfo();
     
       
              
}
}
        
