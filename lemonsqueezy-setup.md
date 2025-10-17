# LemonSqueezy Setup Guide

Complete guide to setting up LemonSqueezy for ultramap payments.

---

## Step 1: Create Account

1. Go to https://lemonsqueezy.com
2. Sign up for a free account
3. Complete email verification
4. Complete identity/business verification process

---

## Step 2: Create Your Store

1. Navigate to Store Settings
2. Set store name (e.g., "ultramap" or your company name)
3. Add business details:
   - Business name
   - Contact email
   - Address (required for tax purposes)
4. Configure store URL slug

---

## Step 3: Connect Payout Method

1. Go to Settings → Payouts
2. Connect your bank account or PayPal
3. Complete payout verification
4. Set payout schedule preferences

---

## Step 4: Create Product

1. Go to **Products** → **New Product**
2. Configure product details:
   - **Product type:** Single payment
   - **Name:** ultramap
   - **Price:** $10 USD
   - **Description:**
     ```
     ultramap - Simple, powerful whiteboarding software

     • Full whiteboarding features
     • AI brainstorming assistant
     • Unlimited boards
     • Lifetime license
     • All future updates included
     ```

3. Product image (optional but recommended)
4. Save product

---

## Step 5: Configure Product Settings

### License Keys (Recommended)
1. Enable "Generate license keys" in product settings
2. Configure license key format
3. Set up activation limits if needed

### File Delivery (If applicable)
1. Upload product files (Mac/Windows/Linux versions)
2. Configure download links
3. Set file access duration

### Email Configuration
1. Customize receipt email
2. Set up welcome email with:
   - Download links
   - License key
   - Getting started instructions
   - Support contact info

---

## Step 6: Get Checkout URL

After creating your product:

1. Go to your product page
2. Copy the checkout URL:
   ```
   https://yourstore.lemonsqueezy.com/checkout/buy/[product-id]
   ```

3. **Optional:** Configure checkout overlay for embedded experience

---

## Step 7: Integrate into Website

Once you have your checkout URL, update these files:

### Files to Update:
- `index.html` - Update all "Buy Now" button links

### Locations to Update:
1. **Navigation** (line ~23):
   ```html
   <a href="YOUR_LEMONSQUEEZY_URL" class="btn-primary">Buy Now</a>
   ```

2. **Hero Section** (line ~31):
   ```html
   <a href="YOUR_LEMONSQUEEZY_URL" class="btn-primary btn-large">Get ultramap</a>
   ```

3. **Pricing Section** (line ~145):
   ```html
   <a href="YOUR_LEMONSQUEEZY_URL" class="btn-primary btn-large">Get ultramap Now</a>
   ```

---

## Step 8: Test Purchase

1. Use LemonSqueezy's test mode
2. Make a test purchase
3. Verify:
   - Checkout flow works
   - Emails are sent correctly
   - License keys generate (if enabled)
   - Download links work (if applicable)

---

## Step 9: Go Live

1. Disable test mode in LemonSqueezy settings
2. Push updated website with real checkout links
3. Make your first real purchase to verify everything works

---

## Important Notes

### Fees
- 5% LemonSqueezy fee + payment processing (~3%)
- Total: ~8% per transaction

### Tax Compliance
- LemonSqueezy acts as Merchant of Record
- They handle all VAT/sales tax automatically
- You don't need to worry about tax compliance

### Early Bird Discount
When you want to increase the price:
1. Edit product in LemonSqueezy
2. Change price from $10 to new amount
3. Update website text to reflect new pricing
4. Can keep old $10 links for existing customers/affiliates

---

## Support Resources

- LemonSqueezy Documentation: https://docs.lemonsqueezy.com
- Help Center: https://lemonsqueezy.com/help
- Email Support: Available through dashboard

---

## Next Steps

1. [ ] Create LemonSqueezy account
2. [ ] Set up store
3. [ ] Create ultramap product
4. [ ] Configure license keys
5. [ ] Get checkout URL
6. [ ] Share URL to integrate into website
7. [ ] Test purchase flow
8. [ ] Go live!
