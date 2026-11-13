# gsc-regex-filters# 🔍 Google Search Console (GSC) Regex Filter Library

A curated collection of copy-pasteable Regular Expressions (Regex) for **Google Search Console**. 

Use these filters inside the **Performance > Search Results** report (`+ New > Query > Custom (regex)`) to uncover hidden long-tail opportunities, diagnose cannibalization, isolate AI-triggering informational queries, and clean up noisy brand data.

> 💡 **Pro Tip:** GSC uses **RE2 syntax** and matches partial strings by default unless you anchor them with `^` (start) and `$` (end). All filters below are tested and ready for RE2.

---

## 📋 Table of Contents
* [1. High-Intent Question & Informational Queries](#1-high-intent-question--informational-queries)
* [2. Commercial & Bottom-of-Funnel (BoFu) Intent](#2-commercial--bottom-of-funnel-bofu-intent)
* [3. Long-Tail Keyword Discovery (By Word Count)](#3-long-tail-keyword-discovery-by-word-count)
* [4. Brand & Misspelling Isolation](#4-brand--misspelling-isolation)
* [5. Technical & URL Troubleshooting](#5-technical--url-troubleshooting)

---

## 1. High-Intent Question & Informational Queries
Find exact questions users ask before clicking. Ideal for building FAQ schema, glossary hubs, and capturing **AI Overview** citations.

* **All Standard Questions (Starts with Who, What, Where, When, Why, How):**
  ```regex
  ^(who|what|where|when|why|how)\b
  ```

* **Deep Problem-Solving & Troubleshooting Queries:**
  ```regex
  \b(how to|fix|error|issue|broken|not working|guide|tutorial|step by step)\b
  ```

* **AI-Triggering Definition & Concept Queries:**
  ```regex
  ^(what is|what are|define|meaning of|difference between|examples of)\b
  ```

---

## 2. Commercial & Bottom-of-Funnel (BoFu) Intent
Isolate users who are actively comparing tools, checking pricing, or ready to buy.

* **Comparison & Alternative Searches:**
  ```regex
  \b(vs|versus|or|alternative|alternatives|compare|comparison|better than)\b
  ```

* **Pricing, Reviews & Purchase Intent:**
  ```regex
  \b(price|pricing|cost|cheap|free|trial|demo|review|reviews|best|top)\b
  ```

* **Local & Service-Based Intent:**
  ```regex
  \b(near me|agency|consultant|service|services|company|hire|for hire)\b
  ```

---

## 3. Long-Tail Keyword Discovery (By Word Count)
Filter out broad head terms to find specific, low-competition phrases that are easy to rank for quickly.

* **Queries with 5 or More Words:**
  ```regex
  ^([^” “]*\s){4,}[^” “]*\$
  ```

* **Queries with 7 or More Words (Ultra-Specific):**
  ```regex
  ^([^” “]*\s){6,}[^” “]*\$
  ```

* **Single-Word Head Terms Only:**
  ```regex
  ^[^\s]+\$
  ```

---

## 4. Brand & Misspelling Isolation
Separate branded traffic from true non-branded organic growth. *(Replace `yourbrand` with your actual company name).*

* **Capture Brand Variations & Common Typos:**
  ```regex
  .*(yourbrand|your brand|yurbrand|yourbrnd).*
  ```
  *(Note: Select **"Does not match regex"** in GSC to strip out all branded searches and view pure non-branded performance).*

---

## 5. Technical & URL Troubleshooting
Apply these under **`+ New > Page > Custom (regex)`** to audit specific site sections.

* **Find Indexed Parameter / Faceted URLs (Crawl Bloat Check):**
  ```regex
  .*\?(sort|filter|page|tag|utm_|ref|session)=.*
  ```

* **Isolate Non-HTTPS or Subdomain Leaks:**
  ```regex
  ^http://|^(https://)(?!www\.yourdomain\.com).*
  ```

---

## 🤝 Contributing & Feedback
Have a favorite RE2 filter for Search Console that isn't listed here? Feel free to open an **Issue** or start a **Discussion** tab thread to share it!

---

### 👨‍💻 Maintained by Warner Williams
I help SaaS founders, e-commerce stores, and engineering teams turn fast web architectures into compounding organic search traffic.
* 🌐 **Website & Technical SEO Audits:** https://aprilpad.com/
* 💼 **Connect on LinkedIn:** 
