
In working with the dashbord system,

  

There is always a question: What is the best way to do pagination?

  

**Pagination ?**

Suppose we have 1000 rows of data, so it will take a lot of bandwidth to fetch data all the at one time, and it will cause a latency(delay). To overcome this, we use pagination.

We set the number of rows per page to 10, 20, 30, and so on. based on the requirements.

  

In my recent project , I had the same issue.

What I did was use the concepts of skip and limit to achieve my goal.

 ![attachment](https://imgur.com/YQV3iSl.png)

As you can see in the image attached:

we have,

  

id: As the system is dynamic, id will help to fetch specific user data. id is attached to req by a custom middleware fetchuser, which will check if the JWT token is valid, and if it is valid, it will get the id from the token and pass the require.

  

ITEMS-PER-PAGE: It is a numeric value that is set to 10. This means we are requesting 10 rows or documents per request.

  

page: This represents the current page. If not, it will be set to 1. I have used parameters to check what page we are on.

  

skip: Based on the page number and ITEMS-PER-PAGE, it will skip x rows or documents. Supposing we are on page 2 and ITEMS-PER-PAGE is set to 10, skip will be 20 and will skip 20 records, and the endpoint will return data from the 21st record.



countPromise: This is to get the total document or row count. This will be helpful to get the maximum number of pages we have. Suppose there are 50 documents in the table, and ITEMS-PER-PAGE is 10, so we will have 5 pages.

  

usersPromise: This is the list of users that the endpoint will send.

pageCount: The count of pages.

Code is very simple once you read it and do.  
  
If any error, comments are alwyas welcome. I'm trying out this things.

---

If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
