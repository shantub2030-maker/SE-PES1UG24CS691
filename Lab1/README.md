# Software Engineering – Lab 1

## Requirements Engineering & UML Modelling

### Problem Statement #27 – Warehouse Inventory & Pallet Location Tracker

---

### 👨‍🎓 Student Details

| **Field** | **Details** |
|---|---|
| **Student Name** | Shantinath Baligar |
| **SRN** | PES1UG24CS691 |
| **Course** | Software Engineering |
| **Lab** | Lab 1 |
| **Problem Statement** | #27 |
| **Domain** | Smart Cities, Transport & Logistics |

---

## 📌 Problem Statement

The **Warehouse Inventory & Pallet Location Tracker** is a system designed to accurately track pallet storage, inventory movements, and pallet locations within a warehouse.

The system supports pallet identification, 3D warehouse location tracking, rack-capacity validation, stock movement recording, inventory searching, access control, and stock monitoring.

---

## 🎯 Objectives

- Accurately track the location of pallets within a warehouse.
- Validate rack capacity before storing pallets.
- Identify pallets using barcode/RFID scanning.
- Record inbound, outbound, and transfer movements.
- Maintain a time-stamped history of stock movements.
- Provide quick inventory and pallet location lookup.
- Enforce role-based access control.
- Support efficient warehouse inventory management.

---

## ⚙️ Functional Requirements

| ID | Requirement | Priority |
|---|---|---|
| **FR-001** | Validate proposed pallet placement against the rack's maximum load capacity before confirming storage. | High |
| **FR-002** | Record and maintain the 3D location of each pallet using aisle, rack, level, and slot coordinates. | High |
| **FR-003** | Identify pallets and record stock movements using barcode/RFID scanning for inbound, outbound, and transfer operations. | High |
| **FR-004** | Maintain a time-stamped history of stock movements including pallet ID, movement type, operator ID, and source/destination locations. | Medium |
| **FR-005** | Allow authorized users to search for an SKU or pallet ID and display its current 3D warehouse location and inventory status. | Medium |

---

## 🔒 Non-Functional Requirements

| ID | Type | Requirement | Priority |
|---|---|---|---|
| **NFR-001** | Performance & Scalability | Locate and return the current SKU/pallet coordinates across 100,000 bins within 100 ms under simulated peak-load conditions. | High |
| **NFR-002** | Security & Access Control | Enforce Role-Based Access Control (RBAC) and encrypt sensitive inventory and user data at rest and in transit. | High |

---

## 🔄 Core Use Case

### UC-01: Record Pallet Storage

**Goal:** Enable a Warehouse Operator to scan a pallet, assign it to a valid 3D shelf location, verify rack capacity, and record the storage operation for future tracking and retrieval.

**Primary Actor:** Warehouse Operator

**Secondary Actors:**
- Logistics Supervisor
- Barcode/RFID Scanner

### Preconditions

1. The Warehouse Operator is authenticated and logged into the warehouse management system.
2. The pallet has a valid barcode or RFID tag registered in the system.
3. The proposed rack, level, and slot are available.
4. Rack maximum weight capacity is available in the system.

### Main Success Scenario

1. Warehouse Operator selects **Store Pallet**.
2. Operator scans the pallet barcode/RFID tag.
3. System retrieves the pallet ID, SKU, and weight.
4. Operator selects the aisle, rack, level, and slot.
5. System validates location availability and rack load capacity.
6. System confirms that the pallet does not exceed the rack's structural limit.
7. System records the pallet location and creates a time-stamped movement record.
8. System displays **Pallet Stored Successfully** with the pallet ID and assigned coordinates.

### Alternate Flows

- **Rack Weight Capacity Exceeded:** The system rejects the placement and displays an overload warning.
- **Location Unavailable:** The system informs the operator that the selected location is unavailable.
- **Invalid Barcode/RFID:** The system displays an invalid or unregistered pallet message and requests another scan.

---

## 📊 UML Use-Case Model

### Actors

- **Warehouse Staff**
- **Warehouse Manager**
- **System / Notification Service**

### Primary Use Cases

- Register Inventory
- Track Inventory Status
- Assign Pallet Location
- Monitor Stock Levels & Overdue Movements
- Verify & Confirm Inventory Update

### UML Relationships

#### `«include»`

**Register Inventory** includes **Validate Product & Pallet Details**.

This represents mandatory validation during inventory registration.

#### `«extend»`

**Attach Product Image / Supporting Document** extends **Register Inventory**.

This represents an optional action when supporting evidence is available.

#### `«extend» – Stock Alert`

**Trigger Low-Stock Alert** extends **Monitor Stock Levels & Overdue Movements** when:

`Stock Level < Minimum Threshold`

---

## 🏗️ System Requirements Summary

### Performance

The warehouse lookup service is expected to support:

- Up to **100,000 storage bins**
- Location lookup within **100 ms**
- Simulated peak-load conditions

### Security

The system must:

- Implement **Role-Based Access Control (RBAC)**.
- Restrict operations according to user roles.
- Protect sensitive inventory information.
- Encrypt sensitive data at rest and in transit.

### Traceability

Every successful storage/movement operation should maintain:

- Pallet ID
- Movement type
- Operator ID
- Source location
- Destination location
- Timestamp

---

## 📁 Repository Structure

```text
SE-PES1UG24CS691/
│
├── README.md
│
└── Lab1/
    ├── README.md
    ├── Requirements/
    ├── Use-Case/
    ├── UML/
    └── Documentation/
```

---

## 📚 Lab Deliverables

This Lab 1 submission covers:

- Functional Requirements
- Non-Functional Requirements
- Acceptance Criteria
- Rationale
- Core Use-Case Flow Specification
- Main Success Scenario
- Alternate and Exception Flows
- Special Requirements
- UML Use-Case Model
- `«include»` relationship
- `«extend»` relationships
- UML Use-Case Diagram

---

## ✅ Requirements Checklist

- [x] Functional Requirements identified
- [x] Non-Functional Requirements identified
- [x] Acceptance Criteria defined
- [x] Rationale provided
- [x] Core Use Case documented
- [x] Main Success Scenario documented
- [x] Alternate Flows documented
- [x] Special Requirements documented
- [x] UML Actors identified
- [x] UML Use Cases identified
- [x] `«include»` relationship specified
- [x] `«extend»` relationships specified
- [x] UML Use-Case Diagram included

---

## 👨‍💻 Student

**Shantinath Baligar**  
**PES1UG24CS691**

### Software Engineering – Lab 1

**Problem Statement #27: Warehouse Inventory & Pallet Location Tracker**

