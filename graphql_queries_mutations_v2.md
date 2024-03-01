
# GraphQL Queries and Mutations

## Queries

### Login

Log in a user with their email and password.

```graphql
query Login {
  login(user: {email: "user@example.com", password: "userPassword"}) {
    user {
      _id
      email
      permissions
      lowercaseEmail
      timestamp
    }
    token
  }
}
```

### Refresh Token

Refresh an authentication token.

```graphql
query RefreshToken {
  refreshToken
}
```

### Get All Orders

Fetch all orders including the name of the order and the owner's details.

```graphql
query GetAllOrders {
  getAllOrders {
    name
    owner {
      _id
      email
    }
  }
}
```

## Mutations

### Create User

Create a new user with an email and password.

```graphql
mutation CreateUser {
  createUser(createUserInput: {email: "newuser@example.com", password: "newUserPassword"}) {
    user {
      _id
      email
      permissions
    }
    token
  }
}
```

### Create Order

Create a new order by specifying a name.

```graphql
mutation CreateOrder {
  createOrder(createOrder: {name: "New Order Name"}) {
    _id
    name
    owner
  }
}
```
