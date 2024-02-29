#include <stdio.h>
#include <windows.h>
int main()
{
    // Variable declarations
    int h, m, s;
    int d = 1000; // Delay of 1000 milliseconds (1 second)

    // User input for setting the initial time
    printf("Set time : \n");
    scanf("%d%d%d", &h, &m, &s);

    // Check for invalid input
    if (h > 12 || m > 60 || s > 60)
    {
        printf("ERROR ! \n");
    }

    // Infinite loop to update and display the clock
    while (1)
    {
        s++;
        if (s > 59)
        {
            m++;
            s = 0;
        }
        if (m > 59)
        {
            h++;
            m = 0;
        }
        if (h > 12)
        {
            h = 1;
        }

        // Display the clock time
        printf("\n Clock :");
        printf("\n %02d:%02d:%02d", h, m, s); // Format the time as HH:MM:SS
        Sleep(d); // Introduce a delay using the Sleep function from Windows API
        system("cls"); // Clear the console screen
    }

    return 0;
}



# Simple Digital Clock for Windows Console
 Description: This C program utilizes the Windows API to create a simple digital clock in the console. 
 The user sets the initial time, and the program continuously updates and displays the time in HH:MM:SS format. 
 It includes a 1-second delay between updates for a realistic time passage effect. The console screen is cleared before each update to create a smooth display.
