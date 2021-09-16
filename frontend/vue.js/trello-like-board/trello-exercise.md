# Trello exercise:

The purpose of the test is to create a personal projects organizer web app using Trello's APIs as a backend. The feature scope for the test is the following:
- List all boards
- Given a selected board, show the "lists" and "cards" associated to the board. Remember 1 board -> many lists, 1 list -> many cards.
- Create a card by giving just the field "name".
- Move cards around lists, this is, user can drag and drop a card from any list to another  (optional with big plus).

Find attached to this description a trello snap for the exercise, this will play as a wireframe. Please note that the black rectangles indicates the areas to be implemented, everything else is not needed.

Free admin dashboard for visual resources if needed (this is optional): https://github.com/mrholek/CoreUI-React

Trello Account Login:

    Login: https://trello.com/login
    User: roque@eurekalabs.io
    Pass: EurekaLabs!

### Tech Stack
- NodeJS 8.X: https://nodejs.org/en/download/current/
- React 16: https://github.com/facebook/react

Feel free to use the preferred dev environment and also any other framework that facilitates development.

### Quick Reference
API Docs: https://developers.trello.com/v1.0/reference

- API key: e327c3e08523d8b0c0efca2189a7b372
- Token: fbb3cb59c7c63472fc502a0b65fb79b99e8e5fc1aef520492ccbd9308f56b147

#### Get All Boards
    Synopsis:
    GET https://api.trello.com/1/members/roqueperalta2/boards?key=[key]&token=[token]

    Example:
    GET https://api.trello.com/1/members/roqueperalta2/boards?key=e327c3e08523d8b0c0efca2189a7b372&token=fbb3cb59c7c63472fc502a0b65fb79b99e8e5fc1aef520492ccbd9308f56b147

#### Get All Boards selecting name and id fields only
    Synopsis:
    GET https://api.trello.com/1/members/roqueperalta2/boards?key=[key]&token=[token]&fields=[comma separated fields list]

    Example:
    GET https://api.trello.com/1/members/roqueperalta2/boards?key=e327c3e08523d8b0c0efca2189a7b372&token=fbb3cb59c7c63472fc502a0b65fb79b99e8e5fc1aef520492ccbd9308f56b147&fields=name,id

#### Get the "New Office Setup" board with the associated lists (just id and name for them)
    Synopsis:
    GET https://api.trello.com/1/boards/[id-board]?fields=[comma separated fields list]&lists=open&list_fields=id,name&key=[key]&token=[token]

    Example:
    GET https://api.trello.com/1/boards/59cd98e6484b7bbd8b814879?fields=id,name&lists=open&list_fields=id,name&key=e327c3e08523d8b0c0efca2189a7b372&token=fbb3cb59c7c63472fc502a0b65fb79b99e8e5fc1aef520492ccbd9308f56b147

#### Get Cards from list "To Do" (3 fields are selected)
    Synopsis:
    GET https://api.trello.com/1/lists/[list-id]/cards?fields=[comma separated field list]&key=[key]&token=[token]

    Example:
    GET https://api.trello.com/1/lists/59cd98e6484b7bbd8b81487a/cards?fields=id,name,desc&key=e327c3e08523d8b0c0efca2189a7b372&token=fbb3cb59c7c63472fc502a0b65fb79b99e8e5fc1aef520492ccbd9308f56b147

#### Move card from one list to another
    Synopsis:
    PUT https://api.trello.com/1/cards/[card-id]?idList=[id-list]&key=[key]&token=[token]

    Example:
    PUT https://api.trello.com/1/cards/59cd9df1a115d8f3fe612844?idList=59cd98e6484b7bbd8b81487b&key=e327c3e08523d8b0c0efca2189a7b372&token=fbb3cb59c7c63472fc502a0b65fb79b99e8e5fc1aef520492ccbd9308f56b147

#### Post a Card with name "Test"
    Synopsis:
    POST https://api.trello.com/1/cards?idList=[id-list]&name=[card-name]&key=[key]&token=[token]

    Example:
    POST https://api.trello.com/1/cards?idList=59cd98e6484b7bbd8b81487a&name=Test&key=e327c3e08523d8b0c0efca2189a7b372&token=fbb3cb59c7c63472fc502a0b65fb79b99e8e5fc1aef520492ccbd9308f56b147
