## 2026-1-6 Wakarumade Native / Architecture / OCR

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

## Wednesday　2026/01/07 – User Value & Product

### Q1: Building confidence through repetition
S: Children struggled to solve repeated problem types and lost confidence  
A: I designed exercises with gradually increasing similar problems so children could recognize patterns and practice  
R: Children gained confidence and were able to overcome their weak points systematically

### Q2: Feature mismatch with user needs
S: I built an import-status feature in Track to Inventory, but store owners did not use it  
A: I realized they prioritized forecasting inventory rather than managing import details  
R: I started developing a Forecast-to-Inventory feature aligned with their real needs

### Q3: Reducing parent–child friction
S: Children aged 8–10 resisted parental help when solving weak points, causing stress for parents  
A: I designed Wakarumade so children can interact with AI chat and work independently  
R: Children practice without friction and parents are relieved from stress

### Q4: No response as user feedback
S: I contacted a target company about Track-to-Inventory and received no response  
A: I interpreted this as a signal that the product did not solve their pain points and pivoted  
R: I am now building Forecast-to-Inventory to better address user problems

### Q5: Removing distracting hints
S: The hint feature distracted children and reduced focus  
A: I removed it to simplify the interface and encourage them to verbalize weak points  
R: The UX became simpler and children could concentrate better

### Q6: Postponing authentication
S: Authentication would enable progress tracking but add friction for parents and children  
A: I postponed auth to keep onboarding simple and prioritize usability  
R: The current version has low entry barriers and I am designing lightweight auth for the native app

### Q7: Fixing unreliable voice input
S: Voice input was unreliable because children’s speech was unclear  
A: I introduced an AI-based refactoring step before displaying transcribed text  
R: Children experienced less stress and could interact more smoothly

### Q8: Improving discoverability of UI
S: Children could not find the send button because it was too small  
A: I redesigned the UI with larger, child-friendly buttons  
R: Children could use the app intuitively without explanation

### Q9: Launching without auth
S: Auth would help parents track progress but frustrate children  
A: I launched the web version without authentication  
R: Children can now use the app independently

### Q10: Photo-based annotation vision
S: Children often could not recognize which parts needed attention  
A: I decided to add photo-based annotations like real paper worksheets  
R: The native app will better support visual understanding of mistakes
