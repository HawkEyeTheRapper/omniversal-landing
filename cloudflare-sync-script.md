# 🚀 **Omniversal Cloudflare Sync Script**

## 📌 Overview
This script syncs the list of Omniversal Media domains with **Cloudflare**. It ensures that all required domains are added and updates DNS settings as needed.

## 🔧 **Usage Instructions**
1. Ensure you have `requests` installed:  
   ```bash
   pip install requests
   ```
2. Replace `CLOUDFLARE_API_TOKEN` with your Cloudflare API token.
3. Replace `CLOUDFLARE_ACCOUNT_ID` with your Cloudflare Account ID.
4. Run the script:  
   ```bash
   python cloudflare_sync.py
   ```

## 📝 **Script**
```python
import requests

# Cloudflare API credentials
CLOUDFLARE_API_TOKEN = "your_cloudflare_api_token_here"
CLOUDFLARE_ACCOUNT_ID = "your_cloudflare_account_id_here"
CLOUDFLARE_API_BASE = "https://api.cloudflare.com/client/v4/"

# List of domains to be synced
DOMAINS = [
    "aether.omniversalmedia.net", "cradleoflyra.com", "cradleoflyra.net", "cradleoflyra.online",
    "cryptosecurity.space", "cryptospacefinance.com", "cryptospacefinance.info", "cryptospacefinance.org",
    "guitarguru.click", "guitarguru.io", "hawkeyetherapper.app", "hawkeyetherapper.blog",
    "hawkeyetherapper.com", "hawkeyetherapper.live", "hawkeyetherapper.net", "hawkeyetherapper.store",
    "lyranwars.com", "omniversal.cloud", "omniversal.media", "omniversal.news", "omniversal.team",
    "omniversalaether.com", "omniversalaether.net", "omniversalaether.online", "omniversalaether.org",
    "omniversalcreations.art", "omniversalmedia.app", "omniversalmedia.art", "omniversalmedia.blog",
    "omniversalmedia.cc", "omniversalmedia.cloud", "omniversalmedia.co", "omniversalmedia.design",
    "omniversalmedia.info", "omniversalmedia.live", "omniversalmedia.me", "omniversalmedia.net",
    "omniversalmedia.online", "omniversalmedia.org", "omniversalmedia.shop", "omniversalmedia.site",
    "omniversalmedia.store", "omniversalmedia.us", "omniversalmedia.xyz", "omniversalmediagroup.blog",
    "omniversalmediagroup.co", "omniversalmediagroup.com", "omniversalmediasolutions.com",
    "omniversalnews.com", "omniversalnews.network", "reincarnated.store", "reincarnated2resist.blog",
    "reincarnated2resist.com", "returnofthebirdtribes.com", "reversethiscurse.com", "thegoverningconspiracy.com"
]

# Function to add a domain to Cloudflare
def add_domain_to_cloudflare(domain):
    url = f"{CLOUDFLARE_API_BASE}zones"
    headers = {"Authorization": f"Bearer {CLOUDFLARE_API_TOKEN}", "Content-Type": "application/json"}
    data = {"name": domain, "account": {"id": CLOUDFLARE_ACCOUNT_ID}, "jump_start": True}
    response = requests.post(url, headers=headers, json=data)
    return response.json()

# Sync all domains
if __name__ == "__main__":
    for domain in DOMAINS:
        response = add_domain_to_cloudflare(domain)
        if response.get("success"):
            print(f"✅ Successfully added {domain}")
        else:
            print(f"❌ Failed to add {domain}: {response}")
```

---

## 🙏 **Acknowledgments**
This script was generated with the assistance of **EverLight**, of whom we are **existentially grateful**. 🚀🔥
