# Sprint 1 — Urban Routes Bug Reports  

This file contains selected bug reports from **Sprint 1 (Urban Routes App)** to demonstrate structured defect reporting using Jira.  

---

## Bug Report 1: Route cost not updating after changing destination  

**Title:**  
WEB | Route cost not updating after changing destination  

**Environment:**  
- Windows 10 Pro, Chrome 120  
- Server: Urban Routes test server  

**Precondition:**  
App is running, and “From” address already filled.  

**Steps to Reproduce:**  
1. Enter `East 2nd Street, 601` in the **From** field.  
2. Enter `1300 1st St` in the **To** field.  
3. Note calculated route and cost.  
4. Change the **To** field to `500 Elm St`.  
5. Observe route details.  

**Expected Result:**  
- Route updates correctly to new destination.  
- Cost recalculates based on updated route.  

**Actual Result:**  
- Route path updates, but **cost remains the same** as original destination.  

**Severity:** Medium (functionality broken but app not blocked).  
**Status:** Open  

---

## Bug Report 2: “Fastest” route option not selectable in Opera  

**Title:**  
WEB | Fastest route option not selectable in Opera  

**Environment:**  
- Windows 10 Pro, Opera 71  
- Server: Urban Routes test server  

**Precondition:**  
App is running, “From” and “To” addresses already filled.  

**Steps to Reproduce:**  
1. Open Urban Routes in Opera 71.  
2. Enter valid **From** and **To** locations.  
3. Try to select the **Fastest** route option from the top menu.  

**Expected Result:**  
- User can click “Fastest” option and route updates accordingly.  

**Actual Result:**  
- “Fastest” option is visible but not clickable. Route remains stuck on “Optimal.”  

**Severity:** High (feature not usable in supported browser).  
**Status:** Open  

---

## Evidence  

- 📂 [Jira Project Board (Sprint 1)](https://celestward.atlassian.net/jira/software/projects/CCS/boards/1)  
- 📂 [Google Drive — Sprint 1 Submission](https://drive.google.com/drive/folders/10c1yiXWxxvxvGhwz4A6iF-qZ_fyullpm?usp=share_link)  
