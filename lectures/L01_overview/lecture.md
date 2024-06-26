---
title: CS 326
separator: <!--s-->
verticalSeparator: <!--v-->

theme: serif
revealOptions:
  transition: 'none'
---

<div class="header-slide">

# Introduction to the Data Science Pipeline
## L.01 Overview & Logistics

**Instructor**: Joshua D'Arcy

Spring 2024

</div>
<!--s-->
## What is Data Science?

<div class = "col-wrapper">
  <div class="c1 col-centered" style = "width: 50%; align-items: center;">
    Data Science sits at the intersection of computer science, statistics, and domain expertise. It is the process of extracting knowledge and insights from data.
  </div>
  <div class="c2 col-centered" style = "width: 50%; align-items: center; text-align: center;">
    <div>
    <img src="https://cdn-images-1.medium.com/max/800/1*MuglQTETZNJCRp1iceE7-Q.png">
    <p><span style="font-size: 0.4em"> © Steven Geringer </span></p>
    </div>
  </div>
</div>

<!--s-->

## What is a Data Science Pipeline?

1. Data Source
2. Data Exploration
3. Data Preprocessing
4. Data Modeling
5. Data Interpretation
6. Data Action

CS 326 will cover the **fundamentals** of each step of the data science pipeline. We will go for breadth, but you will be encouraged throughout the quarter to go into depth.

<!--s-->

## Course Resources

Both Canvas and GitHub will be used extensively throughout this course.

<div class = "col-wrapper">
<div class="c1" style = "width: 50%">

