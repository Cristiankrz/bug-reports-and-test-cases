# Sprint 6 – Selected Bug Reports (Urban Lunch Mobile App)

## [S6-8] No Back Navigation from Dish List Screen to Change Pickup Point
- **Environment:** Pixel 5 Emulator, Android 12, Urban Lunch v1 (Project 6 APK), Android Studio  
- **Steps:**  
  1. Launch the Urban Lunch app  
  2. Select a pickup point on the map  
  3. Tap "Next" to proceed to the dish list screen  
  4. Look for a back button or navigation option  
- **Expected Result:**  
  A back arrow or navigation option is present to return to the pickup point screen before continuing.  
- **Actual Result:**  
  No back button is available. User is trapped on dish list screen unless app is restarted.  
- **Impact:**  
  - Breaks expected mobile navigation behavior  
  - Frustrates users who select wrong pickup point  
  - Poor UX; potential cause of app abandonment  

---

## [S6-9] [UI] Delivery Fee Not Displayed on Order Confirmation Screen
- **Environment:** Pixel 5 Emulator, Android 12, Urban Lunch v1 (Project 6 APK), Android Studio  
- **Steps:**  
  1. Launch the Urban Lunch app  
  2. Select a pickup point  
  3. Add one or more dishes to cart  
  4. Tap "Next" → proceed to Order Confirmation screen  
  5. Review cost breakdown  
- **Expected Result:**  
  Order Confirmation shows:  
  - Dish subtotal  
  - Delivery fee (listed separately)  
  - Final total = subtotal + delivery fee  
- **Actual Result:**  
  Only dish subtotal is shown. Delivery fee not displayed. Final total unclear.  
- **Impact:**  
  - Lacks pricing transparency  
  - Confuses users about charges  
  - Could lead to mistrust or abandoned orders  
