#include <iostream>
#include <vector>
#include <iomanip>
#include <algorithm>
using namespace std;

// Author: Robiul Hasan Jisan

// Define the Patient structure
struct Patient {
    string pname;
    int page;
    int pweight;
    int pheight;
    string pblood;
    int pnumber;
};

// Function to find a patient by number in the vector
int findPatientByNumber(const vector<Patient>& patients, int pnumber) {
    for (size_t i = 0; i < patients.size(); ++i) {
        if (patients[i].pnumber == pnumber) {
            return i;
        }
    }
    return -1;
}

// Function to find patients by name in the vector
vector<int> findPatientsByName(const vector<Patient>& patients, const string& pname) {
    vector<int> indices;
    for (size_t i = 0; i < patients.size(); ++i) {
        if (patients[i].pname == pname) {
            indices.push_back(i);
        }
    }
    return indices;
}

// Function to display patients sorted by age
void displayPatientsByAge(const vector<Patient>& patients) {
    vector<Patient> sortedPatients = patients;
    sort(sortedPatients.begin(), sortedPatients.end(), [](const Patient& a, const Patient& b) {
        return a.page < b.page;
    });

    cout << "\nPatients Sorted by Age:" << endl;
    for (const auto& patient : sortedPatients) {
        cout << "Name: " << patient.pname << ", Age: " << patient.page << endl;
    }
}

// Function to display patients with a specific blood type
void displayPatientsByBloodType(const vector<Patient>& patients, const string& bloodType) {
    cout << "\nPatients with Blood Type " << bloodType << ":" << endl;
    for (const auto& patient : patients) {
        if (patient.pblood == bloodType) {
            cout << "Name: " << patient.pname << ", Blood Type: " << patient.pblood << endl;
        }
    }
}

// Function to calculate the average age of all patients
double calculateAverageAge(const vector<Patient>& patients) {
    double totalAge = 0;
    for (const auto& patient : patients) {
        totalAge += patient.page;
    }
    return (patients.empty() ? 0 : totalAge / patients.size());
}

// Function to draw a horizontal line
void drawHorizontalLine(int width, char borderChar, char fillChar) {
    cout << borderChar;
    for (int i = 0; i < width - 2; ++i) {
        cout << fillChar;
    }
    cout << borderChar << endl;
}

int main() {
    vector<Patient> patients;
    cout << "----------As-salamu alaykum----------" << endl;
    char choice;
    do {
        Patient patient;
        cout << "Enter patient name: ";
        getline(cin, patient.pname);

        cout << "Enter patient age: ";
        cin >> patient.page;

        cout << "Enter patient weight (in kg): ";
        cin >> patient.pweight;

        cout << "Enter patient height (in cm): ";
        cin >> patient.pheight;

        cout << "Enter patient blood type: ";
        cin >> patient.pblood;

        cout << "Enter patient number: ";
        cin >> patient.pnumber;

        int index = findPatientByNumber(patients, patient.pnumber);
        if (index != -1) {
            // Update patient data if patient is already in the vector
            patients[index] = patient;
            cout << "Patient data updated successfully." << endl;
        } else {
            // Add new patient to the vector
            patients.push_back(patient);
            cout << "Patient added successfully." << endl;
        }

        cout << "Do you want to add another patient? (y/n): ";
        cin >> choice;
        cin.ignore(); // Ignore newline character
    } while (choice == 'y' || choice == 'Y');

    // Draw a horizontal line
    int lineWidth = 50; // Adjust this according to your needs
    drawHorizontalLine(lineWidth, '-', '-');

    // Display all patient details
    cout << "\nAll Patients' Details:" << endl;
    for (const auto& patient : patients) {
        cout << "\nPatient Details:" << endl;
        cout << "Name      : " << patient.pname << endl;
        cout << "Age       : " << patient.page << endl;
        cout << "Weight    : " << patient.pweight << " kg" << endl;
        cout << "Height    : " << patient.pheight << " cm" << endl;
        cout << "Blood Type: " << patient.pblood << endl;
        cout << "Number    : " << patient.pnumber << endl;
        drawHorizontalLine(lineWidth, '-', '-');
    }

    // Display patients sorted by age
    displayPatientsByAge(patients);

    // Display patients with a specific blood type
   displayPatientsByBloodType(patients, "O+");
    displayPatientsByBloodType(patients, "O-");
    displayPatientsByBloodType(patients, "A+");
    displayPatientsByBloodType(patients, "A-");
    displayPatientsByBloodType(patients, "B+");
    displayPatientsByBloodType(patients, "B-");
    displayPatientsByBloodType(patients, "AB+");
    displayPatientsByBloodType(patients, "AB-");gfg


    // Calculate and display the average age of patients
    double avgAge = calculateAverageAge(patients);
    cout << "\nAverage Age of Patients: " << fixed << setprecision(2) << avgAge << " years" << endl;

    cout << "BEST WISHES";

    return 0;
}
