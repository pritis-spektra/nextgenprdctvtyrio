Lab 3 – Intelligent File Organizer (Zava Retail)
Prerequisite sample files — 28 total

HOW TO USE
1. In OneDrive, create a folder named "Lab Files".
2. Inside it, create four subfolders: "Retail", "HR", "Shared Files", "Archive Candidates".
3. Upload the contents of each folder in this zip into the matching OneDrive subfolder.
4. In OneDrive, set "Anyone with the link" sharing on at least 3 files inside
   "Shared Files" (e.g. TeamProjectPlan.xlsx, CompanyWideAnnouncement.docx,
   NewHire_Onboarding_Checklist.docx) to satisfy the Lab prerequisites step.

WHAT'S INCLUDED AND WHY (maps to the lab walkthrough)

Exact duplicates (3) — triggers Exercise 2's "duplicate files" finding:
  - Retail/VendorPricing_2025.xlsx <-> Retail/VendorPricing_2025_copy.xlsx
  - Shared Files/TeamProjectPlan.xlsx <-> Shared Files/TeamProjectPlan_copy.xlsx
  - Shared Files/NewHire_Onboarding_Checklist.docx <-> ..._copy.docx

Near-duplicate versioned pairs (2) — triggers the "versioned near-duplicate" finding:
  - Retail/SeasonalPromo_Draft.docx vs SeasonalPromo_Draft_v2.docx
  - HR/Benefits_OpenEnrollment_2025.xlsx vs ..._v2.xlsx

Empty placeholder spreadsheets (5) — triggers the "no clear owner" / empty-file finding
  and the PDF-fallback extraction behavior called out in Exercise 1:
  - Retail/Store_Opening_Checklist.xlsx
  - HR/Facilities_EquipmentInventory.xlsx
  - HR/Training_Schedule_Template.xlsx
  - Shared Files/Budget_Overview_2026.xlsx
  - Shared Files/Marketing_Assets_Tracker.xlsx
  (The original walkthrough references up to 13 such files; add more blank .xlsx
  files yourself if you want to match that exact count.)

Ownership gap (1) — HR/LegacyPolicy.docx, referenced by name in Exercise 2's
  audit report as a "no clear owner" finding.

Legacy/compliance files (2) — archived in Exercise 2, Task 3:
  - HR/PersonnelRecords_Legacy2019.pdf
  - HR/HR_Compliance_Audit_2019.docx
  (After archiving, 8 active HR files remain for Exercise 4, matching the guide.)

Pre-populated stale documents (3) — Archive Candidates folder, already stale
  by design (2018–2020 dated content), so the Archive subfolder shows
  "3 pre-existing" items before Exercise 2's governance action adds more.

Everything else (Q1_Sales_Summary.xlsx, inventory_jan2026.xlsx, StoreLayout_Fall2025.pdf,
Recruiting_JobDescriptions_2025.docx, EmployeeHandbook_Policy.pdf,
Employee_Relations_CaseLog.docx, CompanyWideAnnouncement.docx) is realistic
filler content so the AI classification and renaming steps in Exercise 1 have
enough variety to work with.

Note: real file names, content, and Copilot Cowork's actual classification/audit
output will vary slightly by run — this set is designed to produce results that
closely track the lab guide, not to guarantee an identical output every time.
