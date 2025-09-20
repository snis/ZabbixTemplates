# Zabbix SVG Graph Widget: Invert Y-Axis Patch

This document provides instructions on how to apply a patch to the SVG Graph widget in Zabbix to add an "Invert Y-Axis" option.

This is useful for metrics where a lower value is better, such as response times or error rates.

## Supported Versions

This patch is available for the following versions of the SVG Graph widget:

*   v7.4.2
*   v7.2.12

## Installation Instructions

1.  **Identify your widget version:**
    Before applying the patch, you need to determine the version of your installed SVG Graph widget. You can usually find this information in the `manifest.json` file located in the widget's directory.

2.  **Choose the correct patch file:**
    Based on your widget version, choose the corresponding patch file:

    *   For v7.4.2, use `svggraph_invert_y_axis_7.4.2.patch`.
    *   For v7.2.12, use `svggraph_invert_y_axis_7.2.12.patch`.

3.  **Navigate to the widget directory:**
    The SVG Graph widget is typically installed at the following location:

    ```bash
    /usr/share/zabbix/ui/widgets/svggraph
    ```

    You will need to have shell access to your Zabbix server to perform the next steps.

4.  **Apply the patch:**
    From the parent directory (`/usr/share/zabbix/ui/widgets/`), run the `patch` command. Use the `-p1` option to strip the leading directory from the file paths in the patch file.

    **For v7.4.2:**
    ```bash
    sudo patch -p1 -d svggraph < /path/to/svggraph_invert_y_axis_7.4.2.patch
    ```

    **For v7.2.12:**
    ```bash
    sudo patch -p1 -d svggraph < /path/to/svggraph_invert_y_axis_7.2.12.patch
    ```

    **Note:** Replace `/path/to/` with the actual path to the patch file on your system.

5.  **Restart the Zabbix server:**
    After applying the patch, you must restart the Zabbix server for the changes to take effect.

    ```bash
    sudo systemctl restart zabbix-server
    ```

## What the Patch Does

This patch adds an "Invert" checkbox to the data set configuration in the SVG Graph widget. When this option is enabled for a data set, the Y-axis values for that data set will be displayed as negative values, effectively inverting the graph.