# Playbooks — direct-flights

> CLI command sequences. Knowledge is for parameter mapping — never answer without executing.

---

## Playbook A: Time Priority

**Trigger:** "fastest direct", "最快"

```bash
flyai search-flight --origin "{o}" --destination "{d}" --dep-date {date} --journey-type 1 --sort-type 4
```

**Output emphasis:** Sort by shortest duration.

---

## Playbook B: Direct + Cheap

**Trigger:** "cheapest direct", "最便宜的直飞"

```bash
flyai search-flight --origin "{o}" --destination "{d}" --dep-date {date} --journey-type 1 --sort-type 3
```

**Output emphasis:** Direct flights sorted by price.

---

## Playbook C: No Directs Available

**Trigger:** fallback when 0 results

```bash
# Inform user no directs exist
flyai search-flight --origin "{o}" --destination "{d}" --dep-date {date} --sort-type 4
# Show shortest connecting as alternative
```

**Output emphasis:** Suggest shortest layover option.

---

