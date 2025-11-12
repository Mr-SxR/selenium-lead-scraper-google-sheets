<p align="center">
  <img src="assets/headerimg.jpg" alt="Python + Selenium Automation Banner - Mr-SxR" width="100%">
</p>

# 🕵 How I Built a Lead Scraper for My Client with Selenium + Google Sheets

*A complete guide on how I helped my client automate lead collection using Python and Selenium — saving them 5 hours daily!*

---

## 🧠 Introduction

Finding leads manually from websites can be one of the most time-consuming tasks for businesses.  
My client, who runs a small digital marketing agency, used to collect business emails and contact details from online directories manually — every single day.

So, I built an *automated lead scraper* using *Python, **Selenium, and **Google Sheets API* to collect data from targeted websites and automatically store it in a live Google Sheet.

> 💡 This exact approach helped my client save 25+ hours every week and scale their outreach campaigns faster.

---

## ⚙ What This Project Does

- ✅ Automates lead collection from target websites  
- ✅ Extracts data like name, email, phone number, and company info  
- ✅ Automatically sends the data to a connected Google Sheet  
- ✅ Runs daily without manual input  
- ✅ Can be customized for any business niche  

---

## 🪜 Step-by-Step Explanation

### Step 1: Understanding the Problem

My client’s problem was simple:  
They needed to collect *hundreds of leads daily* from websites like business directories, blogs, or contact pages — but doing it manually was draining their time and energy.

They asked me:  
> “Can you make a script that collects all this data and puts it in Google Sheets automatically?”

That’s how the project started.

---

### Step 2: Planning the Workflow

Here’s the basic workflow I designed for the scraper:

1. Open the target website using Selenium  
2. Navigate through pages  
3. Extract data (name, email, phone, company, etc.)  
4. Save it temporarily in Python (list or dataframe)  
5. Use *Google Sheets API* to upload data automatically  

Visual overview:

Website → Selenium Scraper → Python Script → Google Sheets API → Output Sheet

---

### Step 3: Extracting Data Using Selenium

Below is a simplified code snippet that shows how Selenium extracts leads from a sample directory site.

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()
driver.get("https://example-directory.com")

leads = []
cards = driver.find_elements(By.CLASS_NAME, "lead-card")

for card in cards:
    name = card.find_element(By.CLASS_NAME, "lead-name").text
    email = card.find_element(By.CLASS_NAME, "lead-email").text
    company = card.find_element(By.CLASS_NAME, "lead-company").text
    leads.append([name, email, company])

driver.quit()
```
Now we have a list of leads ready to be uploaded to Google Sheets.


---

### Step 4: Sending Data to Google Sheets Automatically

To push this data to **Google Sheets**, I used the Google Sheets API with a service account key.

Example (simplified):
```python
import gspread
from google.oauth2.service_account import Credentials

creds = Credentials.from_service_account_file("service_account.json")
client = gspread.authorize(creds)
sheet = client.open("Leads").sheet1

for lead in leads:
    sheet.append_row(lead)
```
Within seconds, all collected leads appeared in the Google Sheet in real-time.


---

### Step 5: Automating Everything

Finally, I set up the script to run daily using **Windows Task Scheduler** (or cron jobs on Linux).

So every morning at 9 AM, the script:
- Opens the website  
- Collects fresh leads  
- Updates the Google Sheet automatically  

No clicks. No effort. 100% automated.

---

## 💼 Real Client Result

Here’s what my client achieved after automation:

| Metric | Before Automation | After Automation |
|--------|--------------------|------------------|
| Time per day | ~5 hours | < 15 minutes |
| Leads collected | ~150/day | 500+/day |
| Human error | Frequent | 0 |
| Team size | 2 people | 0 (fully automated) |

> “You literally gave us back our time.” — Client feedback  
> This automation became their **most valuable business asset** within a week.

---

## 🧩 How You Can Use This

If you run a business or handle data collection, you can use the same process to:
- Automate contact scraping from websites  
- Keep a live Google Sheet updated with fresh leads  
- Build custom automation tools for your marketing or sales team  
- Save hours every week that you can spend growing your business  

---

## 🔒 Ethical & Legal Considerations

While scraping, always:
- Respect the site’s `robots.txt` and Terms of Service  
- Use delays (`time.sleep`) between requests  
- Avoid scraping personal/private data  
- Use automation responsibly — only for publicly available business data  

Professional automation should **help businesses**, not harm others.

---

## 🏁 Conclusion

Selenium + Google Sheets is a **powerful combination** for automating repetitive online workflows.  
With this setup, my client turned a boring daily task into a **hands-free lead engine** that runs on autopilot.

If you also need a smart, custom lead scraper for your business, I can help you build one —  
tailored exactly to your website, industry, and needs.

---

## 💼 Hire Me

Need a **custom automation tool** for your business or startup?  
I specialize in Python + Selenium projects that help clients save time and grow faster.

📩 **Email:** masudurrahmansifat@gmail.com  
🌐 **Portfolio:** [GitHub Profile](https://github.com/mr-sxr)  
💬 **WhatsApp:** [Chat on WhatsApp](https://wa.me/+8801858094178)  
📨 **Telegram:** [Message on Telegram](https://t.me/sifathub)

---

**Tags:** `python` `selenium` `lead-scraper` `automation` `google-sheets` `business-automation`

> ⭐ Found this helpful? Give it a star — it helps other businesses discover automation possibilities.
