---
enabled: true
company_name: ""
company_description: ""
industry: []
locations: []
evp: ""
culture-value-deck: ""
careers_url: ""
preferred_channels: []
sourcing_tools: []
ATS: ""
client_sectors: []
target_companies: []
compensation_philosophy: ""
outreach_tone: ""
report_branding: ""
company_size: 
company_stage: ""
startup_fit_sourcing:                                    # true or false
dossier_retention_days:                                  # e.g. 180 — see "Candidate Data Retention"
---

# Talent Sourcing Configuration

## Company Context

Provide company information so sourcing agents can tailor their work.
Fill in the frontmatter fields above with your company details:

- **company_name**: Your company name
- **company_description**: Brief description of what your company does
- **industry**: Primary industry (e.g., "fintech", "healthtech", "enterprise SaaS")
- **locations**: Office locations as a list (e.g., ["Berlin", "NYC", "Remote"])
- **evp**: Employee Value Proposition - what makes your company attractive to candidates
- **careers_url**: Link to your careers page

## Sourcing Preferences

- **preferred_channels**: Ranked list of sourcing channels your team uses
- **sourcing_tools**: Tools available (e.g., ["LinkedIn Recruiter", "Gem", "Hiretual"])
- **target_companies**: Default target company list (used as starting point for talent maps)
- **compensation_philosophy**: How you position on comp (e.g., "75th percentile base + strong equity")

## Reporting Preferences

- **outreach_tone**: Tone for messaging suggestions ("professional", "casual", "technical")
- **report_branding**: Company name/logo reference for dashboard headers

## Notes on Target Company List

Optional. Use this section to describe how `target_companies` (curated top-20) relates to the full directory in `.claude/data/sector-companies.md`:

- **Segments**: how you group companies (e.g., direct competitors, adjacent industries, talent exporters)
- **Per-role expansion**: when to pull additional companies from the directory for a specific role

## Candidate Data Retention

- **dossier_retention_days**: How long candidate dossiers in `roles/*/candidates/` are kept after a role closes (e.g., 180). Set per your privacy notice and local law. Agents remind you to delete expired dossiers during the post-close retrospective.
