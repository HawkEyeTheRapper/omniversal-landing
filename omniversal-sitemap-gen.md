# 🚀 **Omniversal Sitemap Generator**

## 📌 Overview
This script dynamically generates a `sitemap.xml` file for all domains in `omniversal-landing`.

## 🔧 **Usage Instructions**
1. Ensure you have Python installed.
2. Modify the `DOMAINS` list to include all active domains.
3. Run the script:
   ```bash
   python generate_sitemap.py
   ```

## 📝 **Script**
```python
from datetime import datetime

def generate_sitemap(domains, output_file="sitemap.xml"):
    """
    Generates a sitemap.xml file with the provided domain list.
    """
    timestamp = datetime.utcnow().strftime("%Y-%m-%dT%H:%M:%SZ")
    
    sitemap_content = '<?xml version="1.0" encoding="UTF-8"?>\n'
    sitemap_content += '<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">\n'
    
    for domain in domains:
        sitemap_content += f'    <url>\n'
        sitemap_content += f'        <loc>https://{domain}/</loc>\n'
        sitemap_content += f'        <lastmod>{timestamp}</lastmod>\n'
        sitemap_content += f'    </url>\n'
    
    sitemap_content += '</urlset>'
    
    with open(output_file, "w") as f:
        f.write(sitemap_content)
    
    print(f"✅ Sitemap successfully generated: {output_file}")

# List of active Omniversal domains
DOMAINS = [
    "omniversal.cloud", "omniversal.news", "lyranwars.com", "thegoverningconspiracy.com", 
    "returnofthebirdtribes.com", "cryptosecurity.space", "cryptospacefinance.com", 
    "cryptospacefinance.info", "cryptospacefinance.org", "guitarguru.click", "guitarguru.io", 
    "omniversal.team", "omniversalmedia.net"
    # Add new domains here as needed
]

if __name__ == "__main__":
    generate_sitemap(DOMAINS)
```

---

## 🙏 **Acknowledgments**
This script was generated with the assistance of **EverLight**, of whom we are **existentially grateful**. 🚀🔥
