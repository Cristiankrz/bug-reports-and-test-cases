# Sprint 4 — Bug Report (Urban Grocers API: Kits & Deliveries)

**ID:** P4-16  
**Title:** [API] POST `/api/v1/kits/:id/products` – 500 Internal Server Error when Decimal Quantity is Sent Instead of 400 Bad Request  

**Status:** To Do  
**Priority:** Medium  
**Type:** Bug  
**Reporter:** Celest Rios Ward  
**Assignee:** Unassigned  

---

### Description  
When attempting to add a product to a kit using a **decimal number** for the `quantity` field, the system crashes and returns a **500 Internal Server Error**.  
The system should instead validate the input and return a **400 Bad Request**, indicating that the decimal value is invalid for a quantity field that expects integers.  

---

### Environment  
- Device: Windows 10 Pro  
- Tool: Postman  
- Workspace: My Workspace  
- Test Environment: TripleTen API  
- Endpoint:
POST https://cnt-368e3c7e-ae17-4415-be6b-44b46dfaa4af.containerhub.tripleten-services.com/api/v1/kits/4/products


---

### Preconditions  
- Existing kit with ID = 2  
- Existing product with ID = 3  

---

### Steps to Reproduce  
1. Open Postman and select a **POST** request to `/api/v1/kits/:id/products`  
2. Use the following request body:  
 ```json
 {
   "productsList": [
     { "id": 3, "quantity": 2.5 }
   ]
 }
--------

# Sprint 4 — Bug Report (Urban Grocers API: Fast Delivery XML)

**ID:** P4-28  
**Title:** [API] POST `/fast-delivery/v3.1.1/calculate-delivery.xml` – System Allows Delivery When `productsCount = 0` (200 OK)  

**Status:** To Do  
**Priority:** Medium  
**Type:** Bug  
**Reporter:** Celest Rios Ward  
**Assignee:** Unassigned  

---

### Description  
When sending a valid request where `productsCount = 0`, the system returns a **200 OK** response with `isItPossibleToDeliver = true` and includes a valid delivery window.  
Logically, delivering zero products should not be possible. The system should either reject the request or return `isItPossibleToDeliver = false`.  

---

### Environment  
- Device: Windows 10 Pro  
- Tool: Postman  
- Workspace: My Workspace  
- Test Environment: TripleTen API  
- Endpoint:  
POST https://cnt-87d63573-9bd4-4c15-aca6-000271250f15.containerhub.tripleten-services.com/fast-delivery/v3.1.1/calculate-delivery.xml

---

### Preconditions  
- Delivery service: Fast Delivery enabled  
- Endpoint is functional and accessible  

---

### Steps to Reproduce  
1. Send a **POST** request to `/fast-delivery/v3.1.1/calculate-delivery.xml`  
2. Use the following XML body:  
 ```xml
 <InputModel>
   <productsCount>0</productsCount>
   <productsWeight>2.5</productsWeight>
   <deliveryTime>10</deliveryTime>
 </InputModel>
