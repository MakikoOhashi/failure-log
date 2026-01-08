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

## 2026-01-08 – Failure Log (Conflict / Team:Previous Office Experience

### Q1. Misuse of FOB with Customer’s Forwarder
**S**  
In my previous office, sales tried to use FOB with customers even when we had to rely on the customer’s forwarder, which increased operational risk.

**A**  
I explained the risks of using FOB under that structure and supported sales with concrete examples.

**R**  
Although sales finally followed the customer’s request, they became aware of the operational risks behind Incoterms.

### Q2. Misunderstanding of Indian Factory Lead Time
**S**  
Sales misunderstood the lead time at the Indian side.  
It actually took around **10 days just from the Indian factory to the Indian port**, and vessel lead time was additional, but they expected only 3 days.

**A**  
I informed both sales and the customer and recalculated the delivery schedule.

**R**  
It was already too late, and they finally decided to switch from sea freight to air freight, which increased the cost significantly.

### Q3. Dangerous Use of Dhaka Airport
**S**  
When Dhaka airport was on fire, the import warehouse situation was extremely bad and our forwarder warned about loss and damage.

**A**  
I repeatedly recommended sales and the customer not to use Dhaka airport.

**R**  
There was no alternative airport and the sewing factory could not wait for sea shipment.  
We proceeded with the customer’s decision after clearly notifying that we could not take responsibility for the arrival condition.

### Q4. Merged Sales Teams and Unrealistic Delivery Control
**S**  
Two sales teams (import and domestic) were merged.  
A member from the domestic side treated import orders the same way and insisted on fixed delivery dates.

**A**  
I explained that import schedules are unstable due to vessel delay and customs clearance.

**R**  
After several months, he finally understood that it is unrealistic to promise definitive delivery dates for import items.

### Q5. Helping Sales vs Letting Them Fail
**S**  
An import sales colleague told me not to help sales too much, because sales would not learn overseas trading risks and would make bad contracts.

**A**  
I decided to keep helping, but always explained why each situation was dangerous, low-profit, or had long lead time.

**R**  
Sales started to understand the risks behind overseas trading instead of just relying on me.

### Q6. Conflict Between Boss and Sales Philosophy
**S**  
Sales thought it was important to fail themselves to learn triangle shipment, but my boss wanted to avoid failures and asked me to support strongly.

**A**  
I discussed the issue with both sides.

**R**  
I took a middle approach: supporting sales while ensuring they clearly understood the risks and structure of triangle shipment.

### Q7. Order Handling vs Maintenance Task
**S**  
Another sales assistant prioritized maintaining delivery-date lists, but I thought real orders were more critical.

**A**  
I always handled urgent orders first and postponed maintenance tasks.

**R**  
He received high evaluation for maintenance work, which revealed the gap between actual impact and evaluation criteria.

### Q8. No One Owned the HK Payment Flow
**S**  
There was a sales flow where payment was made to HK branch instead of JP HQ, but no one owned the process.

**A**  
I caught the issue, connected with HK staff, led the sales, and explained the flow to them.

**R**  
This flow became officially part of my responsibility.

### Q9. Duplicate Order Risk by CC Chaos
**S**  
A customer email with too many CCs caused a duplicated order.

**A**  
I immediately coordinated with colleagues and redesigned who should handle the order.

**R**  
Quick internal communication prevented further duplicated orders.

### Q10. Sharing Shipping Documents for SAP Input
**S**  
I gathered shipping documents for another colleague’s account so she could quickly input data into SAP.

**A**  
I shared the documents immediately.

**R**  
Everyone could see the latest stock status, which also helped the PIC handling import instructions.

