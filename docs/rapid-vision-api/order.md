# Order

Direct interactions with the API require a valid Bearer token or an `X-Api-Key` header, and your account or key must be linked to a valid company registered with RapiD Engineering.

??? example "Accepted DateTime format"
    ```
    2026-04-10T13:19:47Z
    "yyyy-MM-ddTHH:mm:ssZ"
    ```

## GET /api/Order

Returns a 200 (OK) response with a list of orders in the given date range. Each order includes its nested Order Rules, which include their Batches.

- Requires valid `startDate` and `endDate` values.
- An optional `search` parameter searches by order ID, order name, or purchase order name — when provided, the date range is ignored.

!!! example "Request"
    ``` c#
    $"{api_url}/api/Order?startDate={datetime}&endDate={datetime}"
    ```

**Response fields:** `Id`, `OrderName`, `PurchaseOrderName`, `ReceivedAt`, `LastDateTime`, `ClaimValue`, `ClaimPercentage`, and a nested `Rules` collection.

## GET /api/Order/{id}

Returns a 200 (OK) response with a single order, or 404 if not found.

!!! example "Request"
    ``` c#
    $"{api_url}/api/Order/{order Guid}"
    ```

**Response fields:** `Id`, `OrderName`, `PurchaseOrderName`, `ReceivedAt`, `LastDateTime`, `ClaimValue`, `ClaimPercentage` (no nested Rules).

## GET /api/Order/Latest

Returns a 200 (OK) response with the most recently updated order (including its Rules and their Batches), or 404 if no orders exist.

!!! example "Request"
    ``` c#
    $"{api_url}/api/Order/Latest"
    ```

## POST /api/Order

Creates a new order. Returns a 201 (Created) response with the new order's `Id`.

**Request body:** `OrderName`, `PurchaseOrderName`, `ReceivedAt`.

!!! Note
    Products are handled separately and won't be included in any order response.

!!! Note
    Updating an order, deleting an order, and order analytics endpoints aren't part of the external API.
