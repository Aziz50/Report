#Abdulaziz Alhedithy
#Professor Evert
#Comsc-1033
#November4, 2015

1.	Program that generates a random uppercase letter using Math.Random() method.

Sol. 	The code/project is already uploaded on my GIT account and the name of the repository is “Random”.

The following code generates a random letter from (A to Z) every time the user complies the code.
I came across many different challenges while writing this code initially when I started it was not generating the random letters. It was repeating letters again and again. 
	
Code:-


public class Random {

	public static void main(String[] args) {
			
			char letter = RandomLetter();
			System.out.print("This code will generate a random character from A to Z, everytime the user runs the code. \n"); //Welcome Statement
			System.out.println(letter);
			
		}
	
	//There are 26 letters in total but as we know that Java excludes the upper limit. Therefore we need to add one at the end to complete 26 letters.
		
		public static char RandomLetter(){ //Upper case Letters
			
			int Initial = 65; // Declaring the initial value i.e. 55
			
			// Although 90 - 65 = 25, but there are 26 letters in total, to complete all 26 letters we do :-
			
			int Final = 90 - 65 + 1 ;	//Declaring final value. The difference between two is 25, to complete the 26 letters we add one in the end. 

			char letterRandom = (char)(Initial + Math.random()*(Final));
			
			return letterRandom; 	//returns the random letter
			
		}
}
		

Output:-

This code will generate a random character from A to Z, every time the user runs the code. 
N

This code will generate a random character from A to Z, every time the user runs the code. 
D

This code will generate a random character from A to Z, every time the user runs the code. 
Q

This code will generate a random character from A to Z, every time the user runs the code. 
B

GIT Steps/Experience.
1.	I created a new repository on the GUI.
2.	Then using the command prompt (cmd) I went to desktop
3.	Cloned the repository using command : 
git clone https://github.com/Aziz50/Random.git
4.	Added all the changes i.e. files from the eclipse project to the repository.
5.	Again used command “git status” to see what new changes are.
6.	Entered “git add .” because I wanted to add all the files/ upload all the new files.
7.	Here, git asked me to configure my identity and using commands
a.	Git config user.name
b.	Git config user.email
8.	I used git commit –m “comment” 
9.	Finally I used “git push”. At this step git asked for my username and password to verify the user and finally the file was uploaded to GitHub. 

P.S.  The cheat sheet helped me a lot in uploading the file to GIT. I am working hard on it to user stand all the commands but I got the basics done. 

2.	Addition Game. Java code for an addition game.

Sol.  This code is for an addition game. The following code generates two random numbers and asks user to add them and enter the answer. If user enters the correct answer then it generates harder random numbers, this goes on for four rounds. If the user enters the wrong answer it displays “Incorrect Answer” and reduces the hardness level.

There are four rounds in this game after the completion of four rounds, it display’s the actual score. 

Code:- 
import java.util.Scanner;

public class AdditionGame {

//Defining Varialbes or globals
	
	public static int number1;
	public static int number2;
	public static int hardness = 10;
	public static int score;
	public static int input1;
	public static int CorrectAnswer;
	
	public static void main(String[] args) {
		//Call the addition game
		additionGameMethod();
	}//End main

	public static void additionGameMethod() {
		//State game name and rules
		System.out.println ("Welcome to the addition game. Let's start! ");
		System.out.println ("For every correct answer you will get 2 points and for every incorrect answer -1 points.");
				
		for(int i=0;i<4;i=i+1){ //Generates Question
			randomMathProblem();
			
			System.out.println("\nRound #" + (i + 1)); //Outputs the current round in session
			System.out.println("Add these two numbers " + number1 + " + " + number2 + "?"); // Puts question to the user
			Scanner input = new Scanner(System.in); //User inputs the answer here
			
			 do {
				 while (!input.hasNextInt()) {
			           System.out.println("That's not a number! Please enter a number.");
			           input.next(); //User enters a numeric variable
			        }
				 input1 = input.nextInt(); // this is important!
			} while (input1 <= 0);
			 isAnswerCorrect(); //This checks the answer, depending upon the answer it outputs the designated text and answer.
		}//Loop end
		
//Final Results of the current session
		System.out.println ("\nGAME OVER \n");
		System.out.println ("Your final score is : " + score);
	}//End additionGameMethod
	
