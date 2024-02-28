---
toc: True
comments: True
layout: default
title: CPT Final
description: Final reflection on my contributions to our CPT project
type: tangibles
courses: {'compsci': {'week': 12}}
---

<style>
    * {
        color: white
    }
</style>

# Project Overview

Our team set out to develop a simple button creator in which novice programmers could experiment with button CSS and animation in a graphic way to learn and share their ideas. Users are able to create and customize buttons which they can then publish.

---

# My Feature

The feature I designed was our button modifier webpage:
On this page, users are able to edit information regarding their buttons such as width, height, animation, and more. This button is then saved to their profile in a database and they can adjust the visibility of the button between public and private. 

# Component A: Program Code

| Collegeboard Requirements | My Project|
|------------------|------------------|
| Instructions for input from one of the following: the user, a device, an online datas stream, a file.  | My feature takes in user input in the form of sliders, color pickers, and button inputs. |
| Use of at least one list (or other collection type) to represent a collection of data that is stored and used to manage program complexity and help fulfill the users purpose.  | One example of a collection of data that I use is the backend which stores the string of html code and animation code that is displayed to the user. It fulfills the users request by allowing the user to save and look at other users designs. The data is stored in an SQLite database table and uses fetch requests to pass information back and forth between frontend and backend. |
| At least one procedure that contributed to the program's intened purpose where you have defined: the name, return type, one or more parameters:  | The procedure below has a name(saveButton), a return(response), and parameters(body): ![](../../../images/Screenshot 2024-02-27 203732.png) |
| An algorithm that includes sequencing, selection, and iteration that is in the body of the selected procedure | The following function shows sequencing, selection, and iteration through a list of users and user designs: ![](../../../images/Screenshot 2024-02-27 203611.png) |
| Calls to your student-developed procedure: | Calling saveButton: ![](../../../images/Screenshot 2024-02-27 203747.png) |
| Instructions for output (tactile, audible, visual, or ) based on input and program functionality  | This code is the function that displays updates to the button after the user changes settings: ![](../../../images/Screenshot 2024-02-27 203850.png) <br> ![](../../../images/Screenshot 2024-02-27 203906.png) |

# Component B: Video

[Link to Video](https://drive.google.com/file/d/14J6lcmIkmGH3bsDo6qAQkT_1NQKcuso3/view?usp=sharing)


| Collegboard Requirements | My Video |
|------------------|------------------|
| Input to program  | Seen in video, editing button configurations to user's liking  |
| At least one aspect of the functionality of your program | The button editor functionality which saves the button to backend and is visible to all, depending on selected visibility.  |
| Output produced by program:  | Newly created and edited button that can also be configured with animations.  |
| My video does not have: | Any distinguishing information and voice narration  |
| My video is | A .mp4, less than 1 minute in length, less than 30MB in file size.  |