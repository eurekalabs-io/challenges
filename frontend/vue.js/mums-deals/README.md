# Mums Deals

Let's help this company to build a nice looking page where products for babies will be presented and users will have the chance to interact with this page by filtering, sorting and changing the way the information is displayed.

## Features

- List products showing Image, Title and Product Type. Required.
- Display amount of results retrieved. Required.
- Select products view between grid and list for the main display area. Required.
- Filter products by Product Type. Required.
- Filter products by Price Range. Optional.
- Sort results: A-Z, Price: High to Low, Price: Low to High. Optional.

## Products Data

In order to retrieve products information, use the following API endpoint:

`https://kabsa.yallababy.com/api/v1/products/best-selling-products-by-subcategory`

Make sure to add the following header to the API request:

`secretKey: 1DIPIkKeq8`

## Data Structure

You will retrieve a JSON object with 9 elements, where each of those will contain a good amount of information, although you should focus only in the following data:

`
{
    "title": "",
    "product_type": "",
    "image": "",
    "quantitySold": 100,
    "variants": [{.., "price": "10.50"}, {.., "price": "20.70"} ..]
}
`

For the element "variants", the information we want to extract is the price, so given that a single product can have multiple variants or versions, this will cause a product to have multiple prices so take this in account when it comes to filter by price.

## Webpage Design

Design will be up to you, although there is a wireframe as reference that you can follow. Feel free to use resources / assets of your preference for this purpose.

### Grid View Wireframe

![Grid View Wireframe](https://github.com/eurekalabs-io/challenges/blob/main/frontend/vue.js/mums-deals/wireframes/mums-deals-grid-view.png)

### List View Wireframe
![List View Wireframe](https://github.com/eurekalabs-io/challenges/blob/main/frontend/vue.js/mums-deals/wireframes/mumsdeals-list-view.png)

## Tech Stack / Considerations

- Implement the challenge using Vue.js. Feel free to include the libraries of your preference.
- Publish source code into code repository (github, bitbucket, etc).
- Deploy page using AWS, Heroku, etc. Optional - Big Plus.
-
