Description: The KPI stat card pattern (icon + title + value + trend) is repeated inline across 3 pages with ~11 instances total. A reusable StatCard component would reduce duplication and ensure consistent styling.

Requirements:

Create components/shared/StatCard.tsx
Props: title, value (ReactNode), icon, trend?, trendLabel?, color? (amber/blue/emerald/purple), className?
Handle the gradient overlay, icon background, and trend display internally
Use the component in dashboard, settlement, and admin overview pages
Suggested execution steps:

Create components/shared/StatCard.tsx
Define the prop interface with all needed fields
Implement the card with gradient overlay, icon, value, and optional trend
Replace the 4 inline stat cards in app/(merchant)/dashboard/page.tsx
Replace the 3 stat cards in app/(merchant)/settlement/page.tsx
Replace the 4 stat cards in app/(admin)/overview/page.tsx
Verify all look identical to the original
Description: Mock data arrays are defined inline at the top of page files: mockChartData in dashboard, mockTransactions in dashboard, mockPaymentLinks in dashboard, mockLinks in payments, mockTxHistory in wallet, mockSettlements in settlement, mockKeys in developers. This clutters page files and makes it hard to swap mock data for real API data.

Requirements:

Create lib/mock/dashboard.ts, lib/mock/transactions.ts, lib/mock/paymentLinks.ts, lib/mock/wallet.ts, lib/mock/settlements.ts, lib/mock/developers.ts
Move all mock data arrays from page files to these dedicated files
Export them as named exports
Import them in the page files
Suggested execution steps:

Create the mock data files under lib/mock/
Move mockChartData, mockTransactions, mockPaymentLinks from app/(merchant)/dashboard/page.tsx
Move mockLinks from app/(merchant)/payments/page.tsx
Move mockTxHistory from app/(merchant)/wallet/page.tsx
Move mockSettlements from app/(merchant)/settlement/page.tsx
Move mockKeys and codeExample from app/(merchant)/developers/page.tsx
Move fxHistory and pairs from app/(merchant)/fx/page.tsx
Move mockChartData from app/(admin)/overview/page.tsx
Update all imports in page files
