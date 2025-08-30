# Sprint 4 – Selected Bug Reports (Urban Grocers API)

## [P4-16] POST /api/v1/kits/:id/products – 500 Internal Server Error (Quantity Decimal)
- **Environment:** Windows 10, Postman, TripleTen API
- **Steps:** Sent POST with `quantity = 2.5`
- **Expected:** 400 Bad Request (invalid decimal input)
- **Actual:** 500 Internal Server Error
- **Impact:** Server fails to handle invalid input gracefully

---

## [P4-28] POST /fast-delivery/v3.1.1/calculate-delivery.xml – Allows Delivery When productCount = 0
- **Environment:** Windows 10, Postman, TripleTen API
- **Steps:** Sent XML body with `productsCount = 0`
- **Expected:** Reject request or return `isItPossibleToDeliver = false`
- **Actual:** 200 OK with delivery allowed
- **Impact:** Business logic broken, deliveries possible with zero items
