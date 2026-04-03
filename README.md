# 🗾 Japan Trip 2026

A mobile-first family travel itinerary app for a 7-day Japan trip (April 6–12, 2026). No installation or build step required — just open the HTML file in any browser.

## Features

- Day-by-day navigation across the full trip
- Event timeline with time, icons, and status tags
- Tap any event for detailed info (map, transit routes, dining notes, reminders)
- One-tap address copy + Google Maps navigation links
- Weather display per day
- Fully responsive, optimized for mobile

## Files

| File | Description |
|------|-------------|
| `japan-trip-2026.html` | Main itinerary (Day 1–6) |
| `japan-trip-2026_2.html` | Extended version with Day 7 (return flight) |

## How to Use

### Option 1 — Open Directly (simplest)

Download the repo and double-click either HTML file. No server needed.

### Option 2 — Local Server (better PWA support on mobile)

```bash
cd japan-trip-2026
python3 -m http.server 8000
```

Then open `http://localhost:8000/japan-trip-2026_2.html` in your browser.

To access from a phone on the same Wi-Fi, replace `localhost` with your computer's local IP address (e.g. `http://192.168.x.x:8000/japan-trip-2026_2.html`).

### Option 3 — Save to Phone Home Screen

On iOS Safari or Android Chrome, open the URL and use **Add to Home Screen** to install it as a web app.

## Customizing the Itinerary

All trip data lives in the `itineraryData` array inside the HTML file. Each day is an object with:

```js
{
  id: 'day1',
  date: '4/6',
  weekday: '一',
  title: '...',
  image: 'https://...',       // hero image URL
  weather: { temp: '16°C', condition: '多雲', icon: 'fa-cloud' },
  events: [
    {
      time: 'HH:MM',
      title: '...',
      desc: '...',
      icon: 'fa-icon-name',   // Font Awesome icon
      tag: { text: '...', color: 'bg-...' },
      details: {
        map: { ... },          // location + Google Maps link
        transitRoute: { ... }, // multi-leg transit breakdown
        restaurantNotes: '...', 
        notes: '...'
      }
    }
  ]
}
```

Edit the array, save the file, and refresh the browser.

## Requirements

- Any modern browser (Chrome, Safari, Firefox, Edge)
- No npm, no build tools, no backend