[Canvas](https://canvas.northwestern.edu/courses/211880)
  - Syllabus (with links!)
  - Grades
  - Discussion threads*
  - Announcements
  - Panopto recordings
  - Project assignments

</div>
<div class="c2" style = "width: 50%">

[GitHub Repository](https://github.com/drc-cs/cs326)
  - Syllabus (with links!)
  - Lecture slides*
  - Homework assignments

</div>
</div>

<!--s-->


## Lecture Breakdown

Lectures will be broken down into theory and applications. Attendance at lectures is mandatory and in your best interests! Homework will be assigned at the end of each lecture.

| Component | Duration | Description |
| --- | --- | --- |
| Lecture | 55 minutes | Theoretical Foundations |
| Break | 5 minutes | ~ |
| Homework Lab | 20 minutes | Application and Practice |


<!--s-->

## Attendance

Attendance is mandatory. You may miss up two lectures without penalty. After that, you will lose 1% of your final grade for each additional missed lecture without a valid excuse.

<!--s-->

## Grading

There is a high emphasis on the practical application of the concepts covered in this course. 
<div class = "col-wrapper">
<div class="c1" style = "width: 50%">

| Component | Weight |
| --- | --- |
| Homework | 50% |
| Project | 30% |
| Quiz | 20% |

</div>
<div class="c2" style = "width: 50%">

| Grade | Percentage |
| --- | --- |
| A | 93-100 |
| A- | 90-92 |
| B+ | 87-89 |
| B | 83-86 |
| B- | 80-82 |
| C+ | 77-79 |
| C | 73-76 |
| C- | 70-72 |

</div>
</div>
<!--s-->

## Homework 

Homeworks are designed to reinforce the concepts covered in lecture. They will be a mix of theoretical and practical problems. If there is time, we will work on homework at the end of every lecture as a group. 

- **Due**: Homework due dates are posted in the syllabus.

- **Late Policy**: Late homeworks will lose 1 out of 10 points per day (1% of your final grade).

- **Platform**: A submission script has been provided to submit your homeworks, please see the first homework [README](https://github.com/drc-cs/cs326/tree/main/homeworks/H01) page for more information.

- **Collaboration**: You are encouraged to work with your peers on homeworks. However, you must submit your own work. Copying and pasting code from other sources will be detected and penalized.


<!--s-->

## Project

You will complete a team project over the course of the semester. The project contains deliverables outlined below. Due dates are posted in the syllabus and assigments are linked as they come up.

- **P.01 Project Proposal**: ~1 page proposal outlining the project, the data, and your group goals.

- **P.02 Milestone**: 10 minute status update, one per group. Elevator-style pitch deck encouraged. 

- **P.03 Presentation**: 20 minute presentation, one per group.

- **P.04 Final Report**: 2 page report, one per group.

Collective ambition and equal contribution is rewarded! A rubric will be posted shortly.

<!--s-->

## Quiz

There will be one quiz at the end of this course. 

- **Coverage**: The quiz will cover the theoretical and practical concepts covered in the course through a mini-project challenge that you will have 75 minutes to complete. 

- **Format**: The challenge will be styled in a format similar to an industry data science coding interview.

If you follow along with the lectures and homeworks, you will be well-prepared for the quiz. The goal is to give you practical code-interview style experience, not trip you up on small details.

<!--s-->

## Academic Integrity [[link]](https://www.northwestern.edu/provost/policies-procedures/academic-integrity/index.html)

### Homeworks

- Do not exchange code fragments on any assignments.
- Do not copy solutions from any source, including the web or previous CS 326 students.
- You cannot upload / sell your assignments to code sharing websites.

### Group project

- Do not use code/analysis from public website.
- Do not use code/analysis from a prior class.

<!--s-->

## Accommodations

Any student requesting accommodations related to a disability or other condition is required to register with AccessibleNU and provide professors with an accommodation notification from AccessibleNU, preferably within the first two weeks of class. 

All information will remain confidential.

<!--s-->

## Mental Health

If you are feeling distressed or overwhelmed, please reach out for help. Students can access confidential resources through the Counseling and Psychological Services (CAPS), Religious and Spiritual Life (RSL) and the Center for Awareness, Response and Education (CARE).

<!--s-->

## Stuck on Something?

### **Office Hours**

- Time: 12:20-1:30PM on Tuesdays and Thursdays (after lecture)
- Location: TBA

### **Canvas Discussion**

- Every homework & project will have a discussion thread on Canvas.
- Please post your questions there so that everyone can benefit from the answers!

### **Email**

- Chongyang and I are here to help you! We ask that you try the office hours and Canvas discussion first, but feel free to reach out to us via email if you are still stuck.
  - Chongyang Gao (TA): Chongyanggao2026@u.northwestern.edu<br>
  - Joshua D'Arcy (Instructor): joshua.darcy1@northwestern.edu

<!--s-->

<div class="header-slide">

# Homework Assignment
## H.01 "Hello World!"

Due: 04.02.2024

</div>

<!--s-->

## H.01 | Installing Conda

We will be using Python for this course. Conda is a package manager that will help us install Python and other packages. 

Link: https://docs.conda.io/en/latest/miniconda.html

<!--s-->

## H.01 | Cloning Repo & Installing Environment

We will be using a public GitHub repository for this course. Enter the following commands in your terminal to clone the repository and install the class environment.


```bash
git clone https://github.com/drc-cs/cs326.git
cd cs326
```

We will be using a conda environment (cs326) for this course. 

```bash
conda env create -f environment.yml
conda activate cs326
```

Don't have <span class="code-span">git</span> installed? [[click-here]](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

<!--s-->

## H.01 | VSCode

All demonstrations will be in VSCode, which is a popular IDE. You're welcome to use any IDE you want, but your TA and I will be best equipped to help you if you use VSCode.

Installation link: https://code.visualstudio.com/

After installing VSCode, you will need to install the Python extension: 

1. Open VSCode
2. Click on the "Extensions" icon in the "Activity Bar" on the side of the window
3. Search for "Python" and click "Install"

Add the <span class="code-span">code</span> command to your PATH so you can open VSCode from the terminal.

1. Open the "Command Palette" (Ctrl+Shift+P on PC or Cmd+Shift+P on Mac)
2. Search for "Shell Command: Install 'code' command in PATH" and click it

<!--s-->

## H.01 | Opening Repo in VSCode

Restart your terminal and open the cloned repository in VSCode using the following command:

```bash
code cs326
```

You should see the following folders:

- <span class="code-span">README.md</span>: Contains the course syllabus.
- <span class="code-span">lectures/</span>: Contains the lecture slides in markdown format.
- <span class="code-span">homeworks/</span>: Contains the homework assignments.

<!--s-->

## H.01 | Pulling

Before you start working on any homework, make sure you have the latest version of the repository.

The following command (when used inside the class folder) will pull the latest version of the repository and give you access to the most up-to-date homework:

```bash
git pull
```

If you have any issues with using this git-based system, please reach out to your TA or myself.

<!--s-->

## H.01 | Opening Homework

Open the <span class="code-span">homeworks/</span> folder in VSCode. You should see a folder called <span class="code-span">H.01/</span>. Open the folder and you will see three files: 

- <span class="code-span">hello_world.py</span>: This file contains placeholders for the methods you will write.

- <span class="code-span">hello_world_narrative.ipynb</span>: This is a Jupyter notebook that provides a useful narrative for the homework and methods found in the <span class="code-span">hello_world.py</span> file.

- <span class="code-span">hello_world_test.py</span>: This is the file that will be used to test your code. Future homeworks will not include this file, and this is for demonstration purposes only.

Let's do the first homework together.

<!--s-->
<div class = "header-slide">

 ## Homework Demonstration

</div>
<!--s-->

## H.01 | Submitting Homework

You will submit your homework using the provided submission script. 

But first, you need a username (your **northwestern** email) and password!

```bash
python account.py --create-account
```

Once you have a username and password, you can submit your completed homework. You should receive your score or feedback within a few seconds, but this may take longer as the homeworks get more involved.

```bash
python submit.py --homework H.01/hello_world.py --username your_username --password your_password
```

You can save your username and password as environment variables so you don't have to enter them every time (or expose them in your notebooks)!

```bash
export CS326_USERNAME="your_username"
export CS326_PASSWORD="your_password"
```

<!--s-->

## H.01 | Homework Grading

The highest score will be recorded, so long as it is submitted before the deadline! You have 3 attempts for every homework. 

Late homeworks will be penalized 10% per day.

<!--s-->

## H.01 | Expected Learnings / TLDR;

With this <span class="code-span">hello_world</span> assignment, we worked on the following:

1. Environment installation practice (<span class="code-span">conda</span>)
2. Exposure to git management (<span class="code-span">GitHub</span>)
3. Local development IDE practice (<span class="code-span">vscode</span>)
4. Familiarity with unit testing (<span class="code-span">pytest</span>)

These tools are all critical for any industry position and are often expected for entry level positions. Please continue to familiarize yourself with them over the course of the quarter.

<!--s-->

<div class="header-slide">

# Questions?

</div>

<!--s-->







