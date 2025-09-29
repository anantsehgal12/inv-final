# Task: Apply Taxes on Taxable Amount Instead of Subtotal in Invoices

## Steps to Complete

### 1. Update Calculation Logic (Completed)
- [x] Modify `src/utils/calculations.ts` to calculate tax as flat 18% on taxable amount = (subtotal - discount) + additional charges.
- This ensures total = taxable amount + 18% tax.
- CGST/SGST split for same state, IGST otherwise.

### 2. Fix Invoice Preview Display (Pending)
- [ ] Edit `src/components/InvoicePreview.tsx` to correctly display "Taxable Amount" as (subtotal - discount + sum(additional charges)).
- Ensure tax rows use the stored `totalTax` (now flat 18%).

### 3. Update Form Calculations for Consistency (Pending)
- [ ] In `src/app/invoices/create/proforma/page.tsx` (and similar for regular invoices if needed):
  - Update useMemo to compute items without per-item tax (set taxAmount: 0, totalAmount: amount).
  - Ensure summary shows correct flat tax from `calculateInvoiceTotal`.
- [ ] In onSubmit, compute and save items without per-item tax.

### 4. Verify and Test (Pending)
- [ ] Run `npm run dev` and create a test proforma invoice with subtotal, discount, additional charges.
- [ ] Check preview: Taxable Amount should be post-discount + charges; taxes 18% of that; total correct.
- [ ] Confirm no errors in console or linter.

### 5. Handle Regular Invoices (If Applicable)
- [ ] Check if regular invoice creation page (`src/app/invoices/create/page.tsx`?) needs similar updates.
- [ ] Apply if it uses the same calculation logic.

### 6. Mark Complete
- [ ] Once verified, update this TODO.md with all [x] and use attempt_completion.
