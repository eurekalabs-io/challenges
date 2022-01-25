# Trello exercise:

The purpose of the test is to create a personal projects organizer web app using Trello's APIs as a backend. The feature scope for the test is the following:
- List all boards
- Given a selected board, show the "lists" and "cards" associated to the board. Remember 1 board -> many lists, 1 list -> many cards.
- Create a card by giving just the field "name".
- Move cards around lists, this is, user can drag and drop a card from any list to another  (optional with big plus).

Find attached to this description a trello snap for the exercise, this will play as a wireframe. Please note that the black rectangles indicates the areas to be implemented, everything else is not needed.

### Tech Stack
- Angular 12 or newer. 

### Quick Reference
API Docs: https://developers.trello.com/v1.0/reference

You should be able to sign up in trello for free, then get the API key + Token so you can connect the backend piece.

Please visit https://trello.com/app-key to get your key and secret (token)

#### Get All Boards
    Synopsis:
    GET https://api.trello.com/1/members/[trello-username]/boards?key=[key]&token=[token]

#### Get All Boards selecting name and id fields only
    Synopsis:
    GET https://api.trello.com/1/members/[trello-username]/boards?key=[key]&token=[token]&fields=[comma separated fields list]

#### Get the "New Office Setup" board with the associated lists (just id and name for them)
    Synopsis:
    GET https://api.trello.com/1/boards/[id-board]?fields=[comma separated fields list]&lists=open&list_fields=id,name&key=[key]&token=[token]

    Example:
    GET https://api.trello.com/1/boards/59cd98e6484b7bbd8b814879?fields=id,name&lists=open&list_fields=id,name&key=[key]&token=[token]

#### Get Cards from list "To Do" (3 fields are selected)
    Synopsis:
    GET https://api.trello.com/1/lists/[list-id]/cards?fields=[comma separated field list]&key=[key]&token=[token]

    Example:
    GET https://api.trello.com/1/lists/59cd98e6484b7bbd8b81487a/cards?fields=id,name,desc&key=[key]&token=[token]

#### Move card from one list to another
    Synopsis:
    PUT https://api.trello.com/1/cards/[card-id]?idList=[id-list]&key=[key]&token=[token]

    Example:
    PUT https://api.trello.com/1/cards/59cd9df1a115d8f3fe612844?idList=59cd98e6484b7bbd8b81487b&key=[key]&token=[token]

#### Post a Card with name "Test"
    Synopsis:
    POST https://api.trello.com/1/cards?idList=[id-list]&name=[card-name]&key=[key]&token=[token]

    Example:
    POST https://api.trello.com/1/cards?idList=59cd98e6484b7bbd8b81487a&name=Test&key=[key]&token=[token]
