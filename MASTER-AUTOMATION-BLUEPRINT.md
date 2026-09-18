# Master Automation Blueprint

## The big idea

You run this business from your phone. Shopify takes the order. Make.com does the busywork. You just watch the numbers go up.

**System flow:**

```
Shopify --> Make.com (6 workflows) --> Google Sheets + Asana + Mailchimp + Gmail
```

Six workflows. Each one has ONE job. Simple beats clever every time.

---

## Workflow 1: Daily Sales

**Trigger:** New order in Shopify (checked once daily, or on a schedule you set)

**What it does:**
1. Pulls the day's orders from Shopify
2. Adds them as rows in the "CHOOSE REAL - Daily Dashboard" Google Sheet
3. Flags any order over a set dollar amount for a quick look

**Why it matters:** You never have to log into Shopify just to check "did anything sell today?"

**To rebuild in Make.com:**
- Module 1: Shopify > Watch Orders
- Module 2: Google Sheets > Add a Row
- Module 3 (optional): Filter > only run if order total > threshold

---

## Workflow 2: Email Metrics

**Trigger:** Scheduled (daily)

**What it does:**
1. Pulls open rate, click rate, and unsubscribe count from Mailchimp
2. Logs them in Google Sheets
3. Lets you spot a dying subject line before it tanks a whole sequence

**To rebuild in Make.com:**
- Module 1: Schedule trigger (once a day)
- Module 2: Mailchimp > Get Campaign Report
- Module 3: Google Sheets > Add a Row

---

## Workflow 3: Weekly Report

**Trigger:** Scheduled (once a week)

**What it does:**
1. Rolls up the week's sales, email performance, and discount usage
2. Sends a summary email to your inbox via Gmail
3. Creates a "Review weekly report" task in Asana so it doesn't get lost

**To rebuild in Make.com:**
- Module 1: Schedule trigger (weekly)
- Module 2: Google Sheets > Search Rows (pull the week's data)
- Module 3: Gmail > Send Email
- Module 4: Asana > Create Task

---

## Workflow 4: Discount Tracking

**Trigger:** New order in Shopify with a discount code applied

**What it does:**
1. Logs which discount code was used
2. Counts redemptions per code in Google Sheets
3. Tells you which of your 12 codes are actually pulling weight

**To rebuild in Make.com:**
- Module 1: Shopify > Watch Orders
- Module 2: Filter > only run if discount_code is present
- Module 3: Google Sheets > Add a Row or Update Row (increment count)

---

## Workflow 5: Subscriber Alerts

**Trigger:** New subscriber in Mailchimp

**What it does:**
1. Sends you a Gmail alert when the list grows
2. Logs the new subscriber count in Google Sheets
3. Optional: creates an Asana task to send a personal welcome for VIP-tier signups

**To rebuild in Make.com:**
- Module 1: Mailchimp > Watch Subscribers
- Module 2: Gmail > Send Email (short alert)
- Module 3: Google Sheets > Add a Row

---

## Workflow 6: Monthly Report

**Trigger:** Scheduled (1st of the month)

**What it does:**
1. Pulls a full month of sales, email, and discount data
2. Builds a summary and emails it to you
3. Creates an Asana task: "Review month, plan next 30 days"

**To rebuild in Make.com:**
- Module 1: Schedule trigger (monthly)
- Module 2: Google Sheets > Search Rows (pull the month's data)
- Module 3: Gmail > Send Email
- Module 4: Asana > Create Task

---

## Where the JSON blueprints go

Make.com lets you export each scenario as a `.json` blueprint file. Export yours and drop them here:

```
docs/blueprints/
    daily-sales.json
    email-metrics.json
    weekly-report.json
    discount-tracking.json
    subscriber-alerts.json
    monthly-report.json
```

That way, if a workflow breaks, you can re-import the exact working version instead of rebuilding from scratch.

## Why this setup works

Think of it like a restaurant kitchen. The waiter (Shopify) takes the order. The expo line (Make.com) routes it to the right station. Nobody's running back and forth. Everybody just does their one job, fast.

**Time saved:** ~5-7 hours a month you get back to spend on content and product, not spreadsheets.
