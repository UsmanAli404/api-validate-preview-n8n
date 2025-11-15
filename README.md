# API Sync + Validate + Preview (n8n Workflow)

This workflow provides a safe, structured intake pipeline for any API-driven product.  
It receives incoming data, cleans it, validates it, and generates a non-destructive preview—without performing any writes.

---

## 🚀 What This Workflow Does

### 1. Accepts Incoming Data (Webhook)
- Listens for POST requests with JSON payloads  
- Includes idempotency keys to avoid double processing  
- Fully retry-safe

### 2. Normalizes & Cleans Fields
- Email normalization  
- URL cleanup  
- Case corrections  
- Whitespace trimming  
- Optional field remapping

### 3. Calls `/validate` on Your Backend
- Sends the cleaned data to your API  
- Expects structured validation errors (if any)  
- Prevents invalid data from progressing further

### 4. Calls `/dedupe/preview`
- Creates a dry-run “diff” of what would change  
- No records are modified  
- Perfect for safe previews in early MVPs

### 5. Returns a Structured Preview Response
- Clean JSON object including:
  - normalized payload  
  - validation results  
  - dedupe preview diff  
- Can be consumed directly by frontends or other automation flows

---

## 🧱 Nodes Included
- Webhook (Main Trigger)  
- Code Nodes (Normalization)  
- HTTP Request Nodes (`/validate`, `/dedupe/preview`)  
- Error Handling & Retry Logic  
- Logging Helpers  

---

## 🧪 Ideal Use Cases
- Client intake forms  
- CRM record previews  
- Safe copy-update workflows  
- API debugging / staging validation  

---

## 📜 License
MIT — free to use and adapt.

