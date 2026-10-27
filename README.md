# dimension-keeper-backend

The serverless back end for dimension-keeper-mobile. AWS Lambda functions behind API Gateway read characters from the public Rick and Morty API and store custom characters in DynamoDB.

## Context

Built on 2 December 2024, together with the Flutter app (dimension-keeper-mobile).

## What it shows

- One Node.js Lambda handler per operation: list all, get by ID, list custom characters, and add, update and delete a custom character.
- DynamoDB access through the DocumentClient, with consistent status codes and JSON error bodies.
- A CloudFormation template for the IAM role, the Lambda function and the API Gateway resource and method, plus a manual deployment guide.
- Architecture screenshots of the deployed functions, roles and table.

## Stack

Node.js (Lambda), AWS API Gateway, DynamoDB, CloudFormation, axios, aws-sdk v2.

## Run it

Follow the README deployment guide: upload the functions to S3, then create the stack with `aws cloudformation create-stack`.

## Looking back (2026)

The template only covers part of the stack (one function and the POST method), and it targets an old Node runtime. Today I would define the whole stack in AWS SAM or CDK, use aws-sdk v3, and add handler tests.
