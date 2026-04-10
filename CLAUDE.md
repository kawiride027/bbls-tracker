# TGD Dumpster Pricing Sheet — Complete Documentation

## Overview
Internal tool for **The Green Dumpster** enabling customer service reps to instantly look up zone-based pricing by zip code, build itemized quotes, and send them to customers.

## Tech Stack
- React 18 (CDN-loaded)
- Babel Standalone (in-browser JSX)
- Single HTML file (no build step)
- GoHighLevel webhook integration
- Branded email template

## Project Structure
```
TGD-Dumpster-PRICING-SHEET/
├── index.html              
├── email-template.html     
├── google-sheet-script.js  
└── CLAUDE.md
```

## Core Functionality

**Zip Code Lookup**: Maps 5-digit codes to 18 service zones covering Valley, South Valley, Southwest, East Valley, LA, Far East Valley, Beach, Far West, SCV, and partner zones.

**Zone Types**: In-House (TGD fleet, supports discounts), Outsourced (partner haulers, no discounts), NEED HAULER (unassigned), Junk Removal Only.

**Bin Sizes**: 3 Yard, 3 Yard w/ Wheels, 9 Yard, 10 Yard Clean, 10 Yard, 12 Yard, 16 Yard, 25 Yard, 40 Yard — each with contractor/residential pricing, tonnage, rental days, extra fees, overload rates, and discount caps.

**Quote Builder**: CSRs select bin(s), apply discounts, send via GHL webhook triggering customer email + SMS.

**Estimate Numbers**: Format `TGD-YYYYMMDD-XXXX` generated at send time, included in email and webhook payload.

**Google Sheets Logging**: Auto-logs quotes via Apps Script (setup: add `GOOGLE_SHEET_URL` to index.html).

**Hidden Feature**: Type zip `99999` to export pricing matrix CSV for Docket import.

## Discount System (In-House Only)
- Per-bin dollar caps
- Multi-bin 3-yard deals
- Extended rental (up to 2 free extra days)

## Email Template
MJ/MJML-compatible responsive design using GHL variables, brand colors (green `#1B8C2A`, dark `#1a3a1a`), company contact: (818) 404-5865, address: 9909 Topanga Cyn Blvd #272 Chatsworth, CA 91311.

## CSR Team
Evelyn, Tais, Emely, Kevin, CJ, Luis, Felix, Yuly, Dory, Dustin, Clint (@thegreendumpster.com).

## Development
Edit `index.html` directly; all zone/pricing data hardcoded in `ZONES` array. Add zones by appending objects with name, zips, pricing, service fields.

## Pricing Strategy
Baseline fuel: $5.50/gal; as of 2026-03-26: $7.09/gal (~29% increase). Only in-house zones under TGD control; outsourced set by partners.

## Recent Changes (2026-03-26)
Raised minimum overage to $120/Ton (9yd+ in-house/outsourced); Heritage at $125/Ton; 3yd at $16/100 Lb. Updated 10yd descriptions: general trash $120/ton, C&D $130/ton. Added unique estimate numbers and Google Sheets auto-logging.
