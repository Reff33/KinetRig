# /ui-ux <product_or_page_brief> [--stack <stack>]

Generate and apply a UI/UX Pro Max design system:

1. Run: `python rigtools/ui_ux_pro_max/scripts/search.py "<product_type> <industry> <keywords>" --design-system -p "<Project Name>" --persist --output-dir .`
2. If a tech stack applies, query stack guidelines: `python rigtools/ui_ux_pro_max/scripts/search.py "<keywords>" --stack <stack>`
3. Consult `rigtools/ui_ux_pro_max/references/quick-reference.md` and `rigtools/ui_ux_pro_max/references/pro-rules.md` for accessibility, contrast, and interaction polish.
4. Implement UI using only SVG icons (no OS emojis), verified color contrast, keyboard focus states, and responsive layout.
