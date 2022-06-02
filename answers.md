# Solutions sheet

Submit your final query after each iteration:

## Iteration 1

db.users.find({},_id:0, name:1)

## Iteration 2

db.users.find({hasInsurance:true},{_id:0,name:1,hasInsurance:1})

## Iteration 3

db.users.find({age:{$gt:17}},{_id:0,name:1,age:1})

## Iteration 4

b.users.findOne({country: "Italy"},{_id:0,name:1,country:1})

## Iteration 5

db.users.find({country: "USA"},{_id:0,name:1}).limit(5)

## Iteration 6

db.users.find({phone:{$exists:false}},{_id:0,name:1})

## Iteration 7

db.users.updateOne({email:"mary@doe.com"},{$set:{email:"marissa@hotmail.com"}}

## Iteration 8

db.users.updateMany({country:"UK"},{$set:{ "currency":"pounds"}})

## Iteration 9

db.users.find({country:"UK"},{_id:0,name:1,currency:1})

## Iteration 10

db.users.remove({age:{$gt:45}})