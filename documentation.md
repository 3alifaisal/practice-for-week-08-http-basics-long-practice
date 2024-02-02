============================================
============================================
## EXAMPLE DOCUMENTATION
### Ask for the Home Page
#### Step 1
Predicted Request components:
- Method: GET
- URL: /
- Headers: none
- Body: none

Predicted Response components:
- Status Code: 200
- Headers:
  - Content-Type: text/html
- Body: HTML page with navigation links to other pages

#### Step 2
In your browser open the chrome dev tools, navigate to [http://localhost:5000] and make a GET request for the Home Page (type "/" into the URL after 5000 and hit "enter").
Explore the "network" tab and find where you can compare your predicted request/response components to the actual components.

#### Step 3
If your prediction was wrong, try to understand why it was incorrect and then update your documentation to the correct request/response components.

Congratulations! You have performed a GET request to / showing the home page of our e-commerce
website. Move on to the next request/response documentation.

* Note
    - Headers contain many keys, but for this exercise focus on **Content-Type** and **Location**.
 
=============================================
=============================================

### Ask for a page that doesn't exist

Request components:
- Method: GET
- URL: http://localhost:5000/homework
- Headers: none
- Body: none

Response components:
- Status code: 404 Page Not Found
- Headers: 
          text/html; charset=utf-8


- Body: none

### Ask for the products list page

Request components:
- Method: GET
- URL: http://localhost:5000/products
- Headers: None
- Body: None

Response components:
- Status code: 200 Ok
- Headers: 
text/html; charset=utf-8


- Body:  products list 

### Ask for the product detail page

Here's an example product on the server:

| detail      | value                                                      |
| ----------- | ---------------------------------------------------------- |
| productId   | 1                                                          |
| name        | "Facial Cleansing Brush"                                   |
| description | "Reaches deep pores to cleanse oil, dirt, and blackheads." |
| price       | 23.99                                                      |
| categories  | "beauty", "electronics"                                    |

Request components:
- Method: GET
- URL:  http://localhost:5000/products/1
- Headers: none 
- Body: none

Response components:
- Status code: 200 ok 
- Headers: text/html; charset=utf-8
- Body: product 1 details and options 

### Ask for the create new product page

Request components:
- Method: GET
- URL: http://localhost:5000/products/new
- Headers: none
- Body:  none

Response components:
- Status code: 200 ok
- Headers: text/html
- Body: create new product body

### Submit a new product

Remember, for a traditional HTML web server, whenever a successful `POST`
request is sent to the server, the server should respond with a redirection to
a page.

After successful submission, user should be looking at the product detail page.

Here are the categories on the server:

| tag         | name           |
| ----------- | -------------- |
| grocery     | Grocery        |
| electronics | Electronics    |
| beauty      | Beauty         |
| toys-games  | Toys and Games |
| health      | Health         |
| furniture   | Furniture      |
| clothing    | Clothing       |

* Note: In Chome dev tools, if the "body" of a request exists, it will appear 
in the network tab as "payload".

Request components:
- Method: Post 
- URL:  http://localhost:5000/products
- Headers: 
application/x-www-form-urlencoded
- Body: name=blackjangaa&description=hookah&price=32&categories=grocery

Response components:
- Status code: 302 Found
- Headers: 
location 
http://localhost:5000/products/3
text/html; charset=utf-8


- Body: HTML page with navigation links to other pages
AND product's 2 detailed table
AND product options

### submit for the edit product page

Request components:
- Method: POST 
- URL:  http://localhost:5000/products/3
- Headers:  application/x-www-form-urlencoded
- Body: name=blackjangaa&description=hookah+shop+&price=32&categories=grocery

Response components:
- Status code: 302 found 
- Headers: lcoation 3 nd text html 
- Body: HTML page with navigation links to other pages
AND product's 2 detailed table
AND product options

### ask an edit for an existing product

After successful submission, user should be looking at the product detail page.

Request components:
- Method: GET
- URL: http://localhost:5000/products/3/edit
- Headers: NONE
- Body: none

Response components:
none on 1st request
on server request 
- HTML page with navigation links to other pages
AND product's 2 detailed table
AND product options

### Submit a delete for an existing product

After successful submission, user should be looking at the products list page.

Request components:
- Method: POST 
- URL: 
http://localhost:5000/products/3/delete
- Headers: application/x-www-form-urlencoded
- Body:  NONE

Response components:
- Status code: 302 FOUND
- Headers: TEXT HTML products/3 
- Body: products page 

### Submit a new review for a product

After successful submission, user should be looking at the product detail page.

Here's an example review on the server:

| detail     | value                  |
| ---------- | ---------------------- |
| reviewId   | 1                      |
| comment    | "I love this product!" |
| starRating | 5                      |
| productId  | 1                      |

Request components:
- Method: Post
- URL: http://localhost:5000/products/2/reviews
- Headers: application/x-www-form-urlencoded
- Body: application/x-www-form-urlencoded

Response components:
- Status code: 302 found
- Headers:location 
http://localhost:5000/products/2 
    text/html 
- Body: what we see review underneeth the normal product description also same as product 2 

### Ask for the edit review page for a product

Request components:
- Method: GET
- URL: http://localhost:5000/reviews/2/edit
- Headers: none
- Body: none

Response components:
- Status code: 200 ok
- Headers: text/httml
- Body: edit review page

### Submit an edit for an existing review

After successful submission, user should be looking at the product detail page.

Request components:
- Method: pOST
- URL: 
http://localhost:5000/reviews/2
- Headers: 
application/x-www-form-urlencoded
- Body: comment=blaj+blah+f&starRating=2

Response components:
- Status code: 302 FOUND
- Headers: 
text/html;  
LCOATION /products/2 
- Body: product 2 homepage

### Submit a delete for an existing review

After successful submission, user should be looking at the product detail page.

Request components:
- Method: POST
- URL: 
http://localhost:5000/reviews/3/delete

- Headers: application/x-www-form-urlencoded
- Body: NONE

Response components:
- Status code: 302 FOUND
- Headers: TEXT/HTML 
- Body: REDIRECTED TO 
http://localhost:5000/products/2

### Ask for all the products in a particular category by tag of the category

Request components:
- Method: GET
- URL: http://localhost:5000/categories/beauty/products
- Headers: none
- Body: none

Response components:
- Status code: 200 ok
- Headers: 
text/html; charset=utf-8


- Body: beauty products list followed bu the products in that category 

### Ask for the best-selling product

Look for clues in the HTML pages from the prior responses for what the route should be.

Request components:
- Method:   GET
- URL: http://localhost:5000/products/best-selling
- Headers: none
- Body: none

Response components:
- Status code: 200 OK 
- Headers:text/html 
- Body: best selling product followed by product name adn tge nromal product flow 