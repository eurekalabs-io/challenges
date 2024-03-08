# Diapers Catalog

Let's help this company to build a nice looking baby diapers catalog where a bunch of diapers will be presented to users and they will have the chance to interact with this page by selecting the diaper presentation, see the price and availability.

## Features

- List products showing image, title, presentations, price and stock availability. Required.
- Display amount of results retrieved. Required.
- Allow users to click on each presentation and according to the selection, show price and stock availability. Required.
- Show an average price (this price is an avarge taken from the different product variants). Optional.

## Backend

In order to retrieve products information, there is a need to build a backend service. This service will provide the required information that will be used by the frontend piece.

It is important to consider that this service will have to interact with an external API where the main information about diapers comes from:

`https://kabsa.yallababy.com/api/v1/products/best-selling-products-by-subcategory`

Make sure to add the following header to the API request:

`secretKey: 1DIPIkKeq8`

### Data Structure

You will retrieve a JSON object with 9 elements, where each of those will contain a good amount of information, although you should be able to extract only the row with 'product_type' = 'diapers' as we want to display information only about diapers. 

If you see the wireframe, you will notice that diapers are grouped by variant name (option1), then you will have to show the different presentations for each diaper variant (option2), for instance: variant 'NB', presentations are 34, 68, 136. The title to show will be Vendor + '-' + Variant Name, like this: PureBorn - NB, then PureBorn - 2, and so on.

Consider the following data coming from external API:

`
{
    "vendor": "",
    "variants": [{.., "option1": "NB", "option2": "34", "price": "43.20", image_id}, {.., "option1": "NB", "option2": "68", "price": "82.09", image_id} ..],
    "images: [{id, src, ..}, {id, src, ..}],
    "presentationsBySizeInStock": [{}]
}
`

The "images" array contains information about the associated images that corresponds to each variant.

The "presentationsBySizeInStock" array contains those variants presentations that are currently in stock, everything else is out of stock.

## Webpage Design

Design will be up to you, although there is a wireframe as reference that you can follow. Feel free to use resources / assets of your preference for this purpose.

### Main Wireframe

![Main Wireframe](https://github.com/eurekalabs-io/challenges/blob/main/fullstack/mums-deals/wireframes/diapers-catalog.png)

## Tech Stack / Considerations

- Implement the frontend using Reactjs. Feel free to include the libraries of your preference.
- Implement the backend using NodeJS. 
- Publish source code into code repository (github, bitbucket, etc).
- Deploy challenge using AWS, Heroku, etc. Optional - Big Plus.
