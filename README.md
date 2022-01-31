// C program to build the complete 

// snake game 

#include <conio.h> 

#include <stdio.h> 

#include <stdlib.h> 

#include <unistd.h> 

 

Int I, j, height = 20, width = 20; 

Int gameover, score; 

Int x, y, fruitx, fruity, flag; 

 

// Function to generate the fruit 

// within the boundary 

Void setup() 

{

Gameover = 0; 

 

 // Stores height and width 

 X = height / 2; 

 Y = width / 2; 

Label1: 

 Fruitx = rand() % 20; 

 If (fruitx == 0) 

 Goto label1; 

Label2: 

 Fruity = rand() % 20; 

 If (fruity == 0) 

 Goto label2; 

 Score = 0;

}

// Function to draw the boundaries 

Void draw() 

{ 

 System(“cls”); 

 For (I = 0; I < height; i++) { 

 For (j = 0; j < width; j++) { 

 If (I == 0 || I == width – 1 

 || j == 0 

 || j == height – 1) { 

 Printf(“#”); 

 } 

 Else { 

 If (I == x && j == y) 

 Printf(“0”); 

 Else if (I == fruitx

&& j == fruity) 

 Printf(“*”); 

 Else

 Printf(“ “); 

 } 

 } 

 Printf(“\n”); 

 } 

 

 // Print the score after the 

 // game ends 

 Printf(“score = %d”, score); 

 Printf(“\n”); 

 Printf(“press X to quit the game”); 

}

// Function to take the input 

Void input() 

{ 

 If (kbhit()) { 

 Switch (getch()) { 

 Case ‘a’: 

 Flag = 1; 

 Break; 

 Case ‘s’: 

 Flag = 2; 

 Break; 

 Case ‘d’: 

 Flag = 3; 

 Break; 

 Case ‘w’:

Flag = 4; 

 Break; 

 Case ‘x’: 

 Gameover = 1; 

 Break; 

 } 

 } 

} 

 

// Function for the logic behind 

// each movement 

Void logic() 

{ 

 Sleep(0.01); 

 Switch (flag) { 

 Case 1:

y--; 

 break; 

 case 2: 

 x++; 

 break; 

 case 3: 

 y++; 

 break; 

 case 4: 

 x--; 

 break; 

 default: 

 break; 

 }

// If the game is over 

 If (x < 0 || x > height 

 || y < 0 || y > width) 

 Gameover = 1; 

 

 // If snake reaches the fruit 

 // then update the score 

 If (x == fruitx && y == fruity) { 

 Label3: 

 Fruitx = rand() % 20; 

 If (fruitx == 0) 

 Goto label3; 

 

 // After eating the above fruit

// generate new fruit 

 Label4: 

 Fruity = rand() % 20; 

 If (fruity == 0) 

 Goto label4; 

 Score += 10; 

 } 

} 

 

// Driver Code 

Void main() 

{ 

 Int m, n; 

 

 // Generate boundary 

 Setup();

// Until the game is over 

 While (!gameover) { 

 

 // Function Call 

 Draw(); 

 Input(); 

 Logic(); 

 } 

}
