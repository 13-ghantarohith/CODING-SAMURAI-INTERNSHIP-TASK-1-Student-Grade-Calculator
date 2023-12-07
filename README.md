# CODING-SAMURAI-INTERNSHIP-TASK-1-Student-Grade-Calculator
#include <iostream>
#include <string>
#include <vector>

using namespace std;

double calculateAverage(int math, int english, int science) {
    return (math + english + science) / 3.0;
}

int main() {
    
    int numStudents;
    cout << "Enter the number of students: ";
    cin >> numStudents;

    
    if (numStudents <= 0) {
        cout << "Invalid number of students. Exiting program." << endl;
        return 1; 
    }

    vector<string> studentNames;
    vector<int> mathScores, englishScores, scienceScores;

    for (int i = 0; i < numStudents; ++i) {
        cout << "Enter the name of student " << i + 1 << ": ";
        string name;
        cin >> name;
        studentNames.push_back(name);

        cout << "Enter the Math score for " << name << ": ";
        int mathScore;
        cin >> mathScore;
        mathScores.push_back(mathScore);

        cout << "Enter the English score for " << name << ": ";
        int englishScore;
        cin >> englishScore;
        englishScores.push_back(englishScore);

        cout << "Enter the Science score for " << name << ": ";
        int scienceScore;
        cin >> scienceScore;
        scienceScores.push_back(scienceScore);
    }

    cout << "\nAverage Grades:" << endl;
    for (int i = 0; i < numStudents; ++i) {
        double average = calculateAverage(mathScores[i], englishScores[i], scienceScores[i]);
        cout << studentNames[i] << ": " << average << endl;
    }

    return 0; 
}
