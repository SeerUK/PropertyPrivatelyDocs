
# API

All resource paths should require the least amount of information possible to represent a resource. That is to say that if you want to see a property for example; you'd only need the property ID, thus; `/properties/:propId`. If however you wanted to see all of the properties of a user, you would have to have the username, and the property ID, thus: `/user/:user/properties/:propId`.

Entities that are directly related, and only have context with that relationship are represented fully, with all of the information of that relationship intact. For example: the current user has tokens, and although tokens are entities of their own, they have no meaning outside of the scope of the current user, therefore: `/user/tokens/:tokenId`.

Entities that are directly related, but have context without that relationship being represented are viewed as an entity on their own. They will however have collections that list the entities with their relationship intact. For example, users have properties, but properties don't need the context of a user to be viewed, therefore: `/properties/:propId`, to view a given users' properties: `/users/:user/properties`. The collection returned from the latter would have links to the former.

---

### Authorisation

```
/auth                                               [POST]
```

### Current User (Private resources)

```
/user                                               [GET, PATCH, DELETE]
/user/applications                                  [GET, POST, DELETE]
/user/applications/:appId                           [GET, PATCH, DELETE]
/user/properties                                    [GET]
/user/tokens                                        [GET, DELETE]
/user/tokens/:tokenId                               [GET, PATCH, DELETE]
/user/tokens/application/:appId                     [GET, DELETE]
```

### Users (Public resources)

```
/users                                              [GET]
/users/:user                                        [GET]
/users/:user/properties                             [GET]
```

### Properties (Public, and Private when authenticated resources)

```
/properties                                         [GET, POST]
/properties/:propId                                 [GET, PATCH, DELETE]
/properties/:propId/images                          [GET, POST, DELETE]
/properties/:propId/images/:imageId                 [GET, PATCH, DELETE]
/properties/:propId/rooms                           [GET, POST]
/properties/:propId/rooms/:roomId                   [GET, PATCH, DELETE]
```