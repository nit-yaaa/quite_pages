MY NOTEBOOK — SETUP GUIDE
==========================

This folder is a small installable app: a journal, a task list, and a
calendar, all private to you. Your entries are saved right in your
browser on each device (via localStorage) — nothing is sent anywhere.

Because phones and "Install App" buttons only work over a real address
(not a random double-clicked file), you need to serve this folder from
a tiny local server first. That sounds technical but it's one line.


STEP 1 — Run a local server
----------------------------
Open a terminal, go into this folder, and run:

  Mac/Linux (Python is usually already installed):
    cd path/to/notebook-app
    python3 -m http.server 8000

  Windows (PowerShell):
    cd path\to\notebook-app
    py -m http.server 8000

Leave that terminal window open — it's now quietly serving your app.
Keep this running whenever you want to use the app (or set it to run
automatically at login — see "Making it permanent" below).


STEP 2 — Install it on your laptop
------------------------------------
1. Open Chrome or Edge.
2. Go to:  http://localhost:8000
3. Look in the address bar for an install icon (a little monitor with
   a down arrow), or open the browser menu and choose
   "Install My Notebook..." / "Apps > Install this site as an app".
4. Click Install. It now opens in its own window, with its own icon,
   like any other desktop app — no browser bar, no tabs.


STEP 3 — Install it on your phone
------------------------------------
Your phone needs to reach your laptop's server over the same Wi-Fi:

1. On your laptop, find its local IP address:
     Mac:     System Settings > Wi-Fi > Details > IP Address
     Windows: run `ipconfig` in Command Prompt, look for IPv4 Address
   It'll look like 192.168.1.42

2. On your phone (connected to the same Wi-Fi), open a browser and go to:
     http://192.168.1.42:8000   (use YOUR laptop's address)

3. iPhone (Safari): tap the Share icon > "Add to Home Screen".
   Android (Chrome): tap the ⋮ menu > "Install app" or
   "Add to Home screen".

4. You'll get a real app icon on your home screen that opens full
   screen, no browser chrome.

Note: your phone and laptop will have separate copies of your notes
(each device saves its own data locally). If you want the exact same
notes on both, keep using the version inside the Claude app instead —
that one syncs through your Claude account.


MAKING IT PERMANENT (optional)
--------------------------------
Running a terminal command every time is annoying. Two easy options:

- Keep it simple: leave a terminal tab open with the server running
  whenever you want the app available (close it, close the app).

- Go further: host these same files for free on GitHub Pages or
  Netlify Drop (netlify.com/drop — just drag this folder in). You'll
  get a permanent https:// address you can install from anywhere,
  including away from home Wi-Fi. Ask me if you'd like help with this.


FILES IN THIS FOLDER
----------------------
index.html     — the app itself
manifest.json  — tells the browser this is an installable app
sw.js          — lets the app work offline once installed
icon.svg       — the app icon
