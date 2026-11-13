#include <iostream>
#include <string>
#include <thread>
#include <chrono>

using namespace std;

// Function to add a slight cinematic pause to text
void slowPrint(string text) {
    for (char c : text) {
        cout << c << flush;
        this_thread::sleep_for(chrono::milliseconds(20));
    }
    cout << endl;
}

int main() {
    string playerName;
    int health = 100;
    int choice;

    slowPrint("==========================================");
    slowPrint("      WELCOME TO THE NEON WASTELAND       ");
    slowPrint("==========================================");
    
    cout << "\nEnter your character's name, traveler: ";
    cin >> playerName;

    slowPrint("\nHello, " + playerName + ". You wake up in a dark, flickering alleyway.");
    slowPrint("Rain hits the pavement. Neon signs buzz overhead.");
    slowPrint("You hear footsteps approaching from behind a rusted dumpster.\n");

    cout << "What do you want to do?\n";
    cout << "1. Sneakily search the dumpster for a weapon.\n";
    cout << "2. Stand your ground and wait for them.\n";
    cout << "3. Run blindly into the main street.\n";
    cout << "Enter your choice (1-3): ";
    cin >> choice;

    if (choice == 1) {
        slowPrint("\nYou rummage through the garbage and find a heavy iron pipe! (+Weapon)");
        slowPrint("A scavenger jumps out, but you swing first and knock them back!");
        slowPrint("You successfully escape into the neon-lit highway. You survived Chapter 1!");
    } 
    else if (choice == 2) {
        slowPrint("\nYou turn around to face the figure. It's a cybernetically enhanced bandit!");
        health -= 40;
        slowPrint("They strike you before you can react! (-40 Health). Current Health: " + to_string(health));
        slowPrint("You manage to break free and slip away into the shadows, barely alive.");
    } 
    else {
        slowPrint("\nYou sprint blindly into traffic! A flying delivery drone clips your shoulder.");
        health -= 30;
        slowPrint(" (-30 Health). Current Health: " + to_string(health));
        slowPrint("You tumble onto a sidewalk, battered but safe for the moment.");
    }

    slowPrint("\n==========================================");
    slowPrint("        END OF DEMO - TO BE CONTINUED     ");
    slowPrint("==========================================");

    return 0;
}
