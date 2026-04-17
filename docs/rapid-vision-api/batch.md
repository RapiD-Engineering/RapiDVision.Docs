# Batch

Direct interactions with the API requires the user to be linked to a valid company registered with RapiD Engineering.

Batches fetched from the RapiDVision API come in two forms:

??? example "Accepted DateTime format"
    ```
    2026-04-10T13:19:47Z
    "yyyy-MM-ddTHH:mm:ssZ"
    ```

## [HttpGet]

With a succesful call to this endpoint, you'll receive a 200 (Ok) response with a list of BatchDTOs. These batches won't include their child items (Products).

- This request needs to have valid DateTimes.
- An optional parameter for this query is a search string which is null by default.

!!! example "The GET endpoint:"
    ``` c#
    $"{api_url}/api/Batch?startDate={datetime}&endDate={datetime}"
    ```



## [HttpGet("{id:guid}")]

With a succesful call to this endpoint, you'll receive a 200 (Ok) response with an BatchDTO.

!!! example "The GET{id} endpoint:"
    ``` c#
    $"{api_url}/api/Batch/{Batch Guid}"
    ```
