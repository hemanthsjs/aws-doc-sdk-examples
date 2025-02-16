# AWS SDK for Rust code examples for Amazon DynamoDB

## Purpose

These examples demonstrate how to perform several Amazon DynamoDB (DynamoDB) operations using the alpha version of the AWS SDK for Rust.
Most use the schema defined in the __create-table__ example.

DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability.

## Code examples

- [Add item to table](src/bin/add-item.rs) (PutItem)
- [Create a table](src/bin/create-table) (CreateTable)
- [Create, read, update, delete table](src/bin/CRUD) (CreateTable, DeleteItem, DeleteTable, PutItem, Query)
- [Delete table item](src/bin/delete-item.rs) (DeleteItem)
- [Delete a table](src/bin/delete-table.rs) (DeleteTable)
- [List tables and create a table](src/bin/dynamodb-helloworld.rs) (CreateTable, ListTables)
- [List the items in a table](src/bin/list-items.rs) (Scan)
- [Lists your tables](src/bin/list-tables.rs) (ListTables)
- [Create a table, adds some items from a file to the table, queries the table, and deletes the table](src/bin/movies.rs) (CreateTable, DeleteTable, ListTables, PutItem, Query)

## ⚠ Important

- We recommend that you grant this code least privilege, 
  or at most the minimum permissions required to perform the task.
  For more information, see
  [Grant Least Privilege](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#grant-least-privilege)
  in the AWS Identity and Access Management User Guide.
- This code has not been tested in all AWS Regions.
  Some AWS services are available only in specific
  [Regions](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services).
- Running this code might result in charges to your AWS account.

## Running the code examples

### Prerequisites

You must have an AWS account, and have configured your default credentials and AWS Region as described in [https://github.com/awslabs/aws-sdk-rust](https://github.com/awslabs/aws-sdk-rust).

## Running the code

### add-item

This example adds a new item to the specified table.

`cargo run --bin add-item -- -t TABLE -u USERNAME -p PERMISSION-TYPE -a AGE -f FIRST-NAME -l LAST-NAME [-d DEFAULT-REGION] [-v]`

- _TABLE_ is the name of the table to which the item is added.
- _USERNAME_ is the username of the user to add to the table. This is the key index to the table.
- _PERMISSION-TYPE_ is the type of user, either "standard_user" or "admin".
- _AGE_ is the age of the user.
- _FIRST-NAME_ is the first name of the user.
- _LAST-NAME_ is the last name of the user.
- _DEFAULT-REGION_ is name of the AWS Region, such as __us-east-1__, where the table is located.
  If not supplied, uses the value of the __AWS_DEFAULT_REGION__ or __AWS_REGION__ environment variable.
  If the environment variable is not set, defaults to __us-west-2__.
- __-v__ displays additional information.

### create-table

This example creates a table.
Use __delete-table__ to delete the table you've created.

`cargo run --bin create-table -- -t TABLE -k KEY [-d DEFAULT-REGION] [-v]`

- _TABLE_ is the name of the table to which the item is added.
- _KEY_ is the primary key for the table.
- _DEFAULT-REGION_ is name of the AWS Region, such as __us-east-1__, where the table is located.
  If not supplied, uses the value of the __AWS_DEFAULT_REGION__ or __AWS_REGION__ environment variable.
  If the environment variable is not set, defaults to __us-west-2__.
- __-v__ displays additional information.

### CRUD

This example creates a table, adds an item to the table, updates the item, deletes the item, and deletes the table.

`cargo run --bin crud -- [-i] [-d DEFAULT-REGION] [-v]`

- __-i__ enables interactive mode, which pauses the code between operations.
- _DEFAULT-REGION_ is name of the AWS Region, such as __us-east-1__, where the table is located.
  If not supplied, uses the value of the __AWS_DEFAULT_REGION__ or __AWS_REGION__ environment variable.
  If the environment variable is not set, defaults to __us-west-2__.
- __-v__ displays additional information.

### delete-item

This example deletes an item from a DynamoDB table.

`cargo run --bin delete-item -- -t TABLE -k KEY -v VALUE [-d DEFAULT-REGION] [-i]`

- _TABLE_ is the name of the table containing the item to delete.
- _KEY_ is the name of the primary key of the item to delete.
- _VALUE_ is the value of the primary key of the item to delete.
- _DEFAULT-REGION_ is name of the AWS Region, such as __us-east-1__, where the table is located.
  If not supplied, uses the value of the __AWS_DEFAULT_REGION__ or __AWS_REGION__ environment variable.
  If the environment variable is not set, defaults to __us-west-2__.
- __-i__ displays additional information.

### delete-table

This example deletes a DynamoDB table.

`cargo run --bin delete-table -- -t TABLE [-d DEFAULT-REGION] [-v]`

- _TABLE_ is the name of the table to delete.
- _DEFAULT-REGION_ is name of the AWS Region, such as __us-east-1__, where the table is located.
  If not supplied, uses the value of the __AWS_DEFAULT_REGION__ or __AWS_REGION__ environment variable.
  If the environment variable is not set, defaults to __us-west-2__.
- __-v__ displays additional information.

### dynamodb-helloworld

This example lists your DynamoDB tables and creates the table __test-table__.
Use __delete-table__ to delete __test-table__.

`cargo run --bin dynamodb-helloworld`

### list-items

This example lists the items in a DynamoDB table.

`cargo run --bin list-items -- [-d DEFAULT-REGION] [-v]`

- _DEFAULT-REGION_ is name of the AWS Region, such as __us-east-1__, where the tables are located.
  If not supplied, uses the value of the __AWS_DEFAULT_REGION__ or __AWS_REGION__ environment variable.
  If the environment variable is not set, defaults to __us-west-2__.
- __-v__ displays additional information.

### list-tables

This example lists your DynamoDB tables.

`cargo run --bin list-tables -- [-d DEFAULT-REGION] [-v]`

- _DEFAULT-REGION_ is name of the AWS Region, such as __us-east-1__, where the tables are located.
  If not supplied, uses the value of the __AWS_DEFAULT_REGION__ or __AWS_REGION__ environment variable.
  If the environment variable is not set, defaults to __us-west-2__.
- __-v__ displays additional information.

### movies

This example creates the DynamoDB table _dynamo-movies-example__ in __us-east-1__, waits for the table to be ready, adds a couple of rows to the table, and queries for those rows.
Use __delete-table__ to delete __dynamo-movies-example__.

`cargo run --bin movies`

## Resources

- [AWS SDK for Rust repo](https://github.com/awslabs/aws-sdk-rust)
- [AWS SDK for Rust API Reference Guide](https://awslabs.github.io/aws-sdk-rust/aws_sdk_config/index.html) 

## Contributing

To propose a new code example to the AWS documentation team, 
see [CONTRIBUTING.md](https://github.com/awsdocs/aws-doc-sdk-examples/blob/master/CONTRIBUTING.md). 
The team prefers to create code examples that show broad scenarios rather than individual API calls.

Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved. SPDX-License-Identifier: Apache-2.0
