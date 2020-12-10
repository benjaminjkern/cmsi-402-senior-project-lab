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

#### 2.1.1. Node Screen

The screen shall be comprised of information describing an artificial situation, along with a list of both canon options and non-canon options.

#### 2.1.2. Create Node Screen

The Create Node Screen shall have a utility that will allow for accurate communication of the situation this node is represented, as well as a smaller version of the suggest action screen.

#### 2.1.3. Suggest Action Screen

The Suggest Action Screen shall allow a user to suggest an action to a specific node. It will also allow the user to create a new node, or point this action towards an already existing node.

#### 2.1.4. User Information Screen

The User Information Screen shall allow the user to access all of the information regarding the user's account, including name, saved nodes, and created nodes and actions.

### 2.2. Administrative Backend

The backend of Crowdventure shall be an instance of Apollo GraphQL.

#### 2.2.1. Admin panel

With the proper administration, a user shall be able to access the admin panel, which will allow for direct access and manipulation of the database and running server.

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
