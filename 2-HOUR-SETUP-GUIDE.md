# 2-Hour Setup Guide

Think of this like packing for a flight. Do it in order, check each box, and you won't scramble at the gate.

Total time: about 2 hours. Grab water first.

---

## Hour 1: Foundation (Shopify + Fulfillment)

### Step 1: Shopify store (15 min)
- [ ] Store created on Basic plan
- [ ] Currency and timezone set (USD / IST)
- [ ] Store name and logo added

### Step 2: Printful connection (15 min)
- [ ] Printful account connected to Shopify
- [ ] Test product synced
- [ ] Fulfillment auto-routing confirmed active

### Step 3: Hero product live (20 min)
- [ ] First product uploaded with mockups
- [ ] Sizes and variants set (aim for 5 size options)
- [ ] Price set in the $10 to $30 range
- [ ] Collection created and product added to it

### Step 4: Inventory check (10 min)
- [ ] Every variant has stock showing (no zero-stock listings)
- [ ] Confirm Printful is set to auto-fulfill, not manual

---

## Hour 2: Automation Layer

### Step 5: Mailchimp (20 min)
- [ ] Account connected to Shopify
- [ ] 5 sequences built: Welcome, Abandoned Cart, Post-Purchase, Re-engagement, VIP Loyalty
- [ ] At least 12 discount codes created and active

### Step 6: Google Sheets dashboard (10 min)
- [ ] "Daily Dashboard" sheet created
- [ ] Tabs for: Sales, Email Metrics, Discounts, Subscribers

### Step 7: Asana workspace (10 min)
- [ ] Project created for the business
- [ ] Sections for Daily / Weekly / Monthly tasks

### Step 8: Make.com workflows (30 min)
- [ ] Workflow 1: Daily Sales connected and tested
- [ ] Workflow 2: Email Metrics connected and tested
- [ ] Workflow 3: Weekly Report connected and tested
- [ ] Workflow 4: Discount Tracking connected and tested
- [ ] Workflow 5: Subscriber Alerts connected and tested
- [ ] Workflow 6: Monthly Report connected and tested

See `MASTER-AUTOMATION-BLUEPRINT.md` for what each workflow does and how to rebuild it.

### Step 9: End-to-end test (5 min)
- [ ] Place a test order
- [ ] Confirm it shows up in Google Sheets within a few minutes
- [ ] Confirm Printful picked it up for fulfillment

---

## You're done when...

Every box above is checked AND a test order flows through the whole chain without you touching anything.

That's the whole point. Set it once, let it run.

## If something breaks

1. Check Make.com's "Execution History" for the workflow that failed. It shows exactly which step errored.
2. Most failures are a broken connection (an app got disconnected). Reconnect it and re-run.
3. If a workflow just won't cooperate, re-import the `.json` blueprint from `docs/blueprints/`.
