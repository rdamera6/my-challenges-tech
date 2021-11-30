# Problem statement

  

  

We will  write code that will query the **meta data** of an instance within **AWS/Azure/GCP** and provide a JSON-formatted output.

  

  

Refer to the documentation of the respective public cloud providers.

  

  

## First things first - Why Python?

  

  

>The IMDS service of AWS, Azure and GCP are simple rest API's and can be implemented in wide range of programming languages. I have chosen Python to showcase my proficiency in Python

  

  

# Approach

  

  

We are going to choose AWS here as it is widely used by many enterprises for **IAAS**. There are two API's IMDSv1 and IMDSv2, I am going to use IMDSv1 for this challenge IMDSv2 there is a new requirement to pass a 
>**X-aws-ec2-metadata-token** and **X-aws-ec2-metadata-token-ttl-seconds**

  The AWS IMDSv1 has an API


The first call will return the top level Keys and we need to iterate the list of keys with the same API with the key amended at the end. Some of the keys may return another array of keys.


Finally we need to keep track all the keys and the values and build the JSON Object.

To obtain a value for a single key we still might need to retrieve  the entire meta-data and traverse through the JSON tree to find the value for the given key.


Would give the JSON output of metadata



  

# Assumptions

  

  

- The machine that is running this service is configured with right access keys and permissions in IAM.

  

  

# Testing

  

  

I am going to use Mocha javascript testing framework to do the unit testing

  

  

# Bonus Points

  

The code allows for a particular data key to be retrieved individually

  

  

# Prerequisites

  

  

Create an EC2 Linux instance on AWS

  

SSH into the instance

  

  

# Installation

  

  

Install Python 3 and git on your instance

  

>sudo yum install python3 git

  

Clone our repository

  


  
  

Install pipenv

  

>sudo pip3 install pipenv

  

Go to directory **challenge2**

  

>cd challenge2

  

Install project dependancies

  

>pipenv install

  

  

# Running

  

  

Open the src folder

  

>cd challenges/challenge2/src

  

Run whichever script you need:

  

>python3 metadata.py

  

>python3 querymetadata.py

  

  

Examples for the key ami-id or vpc-id
