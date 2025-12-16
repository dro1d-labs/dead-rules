# Rule Sources & Attribution

De-Ad uses a curated combination of well-maintained public blocklists and custom refinements optimized for Safari on iOS.

## Upstream Sources

### 1. Peter Lowe's Ad & Tracking Server List
**Source:** [https://pgl.yoyo.org/adservers/](https://pgl.yoyo.org/adservers/)  
**License:** Public Domain  
**Coverage:** ~2,800 well-known ad servers  
**Why we use it:** Conservative, stable, minimal false positives

### 2. AdAway Hosts
**Source:** [https://adaway.org/](https://adaway.org/)  
**License:** CC BY 3.0  
**Coverage:** ~10,000+ mobile-focused ad domains  
**Why we use it:** Mobile-first approach, good regional coverage

### 3. EasyPrivacy (Subset)
**Source:** [https://easylist.to/](https://easylist.to/)  
**License:** GPL v3 / CC BY-SA 3.0  
**Coverage:** ~5,000 tracking scripts (curated subset)  
**Why we use it:** Industry-standard privacy filter list

### 4. dro1d labs Custom Rules
**Source:** Curated internally  
**License:** MIT (this repository)  
**Coverage:** 
- Cookie consent banners & GDPR popups
- Social media tracking pixels
- Analytics scripts not covered by upstream
- Regional ad networks (IE, UK, EU focus)

## Processing Pipeline
1. **Download** upstream sources (monthly)
2. **Merge** and deduplicate domains
3. **Convert** to Safari Content Blocker JSON format
4. **Validate** against Safari rule limits (~150k max)
5. **Test** on major websites for false positives
6. **Bundle** with De-Ad iOS app

## Rule Format
Safari Content Blocker JSON with two action types:
- `block` – Prevent resource from loading
- `css-display-none` – Hide elements (cookie banners, etc.)

## Update Schedule
Rules are updated monthly and ship with De-Ad app updates via the App Store.

## Contributing
Found a false positive? Site not working?  
Email: [support@dro1d.org](mailto:support@dro1d.org)

## No Paid Exceptions
De-Ad has zero "acceptable ads" programs.  
No paid whitelists. No secret exceptions.  
If it's in the blocklist, it's blocked.