# 1. Hello Assignment!
This is an introductory assignment for you (the student) to learn how to submit programming assignments using GitHub. All programming assignments throughout the semester will follow the same procedure.

When run, the program prints the incorrect phrase to the console. Your task is to change the phrase to say `Hello assignment!`. Check the `main` method in the `Hello.java` file.

Note: you should ***NOT*** change any other files.

# 2. Requirements

## 2.1 GitHub
To be able to download and submit your programming assignments, you will need to first create a GitHub account:
1. Go to [GitHub.com](https://github.com) and click to sign up.
1. Provide your email address.
1. Create a password.
1. Choose a GitHub username.

Note: GitHub is extremely popular and used by developers around the globe. Even if you don't like the idea of creating an account for this course, chances are you will likely have to do it in the future!

## 2.2 IntelliJ IDEA
As the IDE of choice, we will be using IntelliJ IDEA. The reason is because it works with minimal configuration if compared with other IDEs, such as Eclipse. You have 2 options: install IntelliJ on your own computer, or use the Virtual Machine provided by Southeastern.

### 2.2.1 Using the VM
To use the VM:
1. In your browser, visit the [CMPS VM website](https://desktop.southeastern.edu).
1. Login using your W#.
1. Choose the **CMPS Lab** VM.
1. After loging in, it is just as if you were in front of a computer in the classroom. You can open IntelliJ now.
    ![CMPS VM IntelliJ](/images/1.png)

The downside is that you will be working over the Internet, on your web browser, so it will rely on your Internet connectivity.

### 2.2.2 Install IntelliJ locally
If you choose to install it on your own computer:
1. Go to [IntelliJ's website](https://www.jetbrains.com/idea/) (JetBrains is the company that maintains the IntelliJ IDEA):
1. Download the installation file, make sure you select the one specific to your operatin system: [download link](https://www.jetbrains.com/idea/download)
1. Execute the installation, choosing the options along the way. (Tip: the defaults are usually good enough and I just keep clicking `Next`/`Finish`)
1. After finishing the installation, you can open IntelliJ

    ![CMPS VM IntelliJ](/images/1a.png)

# 3. Accepting this assignment
The first time you accept an assignment GitHub will link your GitHub account with the GitHub Classroom:
1. On [Moodle](https://moodle.selu.edu), log in and visit the CMPS 280 course page.
1. Go to the `Getting started` section. In this section you will find a copy of this document you are reading right now.
1. Click on the `Hello assignment` link.
1. Click to accept the assignment.
    1. It will open a website and list all stutents enrolled in this class

        ![Roster](/images/2.png)

    1. Select YOUR name on the list:

        ![Select name](/images/2a.png)

1. Now that your account is linked, you can ***accept this assignment***

    ![Accept assignment](/images/3.png)

    ![Preparing repository](/images/4.png)

1. After accepting, GitHub will create a ***repository***\* for you, and only you.

    ![Repository created](/images/5.png)

    If the page doesn't refresh automatically, click refresh on your browser, it will have a link to your repository that you can then visit.

    ![Repository ready](/images/6.png)

\* A repository is like a folder that contains the files of a project. You will use it as a starting point and update your GitHub repository to submit your assignment.

# 4. Cloning (i.e. downloading/copying) the repository to your workstation
Now that you:
1. Have a GitHub account
1. Accepted the first programming assignment from GitHub Classroom
1. Linked your GitHub account to the class roster

It's time to:
1. Connect IntelliJ with your GitHub account

    1. Open IntelliJ IDEA
    1. Click on `Get from VCS` button

        ![IntelliJ Get from VCS screen](/images/7.png)
    
        Note: VCS stands for **V**ersion **C**ontrol **S**ystem, which in our case is Git/GitHub.

    1. Select `GitHub` on the left panel (***NOT*** the other options)

        ![IntelliJ GitHub](/images/8.png)

    1. Click `Log In via GitHub`
    1. Once you click the `Log In via GitHub` button, it will open a browser window and ask you to `Authorize on GitHub`
        
        ![IntelliJ Log In via GitHub button](/images/9.png)

    1. Authorize IntelliJ to have access to your GitHub account, make sure that `Southeastern-Louisiana-University` is also shared :white_check_mark: and click the `Authorize JetBrains` button
        
        ![GitHub auth page](/images/10.png)

    1. After authorizing, it will return you to the JetBrains page, and if successfull will show you a message that you can close the browser now. Go ahead and close it!

        ![Successfully authorized](/images/11.png)

1. ***Clone*** (i.e. download) the repository using IntelliJ
    
    Now that you have connected your IDE to your GitHub account, you can proceed to download the assignment files from your repository to your computer:
    
    1. In the initial IntelliJ scree, click on `Get from VCS`, then on the left panel select `GitHub`. Now instead of asking you to link your account, it will list all the repositories your account has access to
    1. Your screen will look different than mine, scroll until you find the `Southeastern-Louisiana-University/cmps-280---hello-assignment-<YOUR GITHUB USERNAME HERE>` repository, then click `Clone`

        Note: you can change the default folder that it will download the files to. I recommend the default one though.

        ![IntelliJ List of repositories](/images/12.png)

        ![IntelliJ Cloning screen](/images/13.png)

    1. After cloning the files to your computer, the IDE will then setup the project by setting up `Gradle` (we don't need to know what it is for this course!). This is automatic and shouldn't take more than a minute or two. After that, you are ready to work on the assignment

        ![IntelliJ Preparing project](/images/14.png)

        ![IntelliJ Project ready](/images/15.png)


# 5. Solve the assignment

1. Understand the problem

    Now that you have a copy of the assignment files on your computer you can use IntelliJ to solve the assignment. For future assignments, the instructions will be the first thing you read in the `README.md` file (this file that you are reading right now). You can scroll up and check it out, but I'll copy the exact same text here:

    > This is an introductory assignment for you (the student) to learn how to submit programming assignments using GitHub. All programming assignments throughout the semester will follow the same procedure.
    > 
    > When run, the program prints the incorrect phrase to the console. Your task is to change the phrase to say `Hello assignment`. Check the `main` method in the `Hello.java` file.
    > 
    > Note: you should ***NOT*** change any other files.

    Take a moment to look at the project file structure:

    ![Project structure](/images/16.png)

    Open up the source files the assignment pointed out (`Hello.java`, and `TestHello.java`)

    * `src/Hello.java`:

        ```java
        public class Hello {
            public static void main(final String[] args) {
                System.out.println("Hello world!");
            }
        }
        ```

    * `src/TestHello.java` (you ***must not*** edit this file, but you can always peek!):

        ```java
        import static org.junit.jupiter.api.Assertions.assertEquals;
        import org.junit.jupiter.api.Test;
        import java.io.*;

        public class TestHello {
            @Test
            public void testHelloWorld()
            {
                PrintStream originalOut = System.out;
                ByteArrayOutputStream bos = new ByteArrayOutputStream();
                System.setOut(new PrintStream(bos));
                // action
                Hello.main(null);
                // assertion
                assertEquals("Hello assignment!\n", bos.toString());
                // undo the binding in System
                System.setOut(originalOut);
            }
        }
        ```

    The IDE provides a lot of stuff to help us out: compiling and running, testing, debugging.. I can't list them all, it's a lot! For this course, you only need to know how to ***run*** and ***test*** your program.

1. Running the program

    Running the program is something you will be doing very often when solving a programming assignment. It usually involves in creating a file that has the `public static void main(String[]) { ... }` method. For this assignment that is the `Hello.java` file.

    1. Right click the `Hello` file from the project explorer panel and select `Run 'Hello.main()'`

        ![Running the program](/images/17.png)

    1. That's it! Wait a few moments for IntelliJ to compile and run the program, you can see the output of the program in the console panel

        ```bash
        11:35:00: Executing ':Hello.main()'...
        > Task :compileJava
        > Task :processResources NO-SOURCE
        > Task :classes
        > Task :Hello.main()
        Hello world!

        BUILD SUCCESSFUL in 6s
        2 actionable tasks: 2 executed
        11:35:07: Execution finished ':Hello.main()'.
        ```

        We can see that the program compiled and ran according to what we would expect (look at the `Hello.java` file! All it does is print a message to the console...)

1. Running the test (optional)

    Testing is a whole beast on its own. For all our intents and purposes, we will NOT learn to create any tests. All tests will be already included in the assignment repositories for you. In our course, tests will be used for grading purposes only, you don't even need to understand how to run them. However, it might be useful to know that you can run the tests directly from IntelliJ. If the tests ***pass*** when you run it, you can be sure that they will also test when the instructor runs them to generate your grade. If the tests ***fail***, then you know you have something to fix in the program files.

    1. Right click on `TestHello` frpom the project explorer panel, then click on `Run 'TestHello'`

        ![Run unit tests](/images/18/png)

    1. The tests **WILL** fail! That's the point, the assignment requires you to edit the source code in order for the tests to **PASS**. So, naturally, if we don't change anything and just run the tests, they will fail

        ![Tests failed](/images/19.png)

        If you take a look at the messages in red in the console, you may notice exactly why the tests failed (the actual message is more verbose, only the useful parts are listed below):

        ```bash
        > Task :compileJava UP-TO-DATE
        > Task :processResources NO-SOURCE
        > Task :classes UP-TO-DATE
        > Task :compileTestJava
        > Task :processTestResources NO-SOURCE
        > Task :testClasses
        > Task :test

        expected: <Hello assignment!
        > but was: <Hello world!
        >

        1 test completed, 1 failed
        > Task :test FAILED
        ````

        As we can see, the program is printing the string `Hello world!`, but the correct one should be `Hello assignment!` (just like the assignment description at the beginning of this document)

1. Fixing the program (i.e. doing what the assignment asked us to do, finally!)

    The assignment asked us to fix the string that the program is printing. After exploring and understanding the source-code, we should see that the issue is in the `Hello` file:

    Let's change the source code from: 

    ```java
    public class Hello {
        public static void main(final String[] args) {
            System.out.println("Hello world!"); // This is WRONG, we need to fix it!
        }
    }
    ```

    To:
    ```java
    public class Hello {
        public static void main(final String[] args) {
            System.out.println("Hello world!"); // This is WRONG, we need to fix it!
        }
    }
    ```

    1. Re-run the program (right click `Hello`, select `Run 'Hello.main()'`)

        After fixing it, we can check if our change actually worked by running the program again, and it **did**!

        ```bash
        11:58:33: Executing ':Hello.main()'...
        > Task :compileJava
        > Task :processResources NO-SOURCE
        > Task :classes

        > Task :Hello.main()
        Hello assignment!
        ```
    
    1. (**Optional:**) Re-run the test (right click `TestHello`, select `Run 'TestHello`)
    
        We can also run the test again, and double-check that the test now passes, and it **does**!

        ```bash
        > Task :compileJava UP-TO-DATE
        > Task :processResources NO-SOURCE
        > Task :classes UP-TO-DATE
        > Task :compileTestJava
        > Task :processTestResources NO-SOURCE
        > Task :testClasses
        > Task :test
        TestHello > testHelloWorld() PASSED
        BUILD SUCCESSFUL in 10s
        ```

Awesome! The assignment is now ready to be submitted.

# 6. Submit the assignment

To submit the assignment we will be using IntelliJ and GitHub once more. Because we have gone through all that work of connecting them at the beginning, submitting an assignment is actually pretty simple.

1. On the very left of the IDE, there are some "vertical" buttons, click on `Commit`, right below the `Project`. It will bring up the ***Commit*** and ***push*** panel

    The top part will list all the files that have been changed. In this case we only changed the `Hello` file, so that's what is listed there.

    ![IntelliJ Commit and push](/images/20.png)

1. In the commit panel, write a useful message summarizing the modifications you made to the code, such as `Changed printed string`. Now we are ready to submit

    ![IntelliJ Commit and push button](/images/21.png)

1. ***VERY IMPORTANT!!!*** To submit the assignment click on `Commit and Push...` button, and NOT just `Commit`. If you click `Commit`, the IDE will NOT upload the files, will only change it on your computer, not on GitHub. IntelliJ will open a window listing the changes

    ![IntelliJ Commit and push result](/images/22.png)

    Note: this is a part of how Git/GitHub works: you can `commit` several changes to the local files before you `push` (actually upload) those changes to the GitHub repository. You can read more about git/GitHub [here](https://docs.github.com/en/get-started).

Done! Now you can wait a few minutes before chacking your grade! You can close IntelliJ now and take a break.

## 6.1 Check on GitHub Classroom if the solution worked

After submitting your assignment, GitHub will check automatically if your solution worked. This process might take a few minutes though, so don't be alarmed if it doesn't happend instantly.

1. In your browser, go to your assignment's repository [https://github.com/Southeastern-Louisiana-University/cmps-280---hello-assignment-YOUR USERAME HERE](https://github.com/Southeastern-Louisiana-University/cmps-280---hello-assignment-YOUR USERAME HERE)

    ![GitHub repository](/images/23.png)

1. Click on `Actions` at the top menu

    ![Github repo actions](/images/24.png)

1. Check that the `workflow` passed with a green checkmark (i.e. GitHub running the tests), if so, you're done with this assignment!

    Notice that the message that you wrote when submitting (commit/push) is shown in the list

    ![GitHub actions result](/images/25.png)

    ***Note:*** if your solution was incorrect, you would se a red mark (:x:) instead! You can go back to IntelliJ and try to fix it again. If you're stuck and need help, ask the Instructor for assistance. If you think your solution is correct and the grading is wrong, contact the Instructor! You can submit several times before the assignment deadline.

## Next assignments
It may sound like a lot of steps, and it might take you some practice, but once you get a hang it becomes easier and you won't even think about it. And now that you have done the boring part of creating and linking your account, the next assignments won't need all this boring work again.

For the next programming assignments, you won't have to create a GitHub account and configure your IDE all over again. This part is done. The next assignments will only need you to:

1. Accept the assignment when posted on Moodle
1. ***Clone*** the assignment repository (using IntelliJ)
1. Solving the assignmen`
    1. Running, editing, testing...
1. Submitting (`commit` and `push`) the assignment
    1. If GitHub shows the red 'x' (:x:), you can fix it and submit it again, as many times as you want, or contact the instructor if you think your solution is correct but GitHub still fails with :x:
    1. If GitHub shows the green checkmark (:white_check_mark:), go do something fun!

## Notes
- Although IntelliJ will be used by the instructor, and support will be given if you encounter any issues, you are still free to use other programs such as Eclipse, JGrasp, NetBeans, VSCode. However, the instructor might not be able to provide enough support to configure should you face any issues downloading/solving/submitting the assignment.
- This example project is written in Java, and tested with Gradle/JUnit. You do not need to worry about it, only if you are curious to know what it is, in which case I'll be happy to chat about it.
