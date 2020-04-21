### What's it?
A simple example of Laravel GraphQL using https://github.com/rebing/graphql-laravel

---
### How to use

- Clone the repository with __git clone__
- Copy __.env.example__ file to __.env__ and edit database credentials there
- Run __composer install__
- Run __php artisan migrate --seed__
- If you have permission error run these commands https://gist.github.com/Daniyal-Javani/e7a6c70e2bae46945706cd345913c03d

---
### Now check these out

#### View the documentation of your API
`/graphql?query={__schema{types{name,fields{name,description}}}}`

or
```
{
  __schema {
    types {
      name
      fields {
         name
         description
      }
    }
  }
}
```

#### Get all of the users
`/graphql?query=query+FetchUsers{users{id,email}}`

or
```
query FetchUsers {
    users {
        id
        email
    }
}
```

#### Get a specific user
`/graphql?query=query+FetchUsers{users(id:"18"){id,email}}`

or
```
query FetchUsers {
    users (id: "18"){
        id
        email
    }
}
```

#### update the password of a user
`/graphql?query=mutation+users{updateUserPassword(id:%221%22,password:%22newpassword%22){id,email}}`

or
```
mutation users {
    updateUserPassword(id: "1", password: "newpassword") {
        id
        email
    }
}
```

#### update the email of a user with validation
`/graphql?query=mutation+users{updateUserEmail(id:%221%22,email:%22newemail%22){id,email}}`

or
```
mutation users {
    updateUserEmail(id: "1", email: "newemail@example.com") {
        id
        email
    }
}
```
---

### License

Please use and re-use however you want.
