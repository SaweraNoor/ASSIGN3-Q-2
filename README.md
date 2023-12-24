//ASSIGN3-Q-2
#include <iostream>
#include <string>
using namespace std;
// Abstract Base Class
class Course {
public:
    // Pure virtual function
    virtual void displayCourseDetails() const = 0;
    virtual ~Course() {}
};

// Derived Class 1: MathCourse
class MathCourse : public Course {
private:
    string courseName;
    int courseCode;

public:
  
    MathCourse(const string& name, int code) : courseName(name), courseCode(code) {}

    // Implementation of the pure virtual function
    void displayCourseDetails() const override {
        cout << "Math Course: " << courseName << " (Code: " << courseCode << ")" << endl;
    }
};

//Derived Class 2: HistoryCourse
class HistoryCourse : public Course {
private:
    string courseName;
    int courseCode;

public:
   
    HistoryCourse(const string& name, int code) : courseName(name), courseCode(code) {}

    // Implementation of the pure virtual function
    void displayCourseDetails() const override {
        cout << "History Course: " << courseName << " (Code: " << courseCode << ")" <<endl;
    }
};

int main() {
    MathCourse math("Calculus", 101);
    HistoryCourse history("World History", 201);
    Course* course1 = &math;
    Course* course2 = &history;

    course1->displayCourseDetails();
    course2->displayCourseDetails();

    return 0;
}
