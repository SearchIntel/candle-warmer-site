# Candle Warmer Lamps UK - Deployment Guide

## Project Summary

This is a complete affiliate website for candle warmer lamps targeting the UK market. The site includes:
- Responsive, mobile-first design
- 7 product reviews with affiliate links
- Comparison table
- Buying guide
- FAQ section with schema markup
- SEO optimisation (meta tags, Open Graph, schema.org markup)

---

## Quick Start Checklist

### Before You Deploy

- [ ] Register domain at Porkbun (~£2.25 first year)
- [ ] Sign up for Amazon Associates UK
- [ ] Replace `YOURID-21` with your actual Associate ID in all files
- [ ] Add your Google Analytics 4 measurement ID
- [ ] Add your Microsoft Clarity project ID

---

## Step 1: Register Your Domain

**Recommended:** bestcandlewarmers.co.uk at Porkbun

1. Go to https://www.porkbun.com
2. Search for `bestcandlewarmers.co.uk`
3. Add to cart and purchase (~$2.84 / £2.25 first year)
4. Complete checkout

**Alternative domains (if unavailable):**
- candlewarmerguide.co.uk
- warmyourcandle.co.uk
- candlewarmerlamps.uk

---

## Step 2: Amazon Associates Setup

1. Go to https://affiliate-program.amazon.co.uk
2. Click "Join Now for Free"
3. Complete the application:
   - **Website:** bestcandlewarmers.co.uk
   - **Description:** "Product reviews and buying guides for candle warmers and home fragrance accessories"
   - **Traffic methods:** SEO, content marketing
   - **Topics:** Home & Garden

4. Note your Associate ID (format: yourname-21)

**Important:** You have 180 days to make 3 qualifying sales

---

## Step 3: Update Affiliate Links

Find and replace all instances of `YOURID-21` with your actual Amazon Associate ID.

**Files to update:**
- `index.html` (contains multiple affiliate links)

**Search for:** `tag=YOURID-21`
**Replace with:** `tag=your-actual-id-21`

**Quick find/replace in VS Code:**
1. Open the project folder
2. Press `Cmd+Shift+H` (Mac) or `Ctrl+Shift+H` (Windows)
3. Find: `YOURID-21`
4. Replace: `youractualid-21`
5. Click "Replace All"

---

## Step 4: Set Up Analytics

### Google Analytics 4

1. Go to https://analytics.google.com
2. Create a new property
3. Set up a web data stream for your domain
4. Get your Measurement ID (starts with `G-`)
5. In `index.html`, uncomment the GA4 code and replace `G-XXXXXXXXXX`:

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-YOUR-ID"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-YOUR-ID');
</script>
```

### Microsoft Clarity

1. Go to https://clarity.microsoft.com
2. Create a new project
3. Get your project ID
4. In `index.html`, uncomment the Clarity code and replace `XXXXXXXXXX`:

```html
<script type="text/javascript">
    (function(c,l,a,r,i,t,y){
        c[a]=c[a]||function(){(c[a].q=c[a].q||[]).push(arguments)};
        t=l.createElement(r);t.async=1;t.src="https://www.clarity.ms/tag/"+i;
        y=l.getElementsByTagName(r)[0];y.parentNode.insertBefore(t,y);
    })(window, document, "clarity", "script", "YOUR-PROJECT-ID");
</script>
```

---

## Step 5: Deploy to Vercel

### Option A: GitHub + Vercel (Recommended)

1. **Create GitHub account** (if needed): https://github.com

2. **Create a new repository:**
   - Go to https://github.com/new
   - Name: `candle-warmer-site`
   - Make it private
   - Click "Create repository"

3. **Upload files:**
   - Click "uploading an existing file"
   - Drag all files from this folder
   - Commit changes

4. **Connect to Vercel:**
   - Go to https://vercel.com
   - Sign up with GitHub
   - Click "New Project"
   - Import your `candle-warmer-site` repository
   - Click "Deploy"

5. **Add custom domain:**
   - In your Vercel project, go to Settings → Domains
   - Add `bestcandlewarmers.co.uk`
   - Follow the DNS instructions

### Option B: Vercel CLI

```bash
# Install Vercel CLI
npm install -g vercel

# Navigate to project folder
cd candle-warmer-site

# Deploy
vercel

