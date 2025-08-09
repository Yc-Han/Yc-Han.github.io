# Two Sites in One Repository

Your website is now split into two distinct experiences while remaining in a single GitHub Pages repository.

## Structure

### Homepage (/)
- Minimal gateway page with split-screen design
- Visitors choose between Academic or Culture sections
- Each side expands on hover for visual feedback

### Academic Site (/academic/)
- Self-contained academic portfolio
- Internal navigation: CV, Publications, Teaching, Blog, GitHub
- Cross-link to Culture site in top-right corner
- Can be shared directly as: `yourdomain.com/academic/`

### Culture Site (/culture/)
- Self-contained cultural portfolio
- Internal navigation: Tea Ceremony, Essays
- Cross-link to Academic site in top-right corner
- Can be shared directly as: `yourdomain.com/culture/`

## Usage Scenarios

### For Academic Applications
Share: `https://yourdomain.com/academic/`
- PIs and academic contacts see only your research work
- Clean, professional presentation without cultural content

### For Personal/Cultural Sharing
Share: `https://yourdomain.com/culture/`
- Focus on cultural interests and creative work
- No academic content unless visitor explicitly navigates there

### For General Networking
Share: `https://yourdomain.com/`
- Visitors see both sides and choose their interest
- Shows the full breadth of your work

## Future Enhancement: Subdomains

If you want true separation with different URLs:

1. **Set up DNS records:**
   - CNAME: `academic.yourdomain.com` → `username.github.io`
   - CNAME: `culture.yourdomain.com` → `username.github.io`

2. **Activate the redirect script:**
   - Edit `_pages/about.md`
   - Uncomment the JavaScript redirect code (lines 13-19)
   - This will automatically redirect subdomain visitors to their respective sections

3. **Result:**
   - `academic.yourdomain.com` → shows `/academic/` content
   - `culture.yourdomain.com` → shows `/culture/` content
   - `yourdomain.com` → shows the gateway choice page

## Navigation Flow

```
Home (/) 
  ├── Academic (/academic/)
  │     ├── CV
  │     ├── Research Interests
  │     ├── Publications
  │     ├── Teaching
  │     ├── Consulting
  │     ├── Blog
  │     └── → Culture (cross-link)
  │
  └── Culture (/culture/)
        ├── Tea Ceremony
        ├── Essays
        └── → Academic (cross-link)
```

## Maintenance

- Each section maintains its own hero/intro section
- Shared CSS variables ensure consistent theming
- Cross-links allow navigation between "sites" when desired
- Main navigation bar provides fallback to home

This structure gives you the flexibility to present yourself differently to different audiences while maintaining a single, manageable codebase.
