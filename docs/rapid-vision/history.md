# History

**History** shows the most recent products detected by the currently connected vision system, so you can review recent results without switching back to [Live View](live-view.md).

!!! note
    History only keeps the last 50 detections in memory for the current session — it is not a persisted log, and it resets when you reconnect or restart the client. For browsing and reporting on results over longer time ranges, use **RapiD Vision Explorer** instead.

## What's Shown

Each detected product appears as its own card, most recent first, with:

- **Label** and the time it was detected.
- **Sorting** output, **Score**, **Length**, **Width**, **Height**, **Position**, **Weight**, **Orientation**, **Volume**, and **Area**.
- Any detected defect **spots**, each with its own label, score, area, width, and height.
- The top camera image, and the bottom camera image if the configuration uses a bottom detector, both with the detection overlay drawn on them. Scroll to zoom, drag to pan.

## Sorting the List

Use the sorting dropdown to reorder the cards:

- **Time Ascending** / **Time Descending**
- **Length Ascending** / **Length Descending**
- **Label** — groups results alphabetically by label

## Pausing History

Select **Pause** to freeze the list so you can review a result without newer detections pushing it out of view. Select **Resume** to continue receiving new detections.

## Limitations

History currently has no search, filtering (by label, sorting output, or date), or export option, and it isn't organized by batch. If you need any of that, use RapiD Vision Explorer.
