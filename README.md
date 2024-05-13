#include <iostream>
#include <vector>
#include <iomanip>
//Author Robiul hasan jisan
//explor

using namespace std;

struct Grade {

    string course;
    string grade;
    double credits;
};

double calculateCGPA(const vector<Grade>& grades) {
    double totalGradePoints = 0;
    double totalCredits = 0;

    for (const auto& grade : grades) {
        double gradePoint;

        if (grade.grade == "A") {
            gradePoint = 4.0;
        } else if (grade.grade == "A-") {
            gradePoint = 3.7;
        } else if (grade.grade == "B+") {
            gradePoint = 3.3;
        } else if (grade.grade == "B") {
            gradePoint = 3.0;
        } else if (grade.grade == "B-") {
            gradePoint = 2.7;
        } else if (grade.grade == "C+") {
            gradePoint = 2.3;
        } else if (grade.grade == "C") {
            gradePoint = 2.0;
        } else if (grade.grade == "C-") {
            gradePoint = 1.7;
        } else if (grade.grade == "D+") {
            gradePoint = 1.3;
        } else if (grade.grade == "D") {
            gradePoint = 1.0;
        } else if (grade.grade == "F") {
            gradePoint = 0.0;
        } else {
            cout << "Invalid grade entered!" << endl;
            return -1;
        }
        totalGradePoints += gradePoint * grade.credits;
        totalCredits += grade.credits;
    }

    return totalGradePoints / totalCredits;
}

int main() {

    int numCourses;
     cout << "Range of Grading System" << endl;

    cout << "------------------------------------------" << endl;

    cout << "93--Above A 4.0"   << endl;
    cout << "89--<93   A-  3.7"  << endl;
    cout << "86--<89   B+  3.3"  << endl;
    cout << "82--<86   B   3.0"   << endl;
    cout << "79--<82   B-  2.7"  << endl;
    cout << "75--<79   C+  2.3"  << endl;
    cout << "72--<75   C   2.0"   << endl;
    cout << "69--<72   C-  1.7"  << endl;
    cout << "65--<69   D+  1.3"  << endl;
    cout << "60--<65   D   1.0"   << endl;
    cout << "----<60   F   0.0"   << endl;
    cout << "----------------------------------------" << endl;
    cout << "Enter the number of courses: ";
    cin >> numCourses;

    vector<Grade> grades(numCourses);

    for (int i = 0; i < numCourses; ++i) {
        cout << "Enter the grade obtained for course " << i+1 << " (A/A-/B+/B/B-/C+/C/C-/D+/D/F: ";
        cin >> grades[i].grade;
        cout << "Enter the credit hours for course " << i+1 << ": ";
        cin >> grades[i].credits;
    }

    double cgpa = calculateCGPA(grades);
    if (cgpa != -1) {
        cout << "Your CGPA is: " << fixed << setprecision(2) << cgpa << endl;
    }

    return 0;
}
