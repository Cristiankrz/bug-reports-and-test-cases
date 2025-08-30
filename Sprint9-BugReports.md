# Sprint 9 – Selected Bug Reports (Urban Scooter Final Project)

## [P9-1] Web: Last Name Field Accepts >15 Characters Without Validation  
**Environment:**  
- Chrome 139 (1280×720), Opera 120 (1280×720)  
- Windows 10 Pro  
- Urban Scooter web app  

**Preconditions:** User is on the "Who the scooter is for" form.  

**Steps to Reproduce:**  
1. Open the order form.  
2. In the "Last Name" field, enter a string longer than 15 characters (e.g., `Alexandersonnnyy` = 16 chars).  
3. Fill in all other fields with valid data.  
4. Click **Next**.  

**Expected Result:**  
- Last Name field outlined in red.  
- Error message displayed: *"Enter a valid name"*.  
- User is blocked from proceeding to the Renting page.  

**Actual Result:**  
- No error message displayed.  
- Form is accepted and user is navigated to the Renting page.  

**Impact:** Weak validation allows invalid inputs to corrupt user data.  

---

## [P9-31] Mobile: No Push Notification at 9:59 PM for Order Due at 11:59 PM  
**Environment:**  
- Device: Android Emulator (Pixel profile), Android 14  
- Timezone: America/Chicago (CT)  
- App: Scooter client test build  
- Notifications: Enabled  

**Preconditions:**  
- Order exists with address `Elm St 77`, deliveryDate = today 11:59 PM.  
- App launched at least once after order creation.  

**Steps to Reproduce:**  
1. Confirm order is visible in **All orders**.  
2. Put the app in the background.  
3. Wait until **9:59 PM** local time.  
4. Check notification shade.  

**Expected Result:**  
Push notification arrives at 9:59 PM with:  
*“2 hours to the end of the order. The order ‘Elm St 77’ must be completed before time 11:59 PM…”*  

**Actual Result:**  
- No push notification arrives.  
- Address `Elm St 77` is not shown in a notification.  

**Impact:** Courier may miss deadlines → order delays and support issues.  

---

## [P9-14] API: [DELETE] /api/v1/courier/:id — Linked Orders Not Erased  
**Environment:**  
- Server: Urban Scooter API (Project 9 backend)  
- Tool: curl / Postman  
- OS: Mac & Windows 10 Pro tested  

**Steps to Reproduce:**  
1. Create courier (`POST /api/v1/courier`) → 201 Created.  
2. Login courier, capture ID.  
3. Create order, capture track number.  
4. Accept order with courier.  
5. Verify order shows `inDelivery: true`.  
6. Delete courier (`DELETE /api/v1/courier/:id`).  
7. Query order again (`GET /api/v1/orders/track?t=<track>`).  

**Expected Result:**  
- Linked orders erased on courier deletion.  
- Step 7 returns `404 Not Found`.  

**Actual Result:**  
- Step 7 still returns full order object (`inDelivery:true, status:1`).  
- Data integrity broken.  

**Impact:** Major severity. Deleting a courier should not leave orphaned orders in the system.  

---
