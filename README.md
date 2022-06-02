# MongoDB queries 🔎

This repository is for my students at Ironhack, so that they can practise different MongoDB queries.

## Instructions

- Once you have forked and cloned the repository, write the following command on the terminal. 

⚠️ Note: for this command to work, your terminal should be on the repository project folder:

```bash
$ mongoimport --db people --collection users --file users.json
```

- This will create a database called "people" and a collection named "users". Once the process is finished, you should see a message telling you that 12 new documents were imported successfully.

- Open Mongo Compass and connect to the localhost database (mongodb://localhost:27017). Check the databases and make sure you see the "people" database.

- Now, open mongo shell on Mongo Compass or in the terminal and write the queries necessary to do the following actions. After each query, write your solution on the <code>answers.md</code> file for each iteration.

- Remember that, to operate on a specific collection of a specific database, you first have to "navigate" to it:

```bash
$ show dbs
$ use people
```


## Iteration 1

Write a query that finds all the users in the collection but returns only their names.

db.users.find({},{_id:0,name:1})

## Iteration 2

Write a query that finds all the users that currently have insurance.

db.users.find({hasInsurance:true},{_id:0,name:1,hasInsurance:1})

## Iteration 3

Write a query that return all users that are 18 years old or older.

db.users.find({age:{$gt:17}},{_id:0,name:1,age:1})

## Iteration 4

Write a query that returns the first user living in Italy. Return only their name and email.

b.users.findOne({country: "Italy"},{_id:0,name:1,country:1})

## Iteration 5

Write a query that returns users living in the USA. Limit the data to 5 users. Return only their names.

db.users.find({country: "USA"},{_id:0,name:1}).limit(5)

## Iteration 6

Write a query that returns those users of whom we have the phone number.

db.users.find({phone:{$exists:false}},{_id:0,name:1})

## Iteration 7

Write a query that updates the information of Marissa Geller: her new mail account is "marissa@hotmail.com".

db.users.updateOne({email:"mary@doe.com"},{$set:{email:"marissa@hotmail.com"}}

## Iteration 8

Write a query that updates the information of everyone living in the UK. Add to their documents a new field called currency and pass 'pounds' as a value.

db.users.updateMany({country:"UK"},{$set:{ "currency":"pounds"}})

## Iteration 9

Write a query that returns all the users living in the UK. Return only their names and currency.

db.users.find({country:"UK"},{_id:0,name:1,currency:1})

## Iteration 10

Write a query that deletes all users that are older that are 45 or older.

db.users.remove({age:{$gt:45}})