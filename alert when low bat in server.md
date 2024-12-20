# Low Battery Alert with Sound on Server

## 1. Check Battery Status
Use the `upower` command to get battery information:
```bash
upower -i $(upower -e | grep battery)
```
This will display details about your battery status.

## 2. Create a Shell Script
Write a script that checks the battery level and plays a sound if it’s low:

```bash
#!/bin/bash

# Define the threshold
LOW_BATTERY_THRESHOLD=15

# Get battery percentage
BATTERY_PERCENT=$(upower -i $(upower -e | grep battery) | grep "percentage" | awk '{print $2}' | tr -d '%')

# Check if battery level is below the threshold
if [ "$BATTERY_PERCENT" -le "$LOW_BATTERY_THRESHOLD" ]; then
    # Play a sound notification
    paplay /usr/share/sounds/freedesktop/stereo/battery-low.oga
fi
```

Save this file as `battery_check.sh`.

## 3. Install `paplay`
Ensure you have the `pulseaudio-utils` package installed, which includes `paplay`:
```bash
sudo apt update
sudo apt install pulseaudio-utils
```

## 4. Schedule the Script
Set up a cron job to run the script periodically.

Edit the crontab file:
```bash
crontab -e
```

Add a line to check the battery level every 5 minutes:
```bash
*/5 * * * * /path/to/battery_check.sh
```

## 5. Adjust Script Permissions
Make the script executable:
```bash
chmod +x /path/to/battery_check.sh
```

## 6. Customize the Sound (Optional)
You can replace `/usr/share/sounds/freedesktop/stereo/battery-low.oga` with any sound file of your choice.

---

## Notes
- If `upower` is not installed, you can install it using:
  ```bash
  sudo apt install upower
  ```
- Ensure audio is configured and functional on your server. If audio drivers are missing or not supported, consider redirecting notifications to another device.
