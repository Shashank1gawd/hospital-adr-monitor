# Demo case: Enalapril and angioedema

This is a fictional case. Use it to check that the app works. Dates are shown as day-month-year; the date pickers on your device may show them in another order.

## Report tab

**A. Patient**

| Field | Enter |
|---|---|
| Patient code or initials | `AB` |
| Age (years) | `54` |
| Sex | `Female` |
| Weight (kg) | `62` |
| Relevant medical history | `Hypertension. No known drug allergy` |

**B. Suspected reaction**

| Field | Enter |
|---|---|
| Reaction description | `Angioedema with lip and facial swelling` |
| Onset date | 12-Sep-2026 |
| Date reaction stopped | 15-Sep-2026 |
| Outcome | `Recovered` |
| Seriousness | tick **Hospitalisation** only |

**C. Suspected medicine**

| Field | Enter |
|---|---|
| Generic name | `Enalapril` |
| Dose | `10 mg` |
| Route | `Oral` |
| Frequency | `once daily` |
| Start date | 20-Aug-2026 |
| Stop date | 12-Sep-2026 |
| Indication | `Hypertension` |
| Action taken | `Drug withdrawn` |
| Dechallenge | `Positive` |
| Rechallenge | `Unknown` |
| Other medicines taken | `Amlodipine, Atorvastatin` |

**D. Reporter**

| Field | Enter |
|---|---|
| Reporter role | `Doctor` |
| Department / ward | `Medicine` |
| Report date | 16-Sep-2026 |

**Expected:** the completeness bar is full and says **Valid report**.

## Assessment tab

| Step | Enter | Expected result |
|---|---|---|
| WHO-UMC Q1 timing plausible | Yes | |
| Q2 other causes could explain it | No | |
| Q3 improved on stopping | already Yes from dechallenge; confirm | |
| Q4 recognised drug effect | Yes | |
| Q5 rechallenge | leave as Not done | **Probable** |
| Severity | Level 4b | **Moderate (level 4b)** |
| Preventability | tick nothing | **Not preventable** |

Expected case summary (date wording varies with your device language):

> AB (Female, 54 y) in Medicine developed Angioedema with lip and facial swelling on 12 Sep 2026 after Enalapril (10 mg, Oral, once daily) started 20 Aug 2026.
> Action taken: drug withdrawn. Dechallenge: positive. Rechallenge: unknown. Outcome: recovered.
> Seriousness: Hospitalisation.
> Causality (WHO-UMC): Probable. Severity: Moderate (level 4b). Preventability: not preventable.

Press **Save report**. Expected message: `Saved as ADR-001 (Assessed). It now counts in the dashboard.`

## After saving

- The **Saved reports** button and tab show **1**.
- **Ward dashboard:** Reports 1, Serious 1, Fatal 0, Preventable 0, Drafts 0, Ready to submit 1.
- **Saved reports** shows one row: Enalapril, Angioedema, Probable, Moderate, Assessed. **Load** reopens every field. **Mark submitted** changes the status to Submitted.
- Reload the page: the count is still 1.

## Extra checks

- **Repeat alert:** clear the form, enter the same case but with patient `CD`, age `61`, sex `Male`, severity `Level 3`, and save. The dashboard shows *2 reports: enalapril → angioedema with lip and facial swelling (Watch)*. The reaction text must be spelled identically.
- **Draft status:** enter only a medicine and a reaction, then save. The status is **Draft**.
