# Options — Lanes

The **Lanes** tab lets you draw named regions directly on the selected camera's image, for the currently selected Top or Bottom camera.

!!! note
    This is not the same feature as **Lane Manager**. Lane Manager is a live operational view for connected conveyors, robots, and weighing modules — start/stop, speed, and connection status. The Lanes tab here is just about defining regions on the camera image itself; it doesn't show or control any live conveyor hardware.

## Creating a Lane

1. Select **Create Lane**. A new rectangular region appears centered on the image.
2. Drag its four colored corner handles to reshape it as needed.
3. The lane's four corner coordinates are listed under **Configured Lanes**, next to its name.

## Managing Lanes

Each lane in the **Configured Lanes** list shows its name and live corner coordinates, along with a **Delete** button to remove it.

!!! warning
    Creating a lane while editing the **Bottom** camera's configuration triggers a "System needs restart!" notice — restart the system afterward for it to take effect. This doesn't apply to lanes created on the Top camera.

Remember to select **Save** on the Options toolbar once you're done — like other tabs, lane changes apply live but aren't kept after a restart until saved.
