# Tenant member list search regression screenshots

These are synthetic-data screenshots from the existing component validation, not a new browser run at publication. The complete production TenantMembers.vue was rendered in Edge 156.0.4314.42 with real Vue, TDesign, Pinia and frontend request code. HTTP responses were intercepted and debounce timing was controlled. No company service or real Go backend was used.

- before.png: original source from 7f869198659eec5c5883be5c6b71fb3d38d7fae5. The input has changed to beta, but the late alpha response has populated the list before beta's debounce completes.
- after.png: reviewed source SHA256 553cf84609c45a26f91ed8b985b1b7e66ca9b098eb4b33ffb751fd639cf8d3b6. At the same point, the late alpha response is ignored and the list remains empty until beta's own query completes.

The final component validation passed 23 scenarios. Four original-source browser counterexamples failed as expected; these are not additional passing cases. Screenshots capture UI state; request-order assertions were checked separately by the harness.

Image SHA256:

- before.png: f528bc99efef73a2d308f07d114fe689b9ce72a060e32ce8a96f9d527f0e1159
- after.png: 5ce41cf7aaaf2fb58f9dc1ccdc60a0b1dd6622e3fae76cfea0ec273edff9ce31
