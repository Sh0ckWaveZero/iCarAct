# Feature Specification: iCarAct - Vehicle Tax & Insurance Management System

**Feature Branch**: `001-system-name-icaract`
**Created**: 2025-09-19
**Status**: Draft
**Input**: User description: "System Name: iCarAct
Purpose: Thai vehicle tax and insurance renewal management system for shops that handle vehicle registration renewals and automatic notifications

Core Features:
    1. Customer Data Management → Store customer name, address, phone, license plate, insurance/tax expiration dates
    2. Automatic Notifications → Send LINE messages before renewal deadlines
    3. Search & Filter → Find customers by name, phone, or license plate
    4. Dashboard → Display customers with upcoming expiration dates
    5. Multi-platform → Available on PC (Web App) and Android App

Optional Features:
    • Export data to Excel/PDF
    • SMS/Email notifications
    • Payment status tracking
    • Calendar view for expiration dates"

## Execution Flow (main)

```
1. Parse user description from Input
   → Parsed successfully: Thai vehicle tax/insurance renewal management system
2. Extract key concepts from description
   → Actors: shop owners/staff, customers
   → Actions: store data, notify, search, view dashboard, export
   → Data: customer info, vehicle registration, renewal dates
   → Constraints: multi-platform (web + Android)
3. For each unclear aspect:
   → [NEEDS CLARIFICATION: specific notification timing - how many days before expiry?]
   → [NEEDS CLARIFICATION: user authentication and permissions not specified]
   → [NEEDS CLARIFICATION: LINE integration authentication method not specified]
4. Fill User Scenarios & Testing section
   → Primary flow: register customer → view dashboard → receive notifications
5. Generate Functional Requirements
   → 17 testable requirements covering core features
6. Identify Key Entities
   → Customer, Vehicle, Insurance Policy, Tax Record, Notification
7. Run Review Checklist
   → WARN "Spec has uncertainties - contains [NEEDS CLARIFICATION] markers"
8. Return: SUCCESS (spec ready for planning with clarifications needed)
```

---

## ⚡ Quick Guidelines

- ✅ Focus on WHAT users need and WHY
- ❌ Avoid HOW to implement (no tech stack, APIs, code structure)
- 👥 Written for business stakeholders, not developers

### Section Requirements

- **Mandatory sections**: Must be completed for every feature
- **Optional sections**: Include only when relevant to the feature
- When a section doesn't apply, remove it entirely (don't leave as "N/A")

---

## User Scenarios & Testing *(mandatory)*

### Primary User Story

A vehicle tax/insurance renewal service shop needs to track customers' renewal dates and automatically notify them before their insurance (พ.ร.บ.) or vehicle tax expires. Staff should be able to quickly find customer information, see upcoming renewals on a dashboard, and customers should receive timely LINE notifications to ensure they don't miss renewal deadlines.

### Acceptance Scenarios

1. **Given** a new customer visits the shop, **When** staff enters customer details and vehicle information with renewal dates, **Then** the customer record is saved and appears in the system
2. **Given** a customer's insurance expires in [NEEDS CLARIFICATION: notification timing not specified] days, **When** the automatic notification system runs, **Then** the customer receives a LINE message reminder
3. **Given** staff needs to find a customer, **When** they search by name, phone number, or license plate, **Then** matching customer records are displayed
4. **Given** staff opens the dashboard, **When** viewing today's overview, **Then** they see all customers with renewals expiring soon
5. **Given** staff needs to export customer data, **When** they request an export, **Then** data is provided in Excel or PDF format
6. **Given** a customer pays for their renewal, **When** staff updates the payment status, **Then** the record shows payment completed and renewal date is updated

### Edge Cases

- What happens when a customer's LINE account is invalid or blocked?
- How does the system handle duplicate license plate entries?
- What occurs when export files become too large?
- How are customers notified if the LINE service is unavailable?

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: System MUST allow staff to create customer records with name, address, phone number, vehicle license plate, and renewal expiration dates
- **FR-002**: System MUST store both vehicle tax and insurance (พ.ร.บ.) expiration dates for each customer
- **FR-003**: System MUST automatically send LINE notifications to customers before their renewal dates
- **FR-004**: System MUST allow staff to search customers by name, phone number, or license plate number
- **FR-005**: System MUST provide a dashboard showing customers with upcoming renewal dates
- **FR-006**: System MUST be accessible via web browser for PC users
- **FR-007**: System MUST be available as an Android mobile application
- **FR-008**: System MUST allow exporting customer data to Excel format
- **FR-009**: System MUST allow exporting customer data to PDF format
- **FR-010**: System MUST allow staff to record payment status for renewals
- **FR-011**: System MUST display renewal dates in a calendar view format
- **FR-012**: System MUST send notifications via SMS as an alternative to LINE
- **FR-013**: System MUST send notifications via email as an alternative to LINE
- **FR-014**: System MUST allow updating customer information after initial entry
- **FR-015**: System MUST prevent duplicate license plate entries for different customers
- **FR-016**: System MUST authenticate users before allowing system access [NEEDS CLARIFICATION: authentication method not specified - username/password, PIN, biometric?]
- **FR-017**: System MUST send notifications [NEEDS CLARIFICATION: timing not specified - how many days before expiry?]

### Key Entities *(include if feature involves data)*

- **Customer**: Represents individual clients, contains personal information (name, address, phone), linked to vehicles
- **Vehicle**: Represents customer vehicles, contains license plate number, linked to tax and insurance records
- **Insurance Policy (พ.ร.บ.)**: Represents mandatory vehicle insurance, contains expiration date and renewal status
- **Tax Record**: Represents vehicle tax obligations, contains expiration date and payment status
- **Notification**: Represents automated reminders sent to customers, contains delivery method (LINE/SMS/email) and status
- **Staff User**: Represents shop employees who use the system, contains access permissions and login credentials

---

## Review & Acceptance Checklist

*GATE: Automated checks run during main() execution*

### Content Quality

- [X] No implementation details (languages, frameworks, APIs)
- [X] Focused on user value and business needs
- [X] Written for non-technical stakeholders
- [X] All mandatory sections completed

### Requirement Completeness

- [ ] No [NEEDS CLARIFICATION] markers remain
- [X] Requirements are testable and unambiguous
- [X] Success criteria are measurable
- [X] Scope is clearly bounded
- [X] Dependencies and assumptions identified

---

## Execution Status

*Updated by main() during processing*

- [X] User description parsed
- [X] Key concepts extracted
- [X] Ambiguities marked
- [X] User scenarios defined
- [X] Requirements generated
- [X] Entities identified
- [ ] Review checklist passed (pending clarifications)

---