	public static int randomMathProblem(){
		int result = 0;
		number1 = randomNumber();
		number2 = randomNumber();
		CorrectAnswer = number1 + number2; 
	return result;
	}//End randomNumber
	
	public static int randomNumber(){
		int generatedNumber = (int)(Math.random()*hardness);
		return generatedNumber;
	}//End randomNumber
	
	public static void isAnswerCorrect(){
				if (input1 == CorrectAnswer){
					System.out.println("The answer was correct.");
					System.out.println("\n (+2 Points) Good Job! Difficulity level increased.");
					hardness *= 10;
					score += 2;
					System.out.println("Score: " + score);
					//return;
				}else{
					System.out.println("The answer was incorrect.");
					System.out.println("\n1 point removed and difficulty decreased.");
					if (hardness <= 10){
						hardness = 10;
					}else{
						hardness /= 10;
					}
					score -= 1;
					System.out.println("Score: "+ score);
					System.out.println("To play again! Please run the code again.");
					
					//return
				}//End IF statement
	}//End isAnswerCorrect
}//End main

Output:-
Welcome to the addition game. Let's start! 
For every correct answer you will get 2 points and for every incorrect answer -1 points.

Round #1
Add these two numbers 8 + 9?
17
The answer was correct.

 (+2 Points) Good Job! Difficulty level increased.
Score: 2

Round #2
Add these two numbers 64 + 94?
158
The answer was correct.

 (+2 Points) Good Job! Difficulty level increased.
Score: 4

Round #3
Add these two numbers 942 + 610?
1552
The answer was correct.

 (+2 Points) Good Job! Difficulty level increased.
Score: 6

Round #4
Add these two numbers 6160 + 9210?
15370
The answer was correct.

 (+2 Points) Good Job! Difficulty level increased.
Score: 8

GAME OVER 

Your final score is : 8


Welcome to the addition game. Let's start! 
For every correct answer you will get 2 points and for every incorrect answer -1 points.

Round #1
Add these two numbers 5 + 9?
11
The answer was incorrect.

1 point removed and difficulty decreased.
Score: -1
To play again! Please run the code again.

Round #2
Add these two numbers 0 + 2?
2
The answer was correct.

 (+2 Points) Good Job! Difficulty level increased.
Score: 1

Round #3
Add these two numbers 32 + 55?
87
The answer was correct.

 (+2 Points) Good Job! Difficulty level increased.
Score: 3

Round #4
Add these two numbers 154 + 775?
456
The answer was incorrect.

1 point removed and difficulty decreased.
Score: 2
To play again! Please run the code again.

GAME OVER 

Your final score is : 2



GIT Steps/Log.

Microsoft Windows [Version 6.1.7601]
Copyright (c) 2009 Microsoft Corporation.  All rights reserved.

C:\Users\SWOSU>dir
 Volume in drive C has no label.
 Volume Serial Number is 50E4-BFE6

 Directory of C:\Users\SWOSU

