# Invoice

Most data fetching happens automatically through the provided applications. Direct interactions with the API requires the user to be linked to a valid company registered with RapiD Engineering.

Invoices fetched from the RapiDVision API come in two forms:

??? example "Accepted DateTime format"
    ```
    2026-04-10T13:19:47Z
    "yyyy-MM-ddTHH:mm:ssZ"
    ```

## [HttpGet]

With a succesful call to this endpoint, you'll receive a 200 (Ok) response with a list of invoiceDTOs. These invoices will include their child items (InvoiceRules, Batches).

- This request needs to have valid DateTimes.
- An optional parameter for this query is a search string which is null by default.

!!! example "The GET endpoint:"
    ``` c#
    $"{api_url}/api/Invoice?startDate={datetime}&endDate={datetime}"
    ```



## [HttpGet("{id:guid}")]

With a succesful call to this endpoint, you'll receive a 200 (Ok) response with an invoiceDTO.
!!! example "The GET{id} endpoint:"
    ``` c#
    $"{api_url}/api/Invoice/{invoice Guid}"
    ```



!!! Note
    Products are handled separately and won't be included in any of the invoices.
