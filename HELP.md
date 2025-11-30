# 📚 DrawPix Complete Help Center & Troubleshooting Guide 🛠️

Welcome to the **DrawPix Help Center**.
This guide covers **every common and rare issue** users may experience while using DrawPix, explains **why it happens**, and provides **clear solutions**.

---

# ⚠️ Error Categories Overview

Errors on DrawPix usually fall into the following groups:

1. **Connection & Network Errors**
2. **Server & API Errors**
3. **Pixel Interaction Errors**
4. **Canvas, Zoom & Movement Errors**
5. **Color Picker & Input Errors**
6. **Video Ad / Unlock System Errors**
7. **Browser, Device & Extension Issues**
8. **Unexpected, Rare or Unknown Errors**

Each section below contains a full description and solution steps.

---

# 1️⃣ Connection & Network Errors

## **1. "Error connecting to server"**

Your browser failed to connect to the DrawPix backend.

### Why it happens:

* No internet or unstable connection
* Firewall or Wi-Fi restrictions (school / work networks)
* VPN or proxy interference
* Browser blocked the Worker URL
* Cloudflare Worker temporarily down

### How to fix:

1. Check your internet connection.
2. Refresh the page (**Ctrl+Shift+R** / **Cmd+Shift+R**).
3. Disable VPN or try another network.
4. Turn off ad blockers or privacy extensions.
5. Try another browser (Chrome, Firefox, Edge).
6. Check GitHub for outages:
   **github.com/SlizR/DrawPix**

---

## **2. "Failed to load pixel data"**

The canvas did not receive pixel information from the API.

### Why:

* Worker responded slowly
* JSON parsing error
* Server temporarily overloaded

### Fix:

* Refresh the page
* Wait 30–60 seconds and retry
* If persistent → report the issue (steps at bottom)

---

## **3. "Error updating pixels"**

The periodic auto-refresh failed.

### Why:

* Server timeout
* You lost connection for a moment

### Fix:

* Check internet
* Manual refresh
* Disable extensions that block requests

---

# 2️⃣ Server & API Errors

## **4. "Error saving pixel"**

The server rejected your request.

### Why:

* Backend returned an error message
* Invalid request payload
* Server received too many requests at once

### Fix:

* Try again in a few seconds
* If repeated, include console logs when reporting the bug

---

## **5. API Error Codes (HTTP)**

### **403 — Forbidden**

Your request was blocked, possibly due to:

* VPN
* Proxy
* Country/region filtering
* Firewall

**Fix:** Disable VPN, try another network.

### **404 — Not Found**

The endpoint path is wrong or temporarily unavailable.
Fix: Refresh the page; if still failing → report.

### **500 — Internal Server Error**

Something crashed inside the Worker.
Fix: Wait and retry; report with console log.

### **503 — Service Unavailable**

Server overload or maintenance.
Fix: Wait 1–3 minutes and retry.

### **Timeout**

Server didn’t respond quickly enough.
Fix: Retry later; possibly heavy traffic.

---

# 3️⃣ Pixel Interaction Errors

## **6. "This pixel is already colored!"**

The pixel you clicked already has a color.

### Why:

* Someone else colored it before you
* Auto-refresh didn’t update instantly

### Fix:

* Pick another pixel
* Wait ~20s for auto-update
* Press Ctrl+Shift+R to force reload

---

## **7. "No pixel selected!"**

You opened the color picker but no pixel was chosen.

### Fix:

* Close the color picker
* Click a pixel again
* Reopen color picker automatically

---

## **8. Long-press or double-tap not working (Mobile)**

### Why:

* Touch movement interpreted as pan
* Very fast gestures

### Fix:

* Press and hold firmly for at least 300 ms
* Ensure the finger stays mostly still
* Zoom in before selecting

---

# 4️⃣ Canvas, Zoom & Movement Errors

## **9. Canvas not moving / stuck**

### Why:

* Browser prevented pointer events
* Touch gestures misinterpreted
* Lag from many pixels

### Fix:

* Refresh
* Try desktop mode on mobile
* Disable overlays (pull down the browser UI)

---

## **10. Zoom not working**

### Why:

* Touch gestures conflicting
* Browser blocks pinch-zoom
* Trackpad gesture disabled

### Fix:

* Use the **+ / − / ⟲** buttons
* Use mouse wheel on desktop
* Try a two-finger gesture slower

---

## **11. Canvas looks blurry or offset**

### Why:

* Browser scaling issues
* Incorrect screen-to-canvas mapping

### Fix:

* Reload page
* Reset zoom
* Change device orientation (mobile)

---

# 5️⃣ Color Picker & Input Errors

## **12. "Invalid color!"**

The chosen color isn't a valid HEX code.

### Why:

* Manual entry incorrect
* Missing `#` or hex digits

### Fix:

* Use the built-in color picker
* Use format: `#RRGGBB`

---

## **13. Color picker not opening**

### Why:

* Popup blocked
* Pixel already colored
* UI froze

### Fix:

* Refresh page
* Disable ad blockers
* Try selecting another pixel

---

# 6️⃣ Video Ad / Unlock System Errors

## **14. "Click the black area to start the ad."**

Browser blocked autoplay.

### Fix:

* Tap/click anywhere on the black overlay
* Make sure your browser allows media playback

---

## **15. Video frozen or not loading**

### Why:

* Browser blocking media
* Slow connection
* Video decode error

### Fix:

* Wait 5 seconds (auto-unlock may happen)
* Tap overlay
* Disable low-power mode
* Try another browser

---

## **16. Timer not appearing**

### Why:

* Video metadata not loaded yet

### Fix:

* Tap the overlay to force playback
* Wait a moment

---

## **17. Ad instantly finishes or skips**

System detected video failure and auto-unlocked the pixel.

### Fix:

* Simply close the ad and choose color again

---

# 7️⃣ Browser, Device & Extension Issues

## **18. “Nothing happens when clicking pixel”**

### Causes:

* UI layer loaded incorrectly
* Browser extensions blocking click events
* Your browser disabled canvas pointer events

### Solutions:

* Disable extensions
* Try private/incognito mode
* Use another browser (Chromium recommended)

---

## **19. Fonts, UI or layout broken**

### Why:

* Aggressive ad blockers
* CSS blocked
* Browser outdated

### Fix:

* Disable extensions
* Refresh with Ctrl+Shift+R
* Try another browser

---

## **20. "WebGL" or rendering errors**

Not common, but some old devices may fail to render canvas.

### Fix:

* Switch to desktop mode
* Use a modern browser (Chrome/Edge/Firefox)

---

# 8️⃣ Unknown, Rare or Internal Errors

## **21. “[DEBUG] …” errors in console**

These are developer logs — not harmful.

### Fix:

No action required.

---

## **22. “Unexpected token …” (JSON parse error)**

Server sent malformed data (usually temporary).

### Fix:

* Refresh page
* If repeated → report with screenshot

---

## **23. “Cannot read property … of undefined”**

A script tried to read an unloaded element.

### Fix:

* Reload
* Wait for page to fully load
* Try another device if persistent

---

# 🐛 Need More Help?

If the steps above don’t solve your issue, please submit a **Bug Report**:

### 📩 How to report properly:

1. Open **DevTools** → Console (F12).
2. Copy any **red errors** or log messages.
3. Go to GitHub Issues:
   **[https://github.com/SlizR/DrawPix/issues](https://github.com/SlizR/DrawPix/issues)**
4. Include:

   * What you were doing
   * What error appeared
   * Logs
   * Browser + device type
   * Screenshots if possible

Your reports help us keep DrawPix stable for everyone. ❤️