11/11/2015  07:35 PM    <DIR>          .
11/11/2015  07:35 PM    <DIR>          ..
09/28/2015  08:29 PM    <DIR>          .android
09/28/2015  08:26 PM    <DIR>          .AndroidStudio1.3
10/02/2015  12:30 PM    <DIR>          .config
09/21/2015  02:40 PM    <DIR>          .eclipse
09/28/2015  02:55 PM    <DIR>          .git
10/02/2015  12:32 PM               206 .gitconfig
09/28/2015  08:30 PM    <DIR>          .gradle
11/11/2015  07:19 PM    <DIR>          .oracle_jre_usage
11/11/2015  07:35 PM    <DIR>          .p2
09/28/2015  03:00 PM    <DIR>          .ssh
09/28/2015  03:02 PM    <DIR>          .swt
11/11/2015  07:35 PM    <DIR>          .tooling
09/28/2015  08:32 PM    <DIR>          AndroidStudioProjects
10/23/2015  12:50 PM    <DIR>          Contacts
11/11/2015  08:02 PM    <DIR>          Desktop
11/11/2015  08:02 PM    <DIR>          Documents
11/11/2015  07:40 PM    <DIR>          Downloads
11/11/2015  07:19 PM    <DIR>          eclipse
10/23/2015  12:50 PM    <DIR>          Favorites
11/10/2015  02:58 PM    <DIR>          Links
10/23/2015  12:50 PM    <DIR>          Music
11/11/2015  06:56 PM    <DIR>          OneDrive
10/23/2015  12:50 PM    <DIR>          Pictures
10/23/2015  12:50 PM    <DIR>          Saved Games
10/23/2015  12:50 PM    <DIR>          Searches
10/23/2015  12:50 PM    <DIR>          Videos
11/11/2015  07:40 PM    <DIR>          workspace
               1 File(s)            206 bytes
              28 Dir(s)  403,116,507,136 bytes free

C:\Users\SWOSU>cd Desktop

C:\Users\SWOSU\Desktop>git clonehttps://github.com/Aziz50/AdditionGame.git
git: 'clonehttps://github.com/Aziz50/AdditionGame.git' is not a git command. See
 'git --help'.

C:\Users\SWOSU\Desktop>git clone https://github.com/Aziz50/AdditionGame.git
Cloning into 'AdditionGame'...
warning: You appear to have cloned an empty repository.
Checking connectivity... done.

C:\Users\SWOSU\Desktop>git pull
fatal: Not a git repository (or any of the parent directories): .git

C:\Users\SWOSU\Desktop>git add .
fatal: Not a git repository (or any of the parent directories): .git

C:\Users\SWOSU\Desktop>dir
 Volume in drive C has no label.
 Volume Serial Number is 50E4-BFE6

 Directory of C:\Users\SWOSU\Desktop

11/11/2015  08:04 PM    <DIR>          .
11/11/2015  08:04 PM    <DIR>          ..
11/11/2015  08:05 PM    <DIR>          AdditionGame
11/11/2015  08:02 PM            37,037 COMSC_1033_HW8_Alhedithy_Abdulaziz.docx
11/11/2015  07:21 PM               969 Eclipse Java Mars.lnk
09/25/2015  02:35 PM             1,716 Git CMD.lnk
09/28/2015  02:54 PM             2,136 Git Shell.lnk
09/28/2015  02:52 PM               308 GitHub.appref-ms
11/10/2015  02:53 PM           524,288 putty.exe
               6 File(s)        566,454 bytes
               4 Dir(s)  403,115,601,920 bytes free

C:\Users\SWOSU\Desktop>cd AdditionGame

C:\Users\SWOSU\Desktop\AdditionGame>git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .classpath
        .project
        .settings/
        bin/
        src/

nothing added to commit but untracked files present (use "git add" to track)

C:\Users\SWOSU\Desktop\AdditionGame>git add .

C:\Users\SWOSU\Desktop\AdditionGame>git commit -m "Java code for addition game"
[master (root-commit) 5750e73] Java code for addition game
 5 files changed, 116 insertions(+)
 create mode 100644 .classpath
 create mode 100644 .project
 create mode 100644 .settings/org.eclipse.jdt.core.prefs
 create mode 100644 bin/AdditionGame.class
 create mode 100644 src/AdditionGame.java

C:\Users\SWOSU\Desktop\AdditionGame>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': aziz50
Password for 'https://aziz50@github.com':
Counting objects: 10, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (8/8), done.
Writing objects: 100% (10/10), 3.57 KiB | 0 bytes/s, done.
Total 10 (delta 0), reused 0 (delta 0)
To https://github.com/Aziz50/AdditionGame.git
 * [new branch]      master -> master

C:\Users\SWOSU\Desktop\AdditionGame>git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean

C:\Users\SWOSU\Desktop\AdditionGame>
Experiences:

Making this game was the most difficult part for me and I admit that your code on GitHub helped me a lot. I even copied the loops to understand how it works and tried to implement in my code also. 
I am trying my best to learn Java.

Thanks!


