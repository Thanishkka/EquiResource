# EquiResource
EquiResource is a resource distribution platform designed to address the uneven distribution of essential resources. It connects people or organizations that have surplus resources with those who need them, enabling both free contribution and paid resource provision.

## Webiste Link
https://equiresource-s9sxw.thinkroot.app/dashboard
# EquiResource

### Bridging Resource Gaps Through Intelligent Allocation

EquiResource is a resource distribution platform designed to address the **uneven distribution of essential resources**. It connects people and organizations that have surplus resources with those who need them, supporting both **free contribution** and **paid resource provision**.

The platform focuses on improving equitable access to resources and aligns primarily with **UN Sustainable Development Goal 10 — Reduced Inequalities**.

---

## 🌍 Problem Statement

Resources are not always distributed equally.

While some individuals, organizations, institutions, or communities may have excess food, medical supplies, educational materials, or technology, others may face shortages of the same resources.

Traditional donation platforms primarily focus on charitable giving and may not support situations where surplus resources are offered for a reasonable price.

**EquiResource aims to bridge this gap by intelligently connecting resource availability with resource requirements.**

---

## 💡 Solution

EquiResource provides a centralized platform where users can:

- Contribute resources for free
- Provide surplus resources for a specified price
- Request resources they need
- Specify their location and required quantity
- Discover relevant resources available within a preferred location range
- Receive intelligent resource matches based on material, quantity, location, and price

The platform supports both **free resource redistribution** and **paid surplus distribution** within the same system.

---

## 👥 User Roles

EquiResource has three primary user roles.

### 🟢 Contributor

A **Contributor** offers resources **free of cost**.

They provide information such as:

- Location
- Resource category
- Subcategory
- Material name
- Quantity
- Unit
- Availability
- Description

**Example:**

> Rice — 50 kg — Tambaram — Free

---

### 🔵 Provider

A **Provider** offers surplus resources **for a specified price**.

The Provider has the same interface as a Contributor, with one additional feature:

- Price
- Price unit

**Example:**

> Rice — 100 kg — ₹40/kg — Tambaram

For Provider listings, the matching system also considers **price**, with lower-priced valid resources receiving higher priority.

---

### 🟠 Seeker

A **Seeker** is an individual or organization looking for a particular resource.

They provide:

- Location
- Resource category
- Subcategory
- Required material
- Required quantity
- Unit
- Required-by date
- Urgency

**Example:**

> Rice — 30 kg — Medavakkam — Required within 2 days

---

# 📦 Resource Categories

EquiResource currently focuses on three major resource categories.

## 🍲 Food & Nutrition

### Subcategories

- Groceries & Staples
- Fresh Food
- Prepared Meals
- Packaged Food
- Baby Food
- Nutrition
- Food Kits

### Examples

- Rice
- Wheat
- Pulses
- Fruits and vegetables
- Packaged food
- Cooked meals
- Grocery kits

---

## 💊 Health & Medical Requirements

### Subcategories

- Medicines
- First Aid
- Medical Equipment
- Mobility Aids
- Assistive Devices
- Hygiene
- Menstrual Health
- Protective Supplies

### Examples

- First-aid kits
- Medical equipment
- Wheelchairs
- Hygiene supplies
- Protective equipment

> **Note:** Medical and pharmaceutical resources may require appropriate verification, safety checks, expiry validation, and compliance with applicable regulations.

---

## 📚 Education & Technology

### Subcategories

- Books
- Stationery
- School Supplies
- Laptops & Computers
- Mobile Devices
- Accessories
- Connectivity
- Educational Equipment
- Digital Learning

### Examples

- Textbooks
- Notebooks
- School supplies
- Laptops
- Tablets
- Smartphones
- Computer accessories
- Educational equipment

---

# 🤖 Intelligent Matching

The core feature of EquiResource is its **resource matching engine**.

Instead of manually searching through all available resources, the system identifies suitable matches between **Seekers** and **Contributors/Providers**.

## Matching Criteria

The primary matching factors are:

1. **Material**
2. **Quantity**
3. **Location**
4. **Urgency**
5. **Price** — only for Provider listings

---
## 📍 Location-Based Resource Selection

EquiResource uses location information to help Seekers identify suitable Contributors or Providers **without requiring them to disclose their exact residential address**.

Both resource listings and requirements are associated with a **general location**, such as:

- City
- Town
- District
- Locality
- Area

The Seeker can view available resources along with their listed locations and **choose the Contributor or Provider based on the location that is most convenient or suitable for them**.

### Example

A Seeker needs:

> **Rice — 30 kg**

Available resources may be displayed as:

| Contributor / Provider | Resource | Quantity | Location |
|---|---|---:|---|
| Contributor A | Rice | 50 kg | Tambaram |
| Contributor B | Rice | 30 kg | Medavakkam |
| Provider C | Rice | 100 kg | Velachery |

The Seeker can select the resource based on the location they prefer.

### 🔐 Privacy-Focused Location Sharing

EquiResource does **not require Seekers to disclose their exact residential location** for resource matching.

Instead, users can provide a broader location such as their:

- Area
- Locality
- Town
- City
- District

This provides enough information for practical resource selection while helping protect the user's privacy.

### 🔎 Location as a Selection Criterion

Location is therefore **not used to calculate a distance score or automatically select the nearest resource**.

Instead:

```text
Resource Requirement
        │
        ▼
Find Matching Material
        │
        ▼
Check Available Quantity
        │
        ▼
Display Available Locations
        │
        ▼
Seeker Chooses Preferred
Contributor / Provider

## 📊 Quantity Matching

The system supports both complete and partial fulfillment.

### Example

A Provider has:

> **50 kg Rice**

A Seeker requires:

> **30 kg Rice**

The system can allocate:

> **30 kg → Seeker**

The remaining:

> **20 kg → Available quantity**

can then potentially be matched with another Seeker.

This allows one resource listing to satisfy multiple requirements.

---

# 💰 Price-Based Matching

Price is considered only when matching a Seeker with **Providers**.

For example:

| Provider | Quantity | Price | Location |
|---|---:|---:|---|
| Provider A | 50 kg | ₹38/kg | Within range |
| Provider B | 50 kg | ₹42/kg | Within range |
| Provider C | 50 kg | ₹45/kg | Within range |

The system prioritizes:

**Provider A → Provider B → Provider C**

because the lowest-priced valid resource is preferred.

However, a Provider outside the Seeker's selected location range is excluded even if their price is lower.

---

# 🔄 Matching Flow

```text
                 Resource Listing
                       │
          ┌────────────┴────────────┐
          │                         │
          ▼                         ▼
     Contributor                  Provider
        (Free)                     (Paid)
          │                         │
          └────────────┬────────────┘
                       │
                       ▼
                Matching Engine
                       │
             ┌─────────┼─────────┐
             ▼         ▼         ▼
          Material  Quantity  Location
             │         │         │
             └─────────┼─────────┘
                       │
                       ▼
                Valid Matches
                       │
                ┌──────┴──────┐
                ▼             ▼
           Contributor      Provider
             Match          Match
                              │
                            Price
                              │
                      Lowest price first
                              │
                              ▼
                         Best Match
                              │
                              ▼
                          Allocation
                              │
                              ▼
                       Update Quantity