# Follow prompts to link to your account
```

---

## Step 6: Connect Domain to Vercel

At your domain registrar (Porkbun):

1. Go to Domain Management
2. Click DNS for your domain
3. Add a CNAME record:
   - **Type:** CNAME
   - **Host:** @ (or leave blank for root domain)
   - **Answer:** cname.vercel-dns.com
   - **TTL:** 600

For www subdomain, add another CNAME:
   - **Type:** CNAME
   - **Host:** www
   - **Answer:** cname.vercel-dns.com

**Wait 5-10 minutes** for DNS propagation and SSL certificate generation.

---

## Step 7: Post-Launch Tasks

### Submit to Google Search Console

1. Go to https://search.google.com/search-console
2. Add your domain
3. Verify ownership (use DNS verification)
4. Submit sitemap: `https://bestcandlewarmers.co.uk/sitemap.xml`

### Set Up Social Accounts

1. **Pinterest** (highest priority for home decor):
   - Create business account
   - Claim your website
   - Create boards: "Candle Warmers", "Home Fragrance", "Cosy Home Ideas"
   - Pin product images with affiliate links

2. **Instagram** (optional):
   - Create account @bestcandlewarmersuk
   - Share aesthetic candle photos
   - Link in bio to website

---

## File Structure

```
candle-warmer-site/
├── index.html           # Main page with all content
├── style.css            # All styling
├── privacy-policy.html  # Required for compliance
├── robots.txt           # Search engine instructions
├── sitemap.xml          # For Google Search Console
├── vercel.json          # Vercel deployment config
├── images/              # Product images (optional)
└── DEPLOYMENT-GUIDE.md  # This file
```

---

## Affiliate Link Reference

| Product | ASIN | Affiliate Link Template |
|---------|------|------------------------|
| Candeldo (Best Overall) | B0DP99C2ZC | amazon.co.uk/dp/B0DP99C2ZC?tag=YOURID-21 |
| GODONLIF (Most Popular) | B0FLXTHC3Z | amazon.co.uk/dp/B0FLXTHC3Z?tag=YOURID-21 |
| Candeldo Flower (Premium) | B0D7C1NDZH | amazon.co.uk/dp/B0D7C1NDZH?tag=YOURID-21 |
| Paryou (Mid-Range) | B0CY56ZHFP | amazon.co.uk/dp/B0CY56ZHFP?tag=YOURID-21 |
| spqment (Gifts) | B0F48NWHB9 | amazon.co.uk/dp/B0F48NWHB9?tag=YOURID-21 |
| QUIGO (Safety) | B0FF9258SR | amazon.co.uk/dp/B0FF9258SR?tag=YOURID-21 |
| Draome (Budget) | B0FGX2166D | amazon.co.uk/dp/B0FGX2166D?tag=YOURID-21 |

---

## Cost Summary

| Item | Cost | Notes |
|------|------|-------|
| Domain (bestcandlewarmers.co.uk) | ~£2.25/year | Porkbun first year |
| Hosting (Vercel) | £0 | Free tier |
| Analytics (GA4 + Clarity) | £0 | Free |
| Amazon Associates | £0 | Free to join |
| **Total Year 1** | **~£2.25** | |
| **Total Year 2+** | **~£5.50/year** | Domain renewal |

---

## Success Metrics

### Month 1 Targets
- Site indexed in Google
- 100+ organic visitors
- 10+ affiliate clicks
- 1-3 sales

### Month 3 Targets
- 500+ monthly visitors
- 50+ affiliate clicks
- 10-15 sales (~£30-50 commission)

### Month 6 Targets
- 2,000+ monthly visitors
- £100+/month potential

---

## Future Improvements

1. **Add product images** - Download Amazon product images or create simple graphics
2. **Add blog posts:**
   - "Candle Warmer vs Burning: Which is Better?"
   - "How to Use a Candle Warmer Lamp"
   - "Best Candles for Candle Warmers"
3. **Expand to more products** as new ones launch
4. **Consider TikTok** for demo videos
5. **Add Awin affiliate network** for more retailers (Wayfair, Very)

---

## Support

If you need help:
- Vercel docs: https://vercel.com/docs
- Amazon Associates help: https://affiliate-program.amazon.co.uk/help
- Google Analytics help: https://support.google.com/analytics

Good luck with your site! 🕯️
