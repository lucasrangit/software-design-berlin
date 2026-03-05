# Kata 2: PaperTrail

A compliance document management system for regulated industries.

A mid-size consultancy serving pharmaceutical and financial clients needs a system to manage compliance documents. Documents go through complex approval workflows (sometimes 12+ steps), must maintain a tamper-proof audit trail, and need to support simultaneous editing by multiple reviewers with different permission levels.

Users: 500 internal consultants, 2,000 client users across 30 organisations. Peak usage: end of fiscal quarters.

## Requirements

1. Configurable approval workflows (each client has different rules)
2. Tamper-proof audit log (legally admissible)
3. Role-based access control with client-level isolation
4. Full-text search across all documents with permission-aware results
5. Version comparison (diff) between any two versions of a document
6. Offline access for consultants traveling to client sites.

## Constraints

1. Must comply with FDA 21 CFR Part 11 (electronic signatures) and SOX
2. Documents must never leave the EU (data residency)
3. Integration with existing Active Directory for client organisations
4. Some clients still use Internet Explorer 11 (yes, really)

## Additional context

The current system is a SharePoint instance that everyone hates. Migration must be incremental — no big bang.

## Solution

### Our Team (original)
* We are 15 developers, certified compliance experts, blockchain cracks, web3, full-stack, architects.
* We own our own infrastructure
* Teams are evenly distributed by, full-stack, compliance, devops.
* However, we are open to change.

### Our Team (revised)
