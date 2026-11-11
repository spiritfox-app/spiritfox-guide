# Keep the device clock accurate

If your device's time is too far off, encrypted connections are refused. You'll see that no server connects at all.

## Turn on automatic time, then restart the app
- **iPhone, iPad:** Settings › General › Date & Time › Set Automatically.
- **Android:** Settings › System › Date & time › Set time automatically (names vary by brand).
- **Mac:** System Settings › General › Date & Time › Set time and date automatically.
- **Windows:** Settings › Time & language › Date & time › Set time automatically, then click "Sync now".

The time zone must be right too, not just the hour.

## When to suspect the clock
- Nothing connects, whichever server you pick.
- Some websites say "Your clock is ahead" or "Your clock is behind".
- The trouble started after travelling, after the phone ran flat, or after changing the time by hand.

## Why time matters
Encrypted connections carry timestamps, and each side checks the other's time is close to its own. This stops anyone recording a session and replaying it later. If your time is too far off, the other side treats it as suspicious and closes the connection. It's like a ticket valid only today: if your watch says yesterday, the gate won't open even though the ticket is real.
