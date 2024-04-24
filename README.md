-------------
query GamesQuery {
  games{
    id,
    title,
    platform
  }
}

---------------
query AuthorsQuery {
  authors{
    name,
    verified
  }
}
-------------
query gameQuery($id:ID!) {
  author(id: $id) {
    id,
    name,
    reviews {
      rating,
      content
    }
    
  }
  
}

-------------

query ReviewQuery($id:ID!) {
  review(id: $id) {
   rating,
    game {
      platform,
      title
    },
    author {
      name,
      verified
    } 
  }
  
}
*****{
  "id": "1",
 
}

-----------------

mutation DeleteMutation($id:ID!) {
  deleteGame(id:$id){
    id,
    title,
    platform
  }
}

*****{
  "id":"2"
}

-----------------
mutation AddMutation($game:AddGameInput!) {
  addGame(game:$game){
    id,
    title,
    platform
  }
}
****{
    "game": {
        "title": "a new game",
        "platform": [
          "Switch"
        ]
        
    }
}
-------------
mutation EditMutation($edits:EditGameInput!, $id:ID!) {
 updateGame(edits:$edits, id:$id){
    id,
    title
  }
}

*****{
    "edits": {
        "title": "bridgerton ",  
    },
    "id":"2"

}
