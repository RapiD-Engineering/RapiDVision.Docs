# Batch

Direct interactions with the API require a valid Bearer token or an `X-Api-Key` header, and your account or key must be linked to a valid company registered with RapiD Engineering.

??? example "Accepted DateTime format"
    ```
    2026-04-10T13:19:47Z
    "yyyy-MM-ddTHH:mm:ssZ"
    ```

## GET /api/Batch

Returns a 200 (OK) response with a list of batches in the given date range. Batches don't include their Products.

- Requires valid `startDate` and `endDate` values.
- An optional `search` parameter searches by batch ID, order rule ID, supplier, or product description — when provided, the date range is ignored.

!!! example "Request"
    ``` c#
    $"{api_url}/api/Batch?startDate={datetime}&endDate={datetime}"
    ```

**Response fields:** `Id`, `OrderRuleId`, `RapiDVisionDeviceId`, `BatchStart`, `LastDateTime`, `DataCount`, `Supplier`, `ProductDescription`, `SegmentationDefectPercentage`, `ClassificationDefectPercentage`, `ColorDefectPercentage`, `NetWeight`, `CustomFields`.

## GET /api/Batch/{id}

Returns a 200 (OK) response with a single batch, or 404 if not found.

!!! example "Request"
    ``` c#
    $"{api_url}/api/Batch/{batch Guid}"
    ```

## GET /api/Batch/Latest

Returns a 200 (OK) response with the most recently updated batch, or 404 if none exist.

!!! example "Request"
    ``` c#
    $"{api_url}/api/Batch/Latest"
    ```

## PATCH /api/Batch/{id}

Applies a partial update to an existing batch's editable fields. Returns a 204 (No Content) response on success, or 200 with a message if nothing changed.

**Request body (any subset of):** `BatchStart`, `LastDateTime`, `DataCount`, `Supplier`, `ProductDescription`, `SegmentationDefectPercentage`, `ClassificationDefectPercentage`, `ColorDefectPercentage`, `NetWeight`, `CustomFields`, `RapiDVisionDeviceId`.

!!! example "Request"
    ``` c#
    PATCH $"{api_url}/api/Batch/{batch Guid}"
    ```

## POST /api/Batch

Creates a new batch, optionally creating its parent Order and Order Rule in the same call if they don't already exist yet (matched by name). Returns a 200 (OK) response with the created `batchId`, `orderRuleId`, and `orderId`, or a 409 (Conflict) response if a batch with the given `BatchId` already exists.

**Request body:**

| Field | Description |
|---|---|
| `BatchId` | Optional — provide to control the batch's Id, otherwise one is generated. |
| `BatchStart` / `LastDateTime` | Batch timing. |
| `Supplier` / `ProductDescription` | Batch details. |
| `DeviceId` | The RapiD Vision device that created this batch. |
| `Order` / `OrderPrice` / `OrderCreationDate` | Optional — creates a new Order if one with this name doesn't already exist. |
| `OrderRule` / `OrderRulePricePerUnit` / `OrderRulePrice` / `OrderRuleGrossWeight` | Optional — creates a new Order Rule under the Order. Requires `Order` to also be set. |
| `CustomFields` | Optional key/value pairs stored on the batch. |

!!! Note
    Products, per-batch analytics, and supplier statistics aren't part of the external API.
