# Crowdventure Software Requirements Document

> By Ben Kern

## Table of Contents

1. Introduction
2. Functional Requirements
   1. Graphical User Interface (GUI)
      1. Node Screen
      2. Create Node Screen
      3. Suggest Action Screen
      4. User Information Screen
   2. Administrative Backend
      1. Admin Panel
3. Performance Requirements
   1. Database
   2. Server
4. Environment Requirements
   1. Development Environment Requirements
   2. Execution Environment Requirements

---

## 1. Introduction

Crowdventure is a crowd-sourced choose-your-own-adventure game. Users will be able to navigate and play other user’s games, as well as suggest their own options for the game. The owner of the specific node can decide from all suggested options which ones they want to include as “canonical options”, though all users will also be able to scroll through all options - canon and non canon, and leave likes or dislikes on them. Any time a new suggested situation is created, the user who suggested it becomes the owner of that node, and they can decide which suggested options are canon and non canon.

## 2. Functional Requirements

Crowdventure is comprised entirely of the Graphical User Interface and the Administrative Backend.

### 2.1. Graphical User Interface (GUI)

The Graphical User Interface for the application provides the user with a way to select the desired function from those which are available in the application. An overlay that allows the user to access settings and user information is always present on each page.

#### 2.1.1. Navbar

1. All parts of the GUI shall contain a Navbar.
2. The Navbar shall have a link to route to the home screen.
3. The Navbar shall allow users to sign in to accounts, or sign up for an account.
4. While signed in, the Navbar shall display to the user the account they are signed in
5. While signed in, the Navbar shall contain a button to allow them to visit the Account page associated with the account they are signed in as.

#### 2.1.2. Home Screen

1. The Home Screen Shall allow users to traverse to various "Featured" pages.
2. All pages shown in the Home screen shall have a title.
3. All pages shown in the Home screen shall have a link to take you to the page.
4. All pages shown in the Home screen shall allow a user to see the owner of the page.

#### 2.1.3. Node Screen

1. The Node screen shall display information describing an artificial situation.
2. The Node screen shall allow the owner of a node to be able to delete the node.
3. The Node screen shall provide the user with a list of both canon options and non-canon options.
4. The Node screen shall allow all users to click the canon and non-canon choices, and go to the following node pages.
5. The Node screen shall allow the owner of a node to be able to edit its content.
6. The Node screen shall allow the owner of a node to be able to delete the node.
7. The Node screen shall allow a signed in user to create a new action stemming from the current node.
8. The Node screen shall allow a signed in user to create a new page stemming from a new action.
9. The Node screen shall allow a signed in user to connect a new action to an existing node.

#### 2.1.4. Account Screen

1. The account screen shall display information about a particular account.
2. The account screen shall display all nodes owned by the associated account.
3. The account screen shall allow users to traverse all nodes owned by the account.
4. The account screen shall allow the owner of the account to edit its bio.
5. The account screen shall allow the owner of the account to delete the account.
6. The account screen shall allow the owner of the account to create a new node from scratch.

### 2.2. Administrative Backend

The backend of Crowdventure shall be an instance of Apollo GraphQL.

#### 2.2.1. API Calls

1. An administrative user shall be able to retrieve all nodes.
1. An administrative user shall be able to retrieve all accounts.
1. An administrative user shall be able to retrieve all choices.
1. An administrative user shall be able to retrieve a particular node.
1. An administrative user shall be able to retrieve a particular account.
1. An administrative user shall be able to retrieve a particular choice.
1. An administrative user shall be able to create a new node.
1. An administrative user shall be able to create a new account.
1. An administrative user shall be able to create a new choice.
1. An administrative user shall be able to edit an existing node's title and content.
1. An administrative user shall be able to edit an existing account bio and associated nodes and choices.
1. An administrative user shall be able to edit an existing choice action and associated node.
1. An administrative user shall be able to delete an existing node.
1. An administrative user shall be able to delete an existing account.
1. An administrative user shall be able to delete an existing choice.

## 3. Performance Requirements

The performance of Crowdventure is largely dependent upon the database and server that it is built upon.

### 3.1. Database

#### 3.1.1. The backend of Crowdventure shall be able to access the database in a timely manner.

#### 3.1.2. The database that holds the information of Crowdventure shall be large enough to hold all of the data created by its users.

#### 3.1.3. The database shall be as scalable as possible.

### 3.2. Server

The frontend of Crowdventure shall be able to access and manipulate the server(s) that Crowdventure is running on in a timely manner.

## 4. Environment Requirements

### 4.1. Development Environment Requirements

To develop Crowdventure, a computer with access to the internet, as well as an IDE shall be available and is required.

### 4.2. Execution Environment Requirements

All that is required for a user to access and interact with Crowdventure is a computer with a working web browser and access to the internet.
