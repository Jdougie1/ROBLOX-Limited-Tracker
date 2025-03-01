This Python script is a Roblox limited item tracker that uses a graphical user interface (GUI) built with Tkinter.

Key Points:

User Input:
The user enters three things in the GUI:

The Limited Item ID (the Roblox item to monitor)
A Target Price (the price threshold to trigger an alert)
A Check Interval in seconds (how often the app checks the item)
Authentication & Session Setup:
The code sets up an authenticated HTTP session with Roblox using a provided .ROBLOSECURITY cookie and retrieves a CSRF token. This ensures the app can make API requests to Roblox without being logged out.

Monitoring Process:
A background thread periodically makes API calls to fetch item details and seller data.

It retrieves the current lowest price from available sellers.
It compares this price to the user-specified target price.
Notifications:
If the lowest price meets or falls below the target price, the application opens the item’s page in the default web browser and triggers a notification sound.

On Windows, it uses winsound for the beep; on other platforms, it uses Tkinter’s bell.
Logging:
All actions, status updates, and errors are logged in a text widget within the GUI and also appended to a log file ("tracker_log.txt").

Graceful Shutdown:
The program ensures that when the GUI is closed, any running monitoring thread is stopped and all resources (like open log files) are properly closed.
