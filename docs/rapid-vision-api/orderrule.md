# OrderRule

Direct interactions with the API require a valid Bearer token or an `X-Api-Key` header, and your account or key must be linked to a valid company registered with RapiD Engineering.

??? example "Accepted DateTime format"
    ```
    2026-04-10T13:19:47Z
    "yyyy-MM-ddTHH:mm:ssZ"
    ```

## GET /api/OrderRule

Returns a 200 (OK) response with a list of order rules in the given date range. Each order rule includes its nested Batches.

- Requires valid `startDate` and `endDate` values.
- An optional `search` parameter searches by order rule ID, order ID, description, or parent order/purchase order name — when provided, the date range is ignored.

!!! example "Request"
    ``` c#
    $"{api_url}/api/OrderRule?startDate={datetime}&endDate={datetime}"
    ```

**Response fields:** `Id`, `OrderId`, `CreatedOn`, `LastDateTime`, `Description`, `ParentOrderName`, `ParentPurchaseOrderName`, `ClaimValue`, `ClaimPercentage`, `PricePerUnit`, `Price`, `GrossWeight`, `OrderRuleName`, and a nested `Batches` collection.

## GET /api/OrderRule/{id}

Returns a 200 (OK) response with a single order rule (including its nested Batches), or 404 if not found.

!!! example "Request"
    ``` c#
    $"{api_url}/api/OrderRule/{order rule Guid}"
    ```

## POST /api/OrderRule

Creates a new order rule. Returns a 201 (Created) response with the new order rule's `Id`.

**Request body:** `OrderId`, `CreatedOn`, `LastDateTime`, `Description`, `ParentOrderName`, `ParentPurchaseOrderName`, `ClaimValue`, `ClaimPercentage`, `PricePerUnit`, `Price`, `GrossWeight`, `OrderRuleName`.

!!! Note
    Products are handled separately and won't be included in any order rule response.

!!! Note
    Updating an order rule, deleting an order rule, and order rule analytics endpoints aren't part of the external API.
