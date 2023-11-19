# AICP-Task-3
# Bill unit consumption
#include <iostream>
using namespace std;

const string student_id = "YourStudentID";

const int electricity_matrix[3][3] = {
    {55, 65, 75},
    {120, 150, 170},
    {210, 230, 240}
};

int costSlab1(int units) 
{
    int unit_range = min(units, 100);
    int cost_per_unit = 10;
    int total_cost = unit_range * cost_per_unit;
    return total_cost;
}

int costSlab2(int units) 
{
    int unit_range = max(min(units - 100, 100), 0); 
    int cost_per_unit = 15;
    int total_cost = unit_range * cost_per_unit;
    return total_cost;
}

int costSlab3(int units) 
{
    int unit_range = max(units - 200, 0);
    int cost_per_unit = 20;
    int total_cost = unit_range * cost_per_unit;
    return total_cost;
}

void displayMenu() 
{
    cout << "Student ID: " << student_id << endl;
    cout << "1. Display cost for slab 1 and slab 2" << endl;
    cout << "2. Display cost for slab 3" << endl;
    cout << "Any other key to exit" << endl;
}

int main() 
{
    while (true) 
	{
        displayMenu();
        cout << "Enter your choice: ";
        
        char choice;
        cin >> choice;

        if (choice == '1') 
		{
            int units;
            cout << "Enter units consumed: ";
            cin >> units;

            int cost1 = costSlab1(units);
            int cost2 = costSlab2(units);
            cout << "Cost for slab 1: Rs. " << cost1 << endl;
            cout << "Cost for slab 2: Rs. " << cost2 << endl;
        } else if (choice == '2') 
		{
            int units;
            cout << "Enter units consumed: ";
            cin >> units;

            int cost = costSlab3(units);
            cout << "Cost for slab 3: Rs. " << cost << endl;
        } else 
		{
            cout << "Exiting the program. Goodbye!" << endl;
            break;
        }
    }

    return 0;
}
