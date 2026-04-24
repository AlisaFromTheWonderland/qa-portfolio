# RTM — Roles and Access Matrix

> **Document type:** Documentation testing / role-based access matrix  
> **Purpose:** Validate which fields, permissions, and profile attributes are available for each user role.

---

## Roles Covered

- **Guest**
- **Registered User**
- **Premium User**
- **Administrator / Moderator**

---

## Roles and Access Matrix

| Field / User Data | Guest | Registered User | Premium User | Administrator / Moderator | Comment / Purpose |
|---|---|---|---|---|---|
| **Email** | ❌ | ✅ Required | ✅ Required | ✅ Required | Used for login, password recovery, and communication |
| **Password / OAuth token (Google, Apple ID)** | ❌ | ✅ Required | ✅ Required | ✅ Required | Used for user authentication |
| **Username / Nickname** | ❌ | ✅ Required | ✅ Required | ✅ Required | Displayed in profile and community |
| **Profile Photo / Avatar** | ❌ | 🔹 Optional | ✅ Recommended | ✅ Required | Used for profile personalization |
| **Interface Language (UA / EN)** | ✅ Default UA | ✅ | ✅ | ✅ | Can be changed in settings |
| **Date of Birth / Age** | ❌ | 🔹 Optional | 🔹 Optional | ✅ For statistics | Used for personalization and recommendations |
| **Country / Region** | ❌ | 🔹 Optional | ✅ | ✅ | Used for content localization |
| **User Level / Status** | ❌ | ✅ Automatic | ✅ With bonuses | ✅ Admin level | Used for badges and achievements |
| **Genre / Category Preferences** | ❌ | 🔹 Optional | ✅ Required | 🔹 Analytics view only | Used for AI-based recommendations |
| **Push Notifications Consent** | ❌ | 🔹 Optional | ✅ Required | ✅ | GDPR consent during registration |
| **Privacy Settings (profile visibility / activity visibility)** | ❌ | ✅ | ✅ Extended | ✅ Full control | Restricts profile and activity visibility |
| **Premium Status / Subscription** | ❌ | ❌ | ✅ | 🔹 Can be changed manually | Managed through in-app purchases |
| **Payment Method Data** | ❌ | ❌ | ✅ | 🔹 Monitoring / statistics only | Stored in encrypted form (GDPR / PCI DSS) |
| **Account Creation Date** | ❌ | ✅ Automatic | ✅ | ✅ | Used for audit and synchronization |
| **Activity Log / Login History** | ❌ | ✅ | ✅ | ✅ | Used for security and monitoring |
| **Device Synchronization (Device ID)** | ❌ | ✅ One device | ✅ Multiple devices | ✅ Admin access | Used for cloud sync |
| **Consent to Personal Data Processing (GDPR)** | ❌ | ✅ Required | ✅ Required | ✅ Required | Mandatory during registration |
| **Access Level / System Role** | 🔹 Temporary role “Guest” | ✅ `User` | ✅ `Premium` | ✅ `Admin` | Assigned automatically after registration |
| **Reading History / Analytics** | ❌ | ✅ Local + cloud | ✅ Extended | 🔹 Monitoring access | Stored for statistics and usage analysis |
| **Buddy Reading / Challenges** | ❌ | ✅ Basic | ✅ Extended | ✅ Creation / moderation | Integrated with user profile |

---

## Notes

- **✅ Required** — the field or access is mandatory for the role
- **🔹 Optional / Limited** — available partially, optionally, or with restricted access
- **❌ Not available** — not accessible for the role

---

## Validation Focus

This matrix can be used to verify:

- role-based field availability
- mandatory vs optional profile data
- access restrictions by role
- premium-only features
- admin/moderator control permissions
- GDPR-related required data handling
