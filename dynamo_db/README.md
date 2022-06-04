## Dynamo DB


### lab 1.1 - create a DynamoDB database

## ```Step One```: Search For the dynamoDB service

![dynamo-db]()

## ```Step Two```: click on create Database


This would redirect to the create table console

## ```Step Three```: Table details

By default in DynamoDB the database is managed by AWS, and the first thing we do is just to create a table in the databe

- Table name: This is the name of the table you want to store your data, for example in a ecommerce site, you might have a table for users, another table for products, another for orders e.t.c

- Partition key: A partition key is what we use to access our data, for example say in our ecommerce site, we got a first order, this order can have an id of 1, and thus anytime we want to access the order in this table we can always reference 1, same with a second order.


    | Partition key      | order       |
    | -----------        | ----------- |
    | 1                  | A Roja Dove musk Perfume              |
    | 2   | Play station 5       |

- Sort Key: A sort key is kinda like a partition key, but is usually used with a partition key, now say for example in our list of products in our ecommerce site, we want to fetch or group the products that come in by weeks, this would be a good example to use a sort key and a partition key,

    In the case we can have a partition key that is not unique, but the sort key will be unique, breaking this futher with the products example above, each product that comes in on 1-01-2022 to 7-01-2022, would have a partition key of 1, and each day of the week would be the sort key

    | Partition key      | Sort key    | Products          | 
    | -----------        | ----------- | -----------       |
    | 1                  | 1-01-2022            |30 machintosh computers      |
    | 1                  | 2-01-2022            |200 pens                   |
    | 2                  |  3-01-2022           |500 pencils                   |
    | 2                  |   04-01-2022          | 40 T-shirts                   |


```But how is this important?```

Firstly we have our data grouped by dates, so if we want to say fetch all the orders in week one, we query by the partion key of 1 and we get ```30 machintosh``` and ```200 pens```

Guess what we get by querying with the id of 2?

Answer: we get ```500 pencils``` and ```40 T-shirts```

## ```Step Four```: Settings

Here we choose customized settings, this is so we can dig in and really customize our Database.

## ```Step Five```: Table class

Here we have two modes of how we want our data to be accessed, the two modes are 

- DynamoDB Standard: This is for databases that are frequently accesed with reads and writes.

- DynamoDB Standard-IA: These are for tables, that wont be frequently accessed.

## ```Step Six```: Capacity calculator

The capacity calculator, defines how quick we want our reads and writes to our DynamoDB to be.

the higer the capacity the quicker our reads and writes would be...

But AWS chargers for higher capacity for our writes and reads.

So we will stick with the defaults, but feel free to increase this for higher work loads or in a production environment.

## ```Step Seven```: Read/write capacity settings

#### Capacity mode: 

here we have two options to either choose from on-demand capacity or, from a provision capacity 

- On-demand: This deals with the amount of reads being charged directly 
- provision capacity: in simplest terms, charges you for the load of traffic you use.

Thus enabling us to scale reads or writes, when we reach a certain break point.

these breakpoints can be turned off or on in the read capacity and write capacity options


## ```Step eight```: Secondary indexes

A secondary index is a data structure that contains a subset of attributes from a table, along with an alternate key to support Query operations. You can retrieve data from the index using a Query, in much the same way as you use Query with a table. A table can have multiple secondary indexes, which give your applications access to many different query patterns.



## ```Step eight```: Encryption at rest

This data helps us to encrypt our data in AWS, we can just check the default for now.


## ```Step eight```: Tags

Finally we can tag, our database

Name: my_dynamo_db

finally click on create.








