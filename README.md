# :collision: BAMazon :computer: :package:

### Overview
A Node.js &amp; MySQL digital storefront. This is a command line Node app that mimics a beloved online retailer.


### Node.js
Three JavaScript files replicate the basics of a simple ecommerce engine:

- `BamazonCustomer.js` _([See example here](#customer))_
  - Receives orders from customers via the command line and interfaces with mySQL to deplete stock from the store's inventory.

- `BamazonManager.js` _([See example here](#manager))_
  - Mimics the basics of a warehouse management system, providing managers with a list of options to view stock and adjust inventory.
  - A sample of the menu is below:
    * View Products for Sale 
    * View Low Inventory
    * Add to Inventory
    * Add New Product

- `BamazonExecutive.js` _([See example here](#executive))_
  - Simulates very basic profit and sales insights for upper management.
  - A sample of the menu is below:
    * View Product Sales by Department 
    * Create New Department


### MySQL
The JavaScript files mentioned above query a MySQL database called `Bamazon` which is locally hosted on my laptop.

- Please refer to the `schema.sql` file to see how the database was created using raw SQL queries.

  - If you wish to run this app on your own machine, then please note the following commands:

    1. If you are new to MySQL, please set up [MySQL](http://dev.mysql.com/downloads/mysql/) and [MySQL Workbench](http://dev.mysql.com/downloads/workbench/) on your laptop and then open up to your localhost connection.
    2. Run `CREATE DATABASE Bamazon;` in mySQL Workbench.
    3. Be sure to select the correct database by running the `USE Bamazon;` 
    4. Refer to the raw SQL commands under the _`=== First Table ===`_ comment to set up the `Products` table.
    5. Refer to the raw SQL commands under the _`=== Second Table ===`_ comment to set up the `Departments` table.


### Node Package Manager (npm)
If you clone this repo down to your machine, note that it has two npm dependencies!
Before running the JavaScript files mentioned above, please run `npm install` in your terminal to download the [prompt](https://www.npmjs.com/package/prompt) and [mysql](https://www.npmjs.com/package/mysql) node packages.


### Screenshots
Below are some screenshots that show the functionality of the app.


<a name="customer"></a>
- Below is a demo of the `BamazonCustomer.js` file...
  - Running `node BamazonCustomer.js` will use MySQL to pull up all the products for sale.
    - The customer can then choose a product using its ID and then enter a quantity to buy.
      ![Customer Order](/example_images/BamazonCustomer-1.png)
    - If the inventory has enough items, the order will be processed.
      ![Order Valid](/example_images/BamazonCustomer-2a.png)
    - If the inventory is lacking, the order will not be processed.
      ![Order Invalid](/example_images/BamazonCustomer-2b.png)
