# NoBeds Calendar Sync & iCal Integration

[![NoBeds PMS](https://img.shields.io/badge/Platform-NoBeds.com-orange)](https://nobeds.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/nobedscom/nobeds-calendar-sync?style=social)](https://github.com/nobedscom/nobeds-calendar-sync)

Universal calendar synchronization, 2-way iCal integration, and booking automation utilities for [NoBeds](https://nobeds.com) — the Free Property Management System (PMS) and Channel Manager for hotels, apartments, vacation rentals, and guest houses.

---

## 🌟 What is NoBeds?

[NoBeds](https://nobeds.com) is an all-in-one cloud property management software designed for independent accommodation providers worldwide. It enables hoteliers and rental managers to:

- Synchronize calendars across **Airbnb, Booking.com, VRBO, Expedia, Agoda, Trip.com**, and direct booking channels.
- Prevent double-bookings with near-instant availability updates.
- Generate and manage direct booking widgets and website availability embeds.
- Automate guest messaging, invoices, check-in instructions, and payment tracking.

Official website: **[https://nobeds.com](https://nobeds.com)**

---

## 🔄 What Does This Repository Provide?

This repository contains integration guides, sample scripts, and technical references for connecting third-party platforms with NoBeds iCal and API endpoints:

1. **2-Way iCal Synchronization Reference**: How standard RFC 5545 iCalendar feeds map to NoBeds room units and availability dates.
2. **Channel Mapping Guides**: Best practices for syncing Airbnb, Booking.com, and VRBO calendar links with NoBeds.
3. **Automated Verification Snippets**: Lightweight Python and Node.js helpers to validate iCal feed availability status and detect date collisions before importing.

---

## 🚀 Quick Start: Testing an iCal Feed

To verify that an accommodation iCal link is responding and formatted correctly:

```python
import urllib.request

ical_url = "https://nobeds.com/your-property-feed-url.ics"

req = urllib.request.Request(ical_url, headers={"User-Agent": "NoBeds-Calendar-Sync/1.0"})
with urllib.request.urlopen(req) as response:
    content = response.read().decode("utf-8")
    events = [line for line in content.splitlines() if line.startswith("SUMMARY:")]
    print(f"Total bookings/blocks found: {len(events)}")
```

---

## 🔗 Related Resources & Links

- **Official Web Platform**: [https://nobeds.com](https://nobeds.com)
- **NoBeds PMS iOS App Repository**: [https://github.com/nobedscom/NoBeds-PMS](https://github.com/nobedscom/NoBeds-PMS)
- **Developer Documentation**: [https://nobeds.com/documentation/](https://nobeds.com)
- **Contact & Support**: [support@nobeds.com](mailto:support@nobeds.com)

---

## 📄 License

This repository is distributed under the MIT License.
