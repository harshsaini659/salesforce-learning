## What is Apex and when to use Apex ?
Apex is server-side programming and strongly typed object oriented programming language which is developed by Salesforce.com.
Apex allow us to write the code that executes on the force.com platform. Apex is saved,compiled and executed on the servers of Force.com platform.
- It is use to build SaaS applications on top of salesforce CRM functionality and for writing business logic.
- Apex is used to perform a couple of business processes which are not supported by workflow, means if we write down the complex business processes which is not possible to be created with the help of point and click tools then this situation
we have to write down Apex.
- To perform complex validation over multiple objects we use Apex.
- To create webservices and email services we use Apex.
for transactions and rollbacks we use Apex.

In other Words:
- Triggers likhne ke liye
- Complex validation ke liye
- Database operations (insert/update/delete) ke liye.
  
Example:
- Record save hone se pehle validation
- Email bhejna
- Related records update karna

## What is mean by Apex is strongly typed ?
It means ki variable ka Datatype phle define karna padta hai.
`
Integer a = 10;   // correct
a = 'test';      // error
`
