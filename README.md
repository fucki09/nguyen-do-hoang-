```csharp
using System;
using System.Collections.Generic;
using System.Linq;

public class Student
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}

public class Program
{
    public static void Main()
    {
        List<Student> students = new List<Student>
        {
            new Student { Id = 2442, Name = "Phuc", Age = 17 },
            new Student { Id = 5645, Name = "Minh", Age = 15 },
            new Student { Id = 6894, Name = "Nghi", Age = 18 },
            new Student { Id = 1231, Name = "Khoa", Age = 16 },
            new Student { Id = 8888, Name = "Nghia", Age = 18 }
        };

        Console.WriteLine("Danh sach hoc sinh:");
        foreach (var student in students)
        {
            Console.WriteLine($"Id: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
        Console.WriteLine();

        var studentsAge15To18 = students.Where(s => s.Age >= 15 && s.Age <= 18).ToList();
        Console.WriteLine("Danh sach hoc sinh có tuoi tu 15 den 18:");
        foreach (var student in studentsAge15To18)
        {
            Console.WriteLine($"Id: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
        Console.WriteLine();

        var studentsNameStartingWithA = students.Where(s => s.Name.StartsWith("A")).ToList();
        Console.WriteLine("Danh sach hoc sinh co ten bat dau bang chu 'A':");
        foreach (var student in studentsNameStartingWithA)
        {
            Console.WriteLine($"Id: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
        Console.WriteLine();

        var totalAge = students.Sum(s => s.Age);
        Console.WriteLine($"Tong tuoi cua tat ca hoc sinh: {totalAge}");
        Console.WriteLine();
       
        var oldestStudent = students.OrderByDescending(s => s.Age).First();
        Console.WriteLine("Hoc sinh co tuoi lon nhat:");
        Console.WriteLine($"Id: {oldestStudent.Id}, Name: {oldestStudent.Name}, Age: {oldestStudent.Age}");
        Console.WriteLine();

        var sortedStudents = students.OrderBy(s => s.Age).ToList();
        Console.WriteLine("Danh sach hoc sinh sau khi sap xep theo tuoi tang dan:");
        foreach (var student in sortedStudents)
        {
            Console.WriteLine($"Id: {student.Id}, Name: {student.Name}, Age: {student.Age}");
        }
    }
}

