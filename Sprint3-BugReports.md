# Sprint 3 — Bug Report (Urban Routes: DevTools & Complex Features)

**ID:** P3-13  
**Title:** [WEB] CVV with Mixed Alphanumeric Input Not Rejected  

**Status:** To Do  
**Priority:** Medium  
**Type:** Improvement  
**Reporter:** Celest Rios Ward  
**Assignee:** Unassigned  

---

### Description  
When a user enters a CVV with mixed alphanumeric input (e.g., `A1`) and submits the form, the system does not reject the input or display an error message.  
The system should **only accept numeric values** for the CVV and reject any alphanumeric input.  

---

### Environment  
- Device: Microsoft Windows 10 Pro  
- OS: Windows 10 Pro  
- Browser: Chrome (latest version)  
- Website: TripleTen Payment Page  

---

### Preconditions  
- The payment page is open  
- No other actions have been taken  

---

### Steps to Reproduce  
1. Open the payment page  
2. Enter a CVV with mixed alphanumeric input (e.g., `A1`)  
3. Click **Submit**  

---

### Expected Result  
The system should reject the CVV and display an error message:  
> "CVV must be numeric."  

---

### Actual Result  
- The system did not reject the alphanumeric CVV  
- No error message displayed  
- The form proceeded  
