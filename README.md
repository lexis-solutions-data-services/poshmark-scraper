# Poshmark Scraper

![Poshmark Scraper](https://i.ibb.co/SXsPXMsN/poshmark-cover.png)

This actor is designed to scrape **Poshmark** listing search results and product detail pages. It extracts structured data such as item metadata (title, description, price, original price, size, category, colors), images, seller information, and engagement metrics (likes, shares, comments) — ideal for resale analytics, market research, inventory ingestion, or price monitoring.

<p align="center">
  <img src="https://apify-image-uploads-prod.s3.us-east-1.amazonaws.com/DevbkY3adMTBuoECt-actor-LBvZkeC1mI2P3frpm-oCztZRWQDg-unnamed-7.png" alt="Poshmark.com Scraper" style="height: 60px; margin-right: 15px;" /><a href="https://apify.com/lexis-solutions/poshmark-scraper" target="_blank">
    <img src="https://img.shields.io/badge/Try%20it%20on-Apify-0066FF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDA4IiBoZWlnaHQ9IjQwOCIgdmlld0JveD0iMCAwIDQwOCA0MDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGNsaXAtcGF0aD0idXJsKCNjbGlwMF8zNDFfNDE1NykiPgo8cGF0aCBkPSJNMjE4LjY5NSAxMDRIMzAwLjk3QzMwMi42NDMgMTA0IDMwNCAxMDUuMzU3IDMwNCAxMDcuMDNWMjMyLjc2NkMzMDQgMjM1Ljc3OCAzMDAuMDgzIDIzNi45NDUgMjk4LjQzNCAyMzQuNDI1TDIxNi4xNTkgMTA4LjY5QzIxNC44NDEgMTA2LjY3NCAyMTYuMjg3IDEwNCAyMTguNjk1IDEwNFoiIGZpbGw9IndoaXRlIi8+CjxwYXRoIGQ9Ik0xODkuMzA1IDEwNEgxMDcuMDNDMTA1LjM1NyAxMDQgMTA0IDEwNS4zNTcgMTA0IDEwNy4wM1YyMzIuNzY2QzEwNCAyMzUuNzc4IDEwNy45MTcgMjM2Ljk0NSAxMDkuNTY2IDIzNC40MjVMMTkxLjg0IDEwOC42OUMxOTMuMTU5IDEwNi42NzQgMTkxLjcxMyAxMDQgMTg5LjMwNSAxMDRaIiBmaWxsPSJ3aGl0ZSIvPgo8cGF0aCBkPSJNMjAyLjU5MSAyMDQuNjY4TDEwOS4xMjcgMjk4LjgzNUMxMDcuMjI5IDMwMC43NDcgMTA4LjU4MyAzMDQgMTExLjI3OCAzMDRIMjk2LjhDMjk5LjQ4MyAzMDQgMzAwLjg0MiAzMDAuNzcgMjk4Ljk2NyAyOTguODUyTDIwNi45MDggMjA0LjY4NUMyMDUuNzI2IDIwMy40NzUgMjAzLjc4MiAyMDMuNDY4IDIwMi41OTEgMjA0LjY2OFoiIGZpbGw9IndoaXRlIi8+CjwvZz4KPGRlZnM+CjxjbGlwUGF0aCBpZD0iY2xpcDBfMzQxXzQxNTciPgo8cmVjdCB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCIgZmlsbD0id2hpdGUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEwNCAxMDQpIi8+CjwvY2xpcFBhdGg+CjwvZGVmcz4KPC9zdmc+Cg==&logoColor=white" alt="Try it on Apify" style="border-radius: 12px; height: 60px;" />
  </a>
</p>


---


## 📊 Actor Stats

| Stat | Value |
|------|-------|
| **Version** | `0.1.2` |
| **Last Update** | Nov 30, 2025 |

---


## ✅ Key Features

- Scrapes Poshmark **search results and product detail pages**
- Captures item details: **title, description, price, original price, size, category, colors**, and **images**
- Extracts seller info and engagement: **likes, shares, comments**, and timestamps
- Supports **custom search queries** and **direct listing URLs**
- Automatically handles **pagination**
- Outputs **structured JSON** suitable for databases or pipelines

---

## 🌍 Why Is This Actor Important?

Poshmark is one of the most popular social commerce platforms for fashion resale, but it doesn’t provide a public API for bulk access to listing data. This actor automates data collection in a reliable and scalable way, enabling users to track prices, monitor demand and engagement, analyze inventory, and power reseller or analytics workflows.

---

## 👤 Who Is This Actor Suitable For?

- **Resellers and inventory managers** sourcing or monitoring Poshmark listings
- **E-commerce analysts** comparing prices, engagement, and product attributes
- **Market researchers** studying resale trends and demand signals
- **Developers and data scientists** building ingestion, enrichment, or monitoring pipelines
- **Businesses** tracking competitors or pricing across marketplaces

---

## 📥 Input Schema

The actor expects a simple JSON input:

```json
{
  "startUrls": [
    {
      "url": "https://poshmark.com/search?query=hats&type=listings&src=dir"
    }
  ],
  "query": "hats",
  "maxItems": 20,
  "proxyConfiguration": {
    "useApifyProxy": true,
    "apifyProxyGroups": ["RESIDENTIAL"]
  }
}
```

---

## 📤 Output Schema

```json
{
  "id": "6875caa5a5bb34edbaea811c",
  "creator_id": "58ea886948e68a4b4711054d",
  "status": "published",
  "status_changed_at": "2025-08-26T13:25:20-07:00",
  "origin_domain": "us",
  "destination_domains": ["us"],
  "publish_count": 1321,
  "app": "web",
  "inventory": {
    "status": "available",
    "status_changed_at": "2025-07-14T20:27:33-07:00",
    "size_quantity_revision": 1,
    "size_quantities": [
      {
        "size_id": "OS",
        "quantity_available": 1,
        "quantity_reserved": 0,
        "quantity_sold": 0,
        "size_ref": 64,
        "size_system": "us",
        "size_obj": {
          "id": "OS",
          "display": "One Size",
          "display_with_size_set": "OS",
          "size_system": "us",
          "display_with_size_system": "US OS",
          "display_with_system_and_set": "US OS"
        },
        "size_set_tags": ["standard"]
      }
    ],
    "multi_item": false
  },
  "catalog": {
    "category_features": ["05009813d97b4e3995005764"],
    "category": "02008c10d97b4e1245005764",
    "department": "01008c10d97b4e1245005764",
    "department_obj": {
      "id": "01008c10d97b4e1245005764",
      "display": "Men",
      "slug": "Men",
      "message_id": "men"
    },
    "category_obj": {
      "id": "02008c10d97b4e1245005764",
      "display": "Accessories",
      "slug": "Accessories",
      "message_id": "men_accessories"
    },
    "category_feature_objs": [
      {
        "id": "05009813d97b4e3995005764",
        "display": "Hats",
        "slug": "Hats",
        "message_id": "men_accessories_hats"
      }
    ]
  },
  "catalog_source": "u",
  "inventory_unit_id": "6875caa5a5bb34edbaea811d",
  "updated_at": "2025-08-26T04:45:05-07:00",
  "colors": [],
  "category": "Other",
  "cover_shot": {
    "id": "6875caa6ed788d7f271b1aa6",
    "creator_id": "58ea886948e68a4b4711054d",
    "picture": "6875caa6ed788d7f271b1aa6.jpeg",
    "path": "posts/2025/07/14/6875caa5a5bb34edbaea811c/m_6875caa6ed788d7f271b1aa6.jpeg",
    "path_small": "posts/2025/07/14/6875caa5a5bb34edbaea811c/s_6875caa6ed788d7f271b1aa6.jpeg",
    "path_large": "posts/2025/07/14/6875caa5a5bb34edbaea811c/l_6875caa6ed788d7f271b1aa6.jpeg",
    "path_webp": "posts/2025/07/14/6875caa5a5bb34edbaea811c/m_wp_6875caa6ed788d7f271b1aa6.webp",
    "path_small_webp": "posts/2025/07/14/6875caa5a5bb34edbaea811c/s_wp_6875caa6ed788d7f271b1aa6.webp",
    "path_large_webp": "posts/2025/07/14/6875caa5a5bb34edbaea811c/l_wp_6875caa6ed788d7f271b1aa6.webp",
    "content_type": "image/jpeg",
    "storage_location": "or",
    "md5_hash": "799666559f24ee6e630eb818557488c4",
    "created_at": "2025-07-14T20:27:34-07:00",
    "url": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/m_6875caa6ed788d7f271b1aa6.jpeg",
    "url_small": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/s_6875caa6ed788d7f271b1aa6.jpeg",
    "url_large": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/l_6875caa6ed788d7f271b1aa6.jpeg",
    "url_webp": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/m_wp_6875caa6ed788d7f271b1aa6.webp",
    "url_small_webp": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/s_wp_6875caa6ed788d7f271b1aa6.webp",
    "url_large_webp": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/l_wp_6875caa6ed788d7f271b1aa6.webp",
    "content_type_alternate": "image/webp"
  },
  "description": "Henschel Halsey hat  Safari sun Hat Please see photos for details and conditions 23” circumference \nOpen to offers \nFast shipper \n12025-B",
  "original_price_amount": {
    "val": "0.0",
    "currency_code": "USD",
    "currency_symbol": "$"
  },
  "pictures": [
    {
      "id": "6875caa82fa054fcf1bf7b50",
      "creator_id": "58ea886948e68a4b4711054d",
      "picture": "6875caa82fa054fcf1bf7b50.jpeg",
      "path": "posts/2025/07/14/6875caa5a5bb34edbaea811c/m_6875caa82fa054fcf1bf7b50.jpeg",
      "path_small": "posts/2025/07/14/6875caa5a5bb34edbaea811c/s_6875caa82fa054fcf1bf7b50.jpeg",
      "path_large": "posts/2025/07/14/6875caa5a5bb34edbaea811c/l_6875caa82fa054fcf1bf7b50.jpeg",
      "path_webp": "posts/2025/07/14/6875caa5a5bb34edbaea811c/m_wp_6875caa82fa054fcf1bf7b50.webp",
      "path_small_webp": "posts/2025/07/14/6875caa5a5bb34edbaea811c/s_wp_6875caa82fa054fcf1bf7b50.webp",
      "path_large_webp": "posts/2025/07/14/6875caa5a5bb34edbaea811c/l_wp_6875caa82fa054fcf1bf7b50.webp",
      "content_type": "image/jpeg",
      "storage_location": "or",
      "md5_hash": "97fec9c12d5f5950b3cc50c7cc9c67e0",
      "created_at": "2025-07-14T20:27:36-07:00",
      "url": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/m_6875caa82fa054fcf1bf7b50.jpeg",
      "url_small": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/s_6875caa82fa054fcf1bf7b50.jpeg",
      "url_large": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/l_6875caa82fa054fcf1bf7b50.jpeg",
      "url_webp": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/m_wp_6875caa82fa054fcf1bf7b50.webp",
      "url_small_webp": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/s_wp_6875caa82fa054fcf1bf7b50.webp",
      "url_large_webp": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/l_wp_6875caa82fa054fcf1bf7b50.webp",
      "content_type_alternate": "image/webp"
    }
  ],
  "price_amount": {
    "val": "16.0",
    "currency_code": "USD",
    "currency_symbol": "$"
  },
  "size": "OS",
  "title": "Henschel Halsey hat  Safari sun Hat",
  "autolist_copy_detection_metadata": {
    "root_ancestor_post_id": "680cfafc6c0504ef59233fd5",
    "created_at": "2025-07-14T20:27:42-07:00",
    "algorithm": "covershot_md5hash"
  },
  "assigned_just_in_at": "2025-07-14T20:27:42-07:00",
  "brand_update_count": 0,
  "first_published_at": "2025-07-14T20:27:42-07:00",
  "first_available_at": "2025-07-14T20:27:42-07:00",
  "share_count": 83,
  "first_event_share": {
    "event_id": "6864c682d6c14e0bfbab5efb",
    "shared_at": "2025-07-15T19:30:34-07:00"
  },
  "like_count": 1,
  "post_like_page": 0,
  "has_offer": true,
  "created_at": "2025-07-14T20:27:33-07:00",
  "price": 16,
  "original_price": 0,
  "comment_count": 0,
  "active_buyer_offer_count": 0,
  "post_comment_page": 0,
  "post_event_page": 0,
  "post_event_host_shares_page": 0,
  "has_seller_offer": false,
  "videos": [],
  "generated_story_ids": [],
  "style_tags": [],
  "picture_url": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/m_6875caa6ed788d7f271b1aa6.jpeg",
  "aggregates": {
    "shares": 83,
    "comments": 0,
    "likes": 1,
    "active_buyer_offers": 0
  },
  "comments": [],
  "events": [],
  "event_host_shares": [],
  "likes": [
    {
      "user_id": "650c628d5280155b9d0591fa",
      "created_at": "2025-07-18T11:10:24-07:00",
      "creator_id": "650c628d5280155b9d0591fa",
      "id": "650c628d5280155b9d0591fa",
      "creator_username": "5134942",
      "creator_display_handle": "5134942",
      "creator_full_name": "513 4942",
      "creator_picture_url": "https://di2ponv0v5otw.cloudfront.net/users/2023/09/21/8/t_650c628e5280155b9d05925a.png"
    }
  ],
  "posh_pass_eligible": false,
  "creator_username": "corinesandifer",
  "creator_display_handle": "corinesandifer",
  "creator_full_name": "Corine Sandifer",
  "creator_picture_url": "https://di2ponv0v5otw.cloudfront.net/users/2022/11/27/12/t_6383cbb5c6fd89ab9fd3c6ee.jpg",
  "department": {
    "id": "01008c10d97b4e1245005764",
    "display": "Men",
    "slug": "Men",
    "message_id": "men"
  },
  "category_v2": {
    "id": "02008c10d97b4e1245005764",
    "display": "Accessories",
    "slug": "Accessories",
    "message_id": "men_accessories"
  },
  "category_features": [
    {
      "id": "05009813d97b4e3995005764",
      "display": "Hats",
      "slug": "Hats",
      "message_id": "men_accessories_hats"
    }
  ],
  "size_obj": {
    "id": "OS",
    "display": "One Size",
    "display_with_size_set": "OS",
    "size_system": "us",
    "display_with_size_system": "US OS",
    "display_with_system_and_set": "US OS"
  },
  "shipping_discount_type": null,
  "system_messages": [],
  "trace_id": "68ae18517cd339a19eefb049",
  "url": "https://poshmark.com/listing/Henschel-Halsey-hat-Safari-sun-Hat-6875caa5a5bb34edbaea811c",
  "mainImageUrl": "https://di2ponv0v5otw.cloudfront.net/posts/2025/07/14/6875caa5a5bb34edbaea811c/m_6875caa6ed788d7f271b1aa6.jpeg"
}
```

👀 p.s.

Got feedback or need an extension?

Lexis Solutions is a [certified Apify Partner](https://apify.com/partners/find). We can help you with custom solutions or data extraction projects.

Contact us over [Email](mailto:scraping@lexis.solutions) or [LinkedIn](https://www.linkedin.com/company/lexis-solutions)

## Support Our Work 💝

If you're happy with our work and scrapers, you're welcome to leave us a company review [here](https://apify.com/partners/find/lexis-solutions/review) and leave a review for the scrapers you're subscribed to. It will take you less than a minute but it will mean a lot to us!

Image Credit: https://poshmark.com
