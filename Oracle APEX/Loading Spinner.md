# Loading Spinner
The loading spinner is a progress indicator to let the user know a process hasn't yet finished and this also works 
as an effective way to prevent the user from making any other actions while the process is in progress.

To have this effect throughout the application, this should be implemented on the global page.

## Implementation
First, create a *Dynamic Action* on the page with the following properties:
- **When**: Before Page Submit

Next, create a True action: *Execute JavaScript Code* with the following source code:
`apex.widget.waitPopup();`
