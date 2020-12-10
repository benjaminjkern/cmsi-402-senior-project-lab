# Crowdventure Software Test Plan

> By Ben Kern

## Table of Contents

1. Introduction
2. Unit Test Plan
   1. Unit Tests Planned
   2. Unit Test Procedures
3. Integration Test Plan
   1. Integration Tests Planned
   2. Integration Test Procedures
4. Acceptance Test Plan
   1. Acceptance Tests Planned
   2. Final Acceptance Test Procedures
5. Test Configuration Control
6. Items Not Tested
7. Test Verification Matrix

## 1. Introduction

Begin by describing the purpose and contents of this section of your document.

## 2. Unit Test Plan

### 2.1. Unit Tests Planned

- 1 unit test per search function on the backend, verify that all items returned contain the proper query
- All Date Created Endpoints: Should return 'Before September 16, 2020' if null.
- Accounts:
  - nodes: should return all nodes owned by the account, verify that there aren't nodes that exist outside of the returned list.
  - totalNodeViews: Should count all node's views. Run with a few positive and negative test examples.
  - totalSuggestionScore: Should count the total suggestion score of all suggestions. Run with positive and negative test examples.
- Nodes:
  - content: should add to views if the IP is unique
  - views: should count the views set, and reset it back to a set and set previouslySaved if the data gets turned into a number somehow.
  - nonCanonChoices: Should return in sorted order, based on the score, verify sorted order.
  - size: should return the total number of connected nodes to this page, positive and negative tests.
  - parents: should return all nodes that can lead to this one, verify there aren't nodes that should have been returned that didn't, as well as verify all nodes returned are actually parents.
- Mutations:

  - createAccount: Should fail if the screenName or password dont exist, or if the account screen name already exists, or if the account name has a bad word in it. Verify the account was created afterwards.
  - deleteAccount: should fail if the account doesnt exist, should also delete all suggested choices and created nodes. Verify that there arent nodes or choices that were created by the account. Verify the account doesnt exist afterwards.
  - editAccount: should fail if the account doesnt exist, shouldnt write if new bio or screenname contain bad words, and changing the screen name should change all nodes and choices owned by the account. Also verify that a copy account isnt created on screenname change
  - loginAccount: Should fail if the account doesnt exist, and only allow in if the password is correct, or if the password is null and the ip matches the stored ip.

  - createNode: Should fail if the owner doesnt exist, or if the title or content are empty. Should also automatically hide the page if the title or content contain bad words. Verify the node was created and exists in the owner's owned nodes.
  - deleteNode: Should fail if the node doesnt exist, and should remove the node from the owner's owned nodes, as well as remove the choices stemming from this node. Should not remove nodes that lead to this one. Verify the node doesnt exist afterwards in the main nodes list or in the owner's owned nodes.
  - editNode: Should fail if the node doesnt exist, and should hide the page if the title or content contains bad words.

  - suggestChoice: should fail if the owner doesnt exist, or if the to or from nodes dont exist, or if the action is empty. Should hide the choice if the action contains bad words. Verify the choice exists, under all choices, as well as under the from node, as well as under the owner afterwards.
  - removeSuggestion: should fail if the choice doesnt exist. Should remove the choice from the node as well as the owner.
  - editSuggestion: should fail if the choice doesnt exist, and should flag the content if the action contains a bad word.

  - switchCanon: should fail if the choice or the node doesnt exist, should put the choice into the opposite list in the node. Verify no duplication.
  - like/dislike: should fail if the choice, or account doesnt exist. Should switch lists of the choice

### 2.2. Unit Test Procedures

For the unit tests, all that is necessary is running the test suite, verify they all pass.

## 3. Integration Test Plan

### 3.1. Integration Tests Planned

- Database calls: There will be a single suite, that calls in order: - createAccount - editAccount (with profile pic and bio) - getAccount (verify all information is present) - loginAccount (verify that it wont work with no or incorrect password) - createNode (with account) - editNode (change content and picture) - getNode (verify all information is present) - suggestChoice - editChoice (edit action and to node) - getChoice (verify) - like/dislike choice - getChoice (verify) - canonize/decanonize choice - getChoice (verify) - removeChoice - removeNode - removeAccount
  It should be done in this order because you need an account to create a node, and you need a node to create a choice.
- Frontend calls to backend
  - Test suite from the frontend, that just makes several calls and verifies that they all run. Exact same calls from backend tests, just called from the front end.

### 3.2. Integration Test Procedures

Run the test suite, verify all tests passed.

## 4. Acceptance Test Plan

### 4.1. Acceptance Tests Planned

1. Verify that one can go to the website.
2. Verify that one can create an account from the frontend
3. Verify that one can log in to an account from the frontend
4. Verify that one can see account information from the frontend
5. Verify that one can go to pages and see information as well as images and choices from the frontend.
6. Verify that all owned information is editable on the frontend
7. Verify that all owned information can be deleted from the frontend
8. Verify that there are no graphical artifacts on the frontend

### 4.2. Final Acceptance Test Procedures

Perform all tests at a computer with a web browser, verify all pass.

## 5. Test Configuration Control

There will be two test suites on the backend, one for unit and the other for integration (database call) tests, and one integration test on the frontend, that will be available via an admin panel.

## 6. Items Not Tested

- Resolvers that just call database functions will not be unit tested. This includes allAccounts, allNodes, allChoices, getAccount, getNode, and getChoice.

## 7. Test Verification Matrix

| Requirement                       | Verification Test                          |
| --------------------------------- | ------------------------------------------ |
| 1. Graphical User Interface (GUI) | Frontend                                   |
| 1.1. Node Screen                  | Frontend Integration + Frontend Acceptance |
| 1.2. Create Node Screen           | Frontend Integration + Frontend Acceptance |
| 1.3. Suggest Action Screen        | Frontend Integration + Frontend Acceptance |
| 1.4. User Information Screen      | Frontend Integration + Frontend Acceptance |
| 2. Administrative Backend         | Backend                                    |
| 2.1. Admin Panel                  | Database Integration + Unit                |
