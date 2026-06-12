# KIDS FOOD SCANNER — MASTER SPEC
## Version: v2 (In Development)
## Date: June 12, 2026
## Family: Taiwo Family, Columbus Ohio

---

## LIVE URLS
- **Production:** https://fscanner.netlify.app/
- **GitHub:** https://github.com/tboy2020/kids-food-scanner
- **Working tag:** v-working-clean (commit 1864ab60533e)
- **Netlify:** Connected to GitHub — auto-deploys on push

---

## FAMILY PROFILES (from Settings)
| Name | Role | Age | Profile |
|---|---|---|---|
| Anu | Child 1 | 5 | Young Child (4-8) |
| Dominion | Child 2 | 7 | Young Child (4-8) |
| Pastor Taiwo | Parent 1 | Adult | Adult (18+) |
| Vera | Parent 2 | Adult | Adult (18+) |

---

## DAILY NUTRIENT LIMITS BY AGE

### Young Child (4-8) — Anu & Dominion
| Nutrient | Daily Limit |
|---|---|
| Sodium | 1200mg |
| Added Sugar | 25g |
| Saturated Fat | 16g |
| Total Carbs | 130g |
| Calories | 1200-1400 kcal |
| Protein | 19-20g |
| Vitamin D | 15mcg |
| Calcium | 1000mg |
| Iron | 10mg |
| Potassium | 2300mg |
| Vitamin C | 25mg |
| Vitamin A | 400mcg |
| Vitamin B12 | 1.2mcg |
| Folate | 200mcg |

### Adult (18+) — Pastor Taiwo & Vera
| Nutrient | Daily Limit |
|---|---|
| Sodium | 2300mg |
| Added Sugar | 50g |
| Saturated Fat | 22g |
| Total Carbs | 275g |
| Calories | 2000-2500 kcal |
| Protein | 50-56g |
| Vitamin D | 15mcg |
| Calcium | 1000mg |
| Iron | 8mg |
| Potassium | 3400mg |
| Vitamin C | 90mg |
| Vitamin A | 900mcg |
| Vitamin B12 | 2.4mcg |
| Folate | 400mcg |

---

## AGE → PROFILE MAPPING
| Age | Profile | Na | Sugar | Cal |
|---|---|---|---|---|
| 1-3 | Toddler | 1000mg | 25g | 1000-1400 |
| 4-8 | Young Child | 1200mg | 25g | 1200-1400 |
| 9-13 | Older Child | 1500mg | 25g | 1400-1600 |
| 14-18 | Teen | 2300mg | 25g | 1800-2200 |
| 18+ | Adult | 2300mg | 50g | 2000-2500 |

---

## VITAMIN RATING SYSTEM
| % Daily Value | Rating | Label |
|---|---|---|
| 0% | ❌ | None |
| 1-5% | ⚠️ | Minimal |
| 6-10% | 🟡 | Low |
| 11-19% | 🟢 | Good |
| 20%+ | ⭐ | Excellent |

---

## ADULT THRESHOLDS (scanner verdicts)
| Nutrient | Watch | Alert/Skip |
|---|---|---|
| Sodium | >400mg | >800mg |
| Sugar | >15g | >25g |
| Sat Fat | >4g | >7g |
| Calories | >400 | >600 |

## KIDS THRESHOLDS (scanner verdicts)
| Nutrient | Watch | Alert/Skip |
|---|---|---|
| Sodium | >200mg | >400mg |
| Sugar | >5g | >10g |
| Sat Fat | >2g | >4g |
| Calories | >200 | >350 |
| Protein | <4g=watch | <3g=alert |

---

## FDA ZERO ROUNDING RULES
- Sugar 0g labeled → up to 0.4g real
- Sodium 0mg labeled → up to 50mg real  
- Sat Fat 0g labeled → up to 0.4g real
- Trans Fat 0g labeled → up to 0.49g real (most abused!)
- Reality Check multiplies labeled values by 1.2 (+20%)

---

## FULL FEATURE LIST — v2 BUILD

### SETTINGS
- [ ] Family name input
- [ ] Add/remove parents (max 2) with name + age
- [ ] Add/remove children (max 6) with name + age + grade
- [ ] Auto-generates profiles from age
- [ ] API key management
- [ ] Food preferences (Nigerian/African foods toggle)
- [ ] Dietary restrictions (nut allergy, dairy free, gluten free, halal)
- [ ] Scanner preferences (reality check, hidden sugars, additives)
- [ ] Dashboard preferences
- [ ] Auto-reset at midnight toggle

