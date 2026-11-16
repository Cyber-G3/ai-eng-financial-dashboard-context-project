---
name: dashboard-chart-review
description: Review the financial dashboard's monthly Recharts visuals and their accessible data alternatives.
---

# Dashboard chart review

## Goal

Check that each financial chart accurately presents the monthly data already calculated by the frontend and remains understandable without sight or a pointer.

## When to use

Use before changing a dashboard chart, its loading or empty state, chart labels, or the monthly data passed into it.

## Inspect first

- `frontend/src/App.tsx` for the `/api/metrics` request and the path into chart components.
- `frontend/src/lib/financial-types.ts` and `frontend/src/lib/financial-utils.ts` for the monthly data shape and current calculations.
- `frontend/src/components/dashboard/income-outcome-chart.tsx` and `profit-percent-chart.tsx` for chart labels, accessible alternatives, loading, and empty states.
- `frontend/src/index.css` and `frontend/src/components/ui/skeleton.tsx` for chart styling and loading motion.
- `frontend/package.json` for documented frontend commands.

## Steps

1. Trace the monthly values from `App.tsx` through `computeMonthlyData`; preserve existing formulas, ordering, currency, and labels unless requirements or tests define a change.
2. For each chart, compare its series keys and visible labels with the `MonthlyDataPoint` fields actually passed to it.
3. Confirm the chart has an accessible name, Recharts keyboard accessibility is enabled, and a screen-reader-readable table contains the same months and values.
4. Check that the visible empty state and the table remain truthful when data is empty or all values are zero.
5. Check that loading placeholders reserve the chart's rendered height and that reduced-motion preferences are respected.
6. If a chart or data change is required, keep it local to the existing chart or utility layer. Do not change the financial meaning to satisfy a presentation preference.

## Expected result

Return a short review with the files inspected, any mismatches found, the smallest supported changes, and checks actually completed.

## Acceptance criteria

- Each rendered chart's series, visible title, accessible name, and alternative table describe the same fields.
- The chart remains keyboard reachable through Recharts' accessibility layer; no new pointer-only interaction is introduced.
- Empty, loading, and error content does not claim values that are absent from the API result.
- No financial formula or data provenance claim changes without repository evidence or an explicit product decision.
- Any required production build uses the repository script `cd frontend && npm run build`; the documented local app command is `cd frontend && npm run dev`.
