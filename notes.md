- `npm init -y`
- `npm i express express-graphql graphql`
- `npm i --save-dev nodemon`

```js
"scripts": {
    "devStart": "nodemon server.js"
  }
```
- Add `server.js`
- `npm run devStart`

- Update `server.js`
- Go to `http://localhost:5000/graphql`
- Query for books
```js
query {
    books {
        name
    }
}
```
**OR**
```js
{
    books {
        // Include any keys you want displayed
        name
    }
}
```
```js
{
  books {
    name,
    author {
      name
    }
  }
}
```
- Query for a single book
```js
{
  book(id: 3) {
    name
  }
}
```
```js
{
  book(id: 3) {
    name,
    author {
      name
    }
  }
}
```
- Use mutations for `put post delete`
- To add a book
```js
mutation {
    // Need to use ""
    addBook(name: "New Name", authorId: 1) {
        id
        name
    }
}
```