## AI driven Train induction planing and scheduling for KMRL


### Tech Stack
###### UI
- React and tailwind css for UI
- Recharts (React library)
- FullCalendar.js (React component)
###### Backend
- Node.js , Express.js  (Work well with react)
- SQLite [Future PostgresSQL if scaling]
- Tesseract.js For QCR (Works offline)
- CSV/PDF parses to store in DB



###  Features Breakdown

- Each trainset (1–25) = row.
    
- Columns:  
    Fitness Certificate (valid/expired, OCR if PDF)  
     Job Cards (open/closed from CSV)  
     Branding (priority score)  
     Mileage (from log CSV)  
     Depot Bay (from static sheet)
    
- Colour coding: Green = good, Yellow = warning, Red = issue.
    
- Supervisor **clicks a train row → opens modal**.
    
- Modal has:
    
    - Train ID pre-filled
        
    - Start time picker (HH:MM)
        
    - Duration input (hours/minutes)
        
- Saved schedule appears in a **calendar view**

- Expired Fitness Cert = ❌ Red
    
- Critical job card open = ⚠️ Red
    
- Branding below target = ⚠️ Yellow
    
- Mileage variance > threshold = ⚠️ Yellow
---
eg:  `⚠️ Train 07 – Certificate Expired`

##### Algorithm and  Logical for  wear distribution 
Script in backend: 
- Calculate average mileage across all trains.
- Compare each train’s mileage
- Output: “Run / Rest” suggestion in dashboard.


#### Summary 

- Setup React + Express app.
    
- CSV upload + parse (job cards, mileage, branding, depot).
    
- Train list table basic UI.

- Add colour-coded validation rules.
    
- Integrate OCR (Tesseract.js) for fitness certs.
    
- Add “Run / Rest” mileage balancer.
-  Add train selection + scheduling modal (FullCalendar.js).
    
- Show alerts clearly on top.