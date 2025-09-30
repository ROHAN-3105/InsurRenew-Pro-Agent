{
  "customer_name": "Riya Sharma",
  // String: The customer's full name.

  "customer_contact": "+91-90000-00000",
  // String: The customer's mobile number.

  "policy_number": "AB123456789",
  // String: The unique policy identifier.

  "policy_type": "Motor Comprehensive",
  // String: The name of the insurance product.

  "insurer_name": "Sample Insurance Co.",
  // String: Your company's official name.

  "asset_details": {
    // Object: Contains details of the insured asset.
    "make": "Maruti",                 // String
    "model": "Baleno",                // String
    "year": 2021,                     // Number
    "registration_number": "KA01AB1234" // String
  },

  "coverage_summary": [
    // Array of Strings: A concise list of the main policy benefits.
    "OD",
    "Third Party",
    "PA cover"
  ],

  "expiry_date": "2025-10-15",
  // String (YYYY-MM-DD): The policy's expiration date.

  "premium_amount": 12999,
  // Number: The base renewal cost.

  "no_claim_bonus_percent": 25,
  // Number: The No Claim Bonus value without the '%' symbol.

  "eligible_upsell": [
    // Array of Strings: List of add-ons the customer can buy. Can be an empty array if none.
    "Zero Depreciation"
  ],

  "upsell_premium_amount": 14499,
  // Optional, Number: The new total premium after the upsell is added.

  "callback_date": "2025-10-03T18:30:00Z"
  // Optional, String (ISO 8601 Format): The date and time requested for a callback.
}