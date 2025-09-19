# Code-Blocks-Experiment-1
Implementation of Go-Back-N Protocol – Sliding Window

🎯 Aim

To write and execute a program for the Go-Back-N protocol using the sliding window technique.

🛠️ Equipments Required

• 	Personal Computer

• 	Turbo C Compiler

📋 Procedure
1. 	Connect two computers in a Wired/Wireless LAN.
2. 	Ensure both machines are on the same network and can ping each other.
3. 	Open a new C file in Code::Blocks or any C IDE and type the program.
4. 	Navigate to:
Project -> Properties -> Project Build Options -> Linker Settings
Add: netproto and pthread
5. 	Execute the program on both server and client machines.
6. 	Enter:
• 	IP address of the remote machine
• 	Port address of both local and remote machines
• 	Error rate
7. 	Choose the file and verify the Go-Back-N protocol operation.

💻 Program

#include <stdio.h>

#define window_size 4  // Assume 7 frames of data are to be sent using Go-Back-N ARQ

void main() {

    int i, window_start = 1, ack;
    
    int n;

    printf("SLIDING WINDOW PROTOCOL\n");
    scanf("%d", &n);
    printf("GO BACK N ARQ\n");
    printf("Enter the number of frames: %d\n", n);

    char frame[n + 1][10];

    for (i = 1; i <= n; i++) {
        printf("Content for frame %d: ", i);
        scanf("%s", frame[i]);
    }

    while (window_start <= n) {
        printf("\nSending frames:\n");
        scanf("%d", &ack);
        printf("Enter frame number with no ACKs: %d\n", ack);

        if (ack == 0) {
            printf("No ACK received, moving window forward\n");
            window_start += window_size;
        } else {
            printf("No Acknowledgement for frame %d...\n", ack);
            printf("Resending frames starting from frame %d\n", ack);
            window_start = ack;
        }
    }

    printf("\nAll frames sent successfully.\n");
}
🖥️ Sample Output
<img width="1280" height="800" alt="Screenshot 2023-09-19 at 9 25 33 AM" src="https://github.com/user-attachments/assets/33ebad7c-1abd-46b3-8481-7e5067f86980" />


✅ Result

Thus, the Go-Back-N protocol using the sliding window technique was successfully implemented and verified.
