# Products

Direct interactions with the API requires the user to be linked to a valid company registered with RapiD Engineering.



## Parameters for all endpoints
Note that this is also the order the endpoints expects the parameters in

| Name           | Explanation                                 | Required    |
| -------------- | ------------------------------------------- | ----------- |
| Id             | Guid of item you want                       | required    |
| productsToTake | Amount of products you want                 | default 100 |
| filterIds      | A list of filter the products have to match | nullable    |
| defects        | A list of defects the products can have     | nullable    |
| labels         | A list of a labels the products can have    | nullable    |


We can fetch products from the RapiDVision API come in four ways:

??? example "Correct url"
    ```
    "api/Product/Batch?Id=550e8400-e29b-41d4-a716-446655440000&productsToTake=10&filterIds=f47ac10b-58cc-4372-a567-0e02b2c3d479&filterIds=a1b2c3d4-e5f6-47a8-b9c0-d1e2f3a4b5c6&defects=scratch&defects=dent&labels=premium&labels=export"
    ```

## [HttpGet("Invoice")]

Returns Ok(200) and a select amount of ProductDTOs from a specific invoice

!!! example "The GET("Invoice") endpoint:"
    ``` c#
    $"{api_url}/api/Product/Invoice?Id={}&productsToTake{}&filterIds={}&defects={}?=&labels={}"
    ```

## [HttpGet("InvoiceRule")]

Returns Ok(200) and a select amount of ProductDTOs from a specific invoice rule

!!! example "The GET("InvoiceRule") endpoint:"
    ``` c#
    $"{api_url}/api/Product/InvoiceRule?Id={}&productsToTake{}&filterIds={}&defects={}&labels={}"
    ```

## [HttpGet("Batch")]

Returns Ok(200) and a select amount of ProductDTOs from a specific batch

!!! example "The GET("Batch") endpoint:"
    ``` c#
    $"{api_url}/api/Product/Batch?Id={}&productsToTake{}&filterIds={}&defects={}&labels={}"
    Multiple filters:
    ```

## [HttpGet("All")]

Returns Ok(200) and all ProductDTOs from a specific date range

!!! example "The GET("All") endpoint:"
    ``` c#
    $"{api_url}/api/Product/All?startDate={}&endDate{}&filterIds={}&defects={}&labels={}"
    ```

## Possible responses

Below are some of the common response codes and what they mean:

| StatusCode     | Explanation                                     | 
| -------------- | ----------------------------------------------- | 
| 500            | Exception occurred while retrieving data        | 
| 405            | Method not allowed. Check if the request is GET | 
| 404            | Notfound. Id does not exist                     | 
| 401            | User not autherized to acces endpoint           | 
| 400            | Request failed. Check response message          |
| 200            | Succesfully retrieved products                  | 