### SCANNER
- [ ] Total Sugars + Added Sugars (both shown)
- [ ] Vitamins & Minerals (8 nutrients with daily limits)
- [ ] Label Reality Check (Labeled vs +20% FDA)
- [ ] CONSIDERING vs IF YOU ATE THIS toggle
- [ ] Serving adjuster (+/-) connected to budget
- [ ] Safe max servings per profile (limiting factor shown)
- [ ] Rich dynamic suggestions per nutrient gap
- [ ] Age-specific suggestions
- [ ] Time-of-day aware suggestions
- [ ] Who ate this? selector (family member names)
- [ ] Which meal? selector (6 meal slots)
- [ ] Hidden sugar aliases scan
- [ ] Additives scan
- [ ] Revised recommendation (kids + adults)
- [ ] Nutrient completeness score

### DAILY LOG
- [ ] 6 meal slots (Breakfast, Morning Snack, Lunch, Afternoon Snack, Dinner, Evening Snack)
- [ ] 3 ways to add food: Scan / Search / Manual
- [ ] Per-profile food log
- [ ] Gram input with common unit conversion
- [ ] Remaining needs panel (updates after each food)
- [ ] Smart suggestions based on gaps
- [ ] Limiting factor display

### FOOD DATABASE (100 foods)
- [ ] Common American kids foods (~50)
- [ ] Nigerian/African foods (~30)
- [ ] Common fruits & vegetables (~20)
- [ ] Each entry: calories, protein, sugar, addedSugar, sodium, carbs, fat, satFat, fiber, vitD, calcium, iron, potassium, vitC, vitA, vitB12, folate

### DASHBOARD
- [ ] Per-profile daily breakdown
- [ ] Family side-by-side view
- [ ] Vitamin & mineral tracking
- [ ] Week/Month/All time history
- [ ] Meal slot breakdown
- [ ] Smart daily summary

---

## MEAL SLOTS
| Slot | Emoji | Typical Time |
|---|---|---|
| Breakfast | 🌅 | 6-9am |
| Morning Snack | 🍎 | 9-11am |
| Lunch | 🍽️ | 11am-1pm |
| Afternoon Snack | 🍪 | 2-4pm |
| Dinner | 🌙 | 5-8pm |
| Evening Snack | 🌃 | 8-9pm |

---

## SCAN FLOW
1. Take photo of nutrition label
2. Claude Haiku reads label
3. Select: Who ate this? (family member)
4. Select: Which meal?
5. Toggle: CONSIDERING vs IF YOU ATE THIS
6. Adjust: Serving count (+/-)
7. See: Full analysis with verdicts
8. See: Impact on daily budget
9. See: Remaining needs after this food
10. See: Rich dynamic suggestions
11. Tap WE ATE THIS → locks to tracker
12. Dashboard updates immediately

---

## NIGERIAN FOODS DATABASE (partial list)
- Jollof Rice (per cup, estimated)
- Fried Rice (per cup, estimated)
- Egusi Soup (per cup, estimated)
- Efo Riro (per cup, estimated)
- Pounded Yam (per 100g)
- Fufu (per 100g)
- Akara (per piece, ~30g)
- Moi Moi (per wrap, ~150g)
- Suya (per 100g)
- Eba/Garri (per 100g)
- Ofada Rice (per cup)
- Plantain fried (per piece)
- Plantain boiled (per piece)
- Chin Chin (per 100g)
- Puff Puff (per piece)
- Indomie noodles (per pack)
- Banga Soup (per cup)
- Ogbono Soup (per cup)

---

## TECHNICAL STACK
- Single HTML file (vanilla JS, no frameworks)
- Hosted on Netlify (fscanner.netlify.app)
- Source on GitHub (tboy2020/kids-food-scanner)
- GitHub → Netlify auto-deploy on push
- Claude Haiku API for label reading
- localStorage for data persistence
- No backend, no database server
- Works offline after first load (PWA)
- iOS Safari compatible

---

## CRITICAL TECHNICAL LESSONS LEARNED
1. NEVER patch JS across multiple sessions — always rebuild cleanly
2. Always verify brace balance before pushing (open === close)
3. Service workers cause aggressive caching — use cache-busting sw.js
4. GitHub Pages has CDN caching — use Netlify instead
5. iOS Safari: use addEventListener not inline onclick
6. iOS Safari: attach events in DOMContentLoaded
7. Always verify functions exist after rebuild
8. Check for duplicate function definitions after patching
9. Keep a working git tag (v-working-clean) always up to date
10. Build from the tagged version, not patched version

---

## MONETIZATION (to discuss later)
- Family nutrition tracker SaaS
- Subscription model per family
- Nigerian/African food database as differentiator
- School nutrition programs
- Pediatric wellness partnerships

---

## FILE LOCATIONS
- Spec: /mnt/user-data/outputs/KFS_MASTER_SPEC.md
- Working HTML: /mnt/user-data/outputs/food-scanner.html
- GitHub tag: v-working-clean
