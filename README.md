# CODTECH-Task2
/*The StudentGrade program is a simple yet effective tool for calculating and interpreting grades and GPA based on user input. It demonstrates foundational Java concepts such as arrays, loops, conditional statements, methods, and formatted output using printf. This program would be useful in educational contexts for calculating and presenting student performance metrics.*/


package com.student;

import java.util.Scanner;

public class StudentGrade {
	public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of subjects: ");
        int numberOfSubjects = scanner.nextInt();

        double[] grades = new double[numberOfSubjects];
        double total = 0;

        for (int i = 0; i < numberOfSubjects; i++) {
            System.out.print("Enter the grade for subject " + (i + 1) + ": ");
            grades[i] = scanner.nextDouble();
            total += grades[i];
        }

        double average = total / numberOfSubjects;
        String letterGrade = getLetterGrade(average);
        double gpa = getGPA(average);

        System.out.printf("Average Grade: %.2f\n", average);
        System.out.println("Letter Grade: " + letterGrade);
        System.out.printf("GPA: %.2f\n", gpa);

        scanner.close();
    }

    public static String getLetterGrade(double average) {
        if (average >= 90) {
            return "A";
        } else if (average >= 80) {
            return "B";
        } else if (average >= 70) {
            return "C";
        } else if (average >= 60) {
            return "D";
        } else {
            return "F";
        }
    }

    public static double getGPA(double average) {
        if (average >= 90) {
            return 4.0;
        } else if (average >= 80) {
            return 3.0;
        } else if (average >= 70) {
            return 2.0;
        } else if (average >= 60) {
            return 1.0;
        } else {
            return 0.0;
        }
    }


}
