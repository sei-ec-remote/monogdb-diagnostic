# MongoDB Diagnostic

This file is a **markdown** file. Markdown is a special way of formatting text, and one that's used by GitHub in its README files.

Goal: Read each question and write code to complete each task. Each question is going to assume we have a collection called `houses` in our database. 

Test: There are no tests for this diagnostic. You can test your code in your `mongosh` repl making sure to create a collection called `houses` to make your changes in.

### Question 1

Using [`.insertOne()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.insertOne/), create 3 documents, using the data below, inside the collection `houses`. Each document should have 2 field, `name` and `moto`.

- House Arryn, motto 'As High as Honor'
- House Stark, motto 'Winter is Coming'
- House Targaryen, motto 'Fire and Blood'

```js
// answer here
db.houses.insertOne({
    name: "Arryn"
    motto: "As High as Honor"
})
db.houses.insertOne({
    name: "Stark"
    motto: "Winter is Coming"
})
db.houses.insertOne({
    name: "Targaryen"
    motto: "Fire and Blood"
})
```

### Question 2

Using [`.updateOne()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateOne/) and the 3 documents we just created in question 1, add a new field called `members` and `$push` each memeber below to their correct house.

- Ned Stark
- Arya Stark
- Sansa Stark
- Viserys Targaryen
- Daenerys Targaryen
- Jon Arryn

```js
// answer here
db.houses.updateOne({name: "Arryn"},{$push{members: "Jon Arryn"}})
db.houses.updateOne({name: "Stark"},{$push{members: "Ned Stark", "Arya Stark", "Sansa Stark"}})
db.houses.updateOne({name: "Targaryen"},{$push{members: "Viserys Targaryen", "Daenerys Targaryen"}})
```

### Question 3

House Arryn is not honorable! Using [`.updateOne()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateOne/) and `$unset`, remove their house motto.

```js
// answer here
db.houses.updateOne({name: "Arryn"},{$unset{motto:""}})
```

### Question 4

Remove house Stark! Using [`.deleteOne()](https://www.mongodb.com/docs/manual/reference/method/db.collection.deleteOne/), remove house Stark.

```js
// answer here
db.houses.deleteOne({name: "Stark"})
```