# 2026-1-6 Wakarumade Native / Architecture / OCR

### Q1: Why separate frontend and backend?
S: API keys were exposed when logic lived in the client
A: Moved all sensitive logic to a backend service and introduced token-based auth
R: secrets are no longer shipped to clients, zero security incidents

### Q2: Web-first design failure in native port
S: Web-first design assumed browser OCR, failed in native
A: Introduced dedicated OCR microservice, decoupled client
R: native and web share backend, scale independently

### Q3: Choosing OCR engine
S: Needed reliable OCR for kids; cloud APIs had latency and rate limits
A: Chose Tesseract for on-device stability
R: OCR works offline, eliminated API costs and throttling

### Q4: OCR embedding caused conflicts
S: Embedding OCR in Expo caused crashes and dependency conflicts
A: Extracted OCR into separate backend service with clean API
R: mobile app stable, can swap OCR engines without touching client

### Q5: Native port assumptions broke
S: Native port failed; web design assumed client-side OCR
A: Created external OCR service
R: OCR works on both web and native platforms

### Q6: Track to Inventory messy structure
S: Initial Next.js app caused duplicate files when ported to Shopify Remix
A: Reorganized project with clear structure, removed redundant files
R: codebase manageable, new features added safely

### Q7: Business logic placement
S: Functions required API keys and sensitive data; unsafe on client
A: Moved to server; client only handles UI
R: sensitive data safe, client lightweight, development easier

### Q8: Data persistence choice
S: LocalStorage insufficient for multiple children / reloads
A: Adopted Supabase without complex Auth
R: Data persists reliably, app remains simple and safe

### Q9: OCR engine trade-off
S: Google Vision fast but rate-limited; Tesseract slower but stable
A: Chose Tesseract on-device for children app
R: OCR consistent, app stable, maintainable

### Q10: Redesign for engagement
S: Chat-based app feels less engaging for children
A: Redesign as “digital paper” with AI hints and annotations
R: Combines analogue teaching benefits with AI, increasing engagement
