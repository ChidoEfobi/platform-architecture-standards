# Cloud Resource Naming Standard

**Document Owner:** Cloud Platform Engineering  
**Applies To:** All Azure resources, Infrastructure-as-Code deployments, monitoring components, and security platforms  
**Version:** 1.0  

---

## 1. Purpose

This standard defines naming conventions for all cloud resources to ensure:

- Consistency across environments  
- Automation compatibility  
- Governance enforcement  
- Rapid operational troubleshooting  
- Readability for cross-functional teams  
- Scalability of infrastructure

---

## 2. Design Principles

All resource names must be:

- Deterministic  
- Human readable  
- Machine parseable  
- Environment identifiable  
- Region identifiable  
- Workload identifiable  
- Tier identifiable  
- Sequentially unique  

Names must allow an engineer to understand resource purpose **without opening the portal**.

---

## 3. Naming Format Standard

All resources must follow this pattern:
'<resource>-<org>-<env>-<region>-<workload>-<tier>-<instance>'


Example:

vm-chido-preprod-cae-customerportal-web-01


---

## 4. Component Definitions

| Component | Description | Example |
|-----------|------------|---------|
| resource  | Azure resource type | vm |
| org       | organization or tenant | chido |
| env       | environment | prod |
| region    | Azure region code | cae |
| workload  | application/service | customerportal |
| tier      | architecture layer | web |
| instance  | numeric sequence | 01 |

---

## 5. Approved Prefixes

| Resource | Prefix |
|----------|--------|
| Virtual Machine | vm |
| Resource Group  | rg |
| Virtual Network | vnet |
| Subnet          | snet |
| Network Security Group | nsg |
| Public IP       | pip |
| Disk            | disk |
| Load Balancer   | lb |
| VM Scale Set    | vmss |
| Key Vault       | kv |
| Storage Account | st |
| Log Workspace   | log |
| Sentinel        | sentinel |

---

## 6. Region Codes

| Region | Code |
|--------|------|
| Canada Central | cae |
| East US        | eus |
| West Europe    | weu |
| UK South       | uks |

---

## 7. Environment Codes

| Environment | Code |
|------------|------|
| Production | prod |
| Pre-Production | preprod |
| Development | dev |
| Testing    | test |
| Sandbox    | sbx |

---

## 8. Tier Classification

| Tier | Meaning |
|------|---------|
| web  | public entry layer |
| app  | application logic |
| db   | database |
| sec  | security platform |
| ops  | monitoring/logging |
| mgmt | administrative |

---

## 9. Examples

### Virtual Machine

vm-chido-prod-cae-payments-app-01


### Security Workspace
log-chido-prod-cae-secops-01


### Network Security Group

nsg-chido-preprod-cae-customerportal-web-01

---

## 10. Tags (Mandatory for All Resources)

| Tag | Example |
|-----|--------|
| Environment | prod |
| CostCenter  | cc1024 |
| Owner       | CloudPlatformTeam |
| Workload    | customerportal |
| Criticality | high |
| DataClassification | confidential |
| ManagedBy   | terraform |

---

## 11. Forbidden Practices

- Personal emails in names or tags  
- Random strings  
- Inconsistent separators  
- Uppercase characters  
- Spaces  
- Missing environment or region  
- Duplicate resource names

---

## 12. Terraform Compliance

All Terraform modules must:

- Enforce naming via variables  
- Reject invalid names  
- Auto-generate sequence numbers  
- Validate environment codes  

---

## 13. Security Platform Exception

Security resources must use **platform ownership naming**, not workload naming:

sentinel-chido-prod-cae-soc-01


---

## 14. Automation Compatibility

- Lowercase letters only  
- Hyphens as separators  
- Maximum 63 characters  

---

## 15. Change Management

Updates to this standard must be approved by:

- Cloud Architecture Team  
- Security Architecture Team  
- Platform Engineering  

---

**End of Document**

