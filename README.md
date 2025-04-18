# elb-cross-region

## 📌 Why Use EBS Cross-Region Replication?

- **Disaster Recovery**: In case of region failure or unavailability.
- **Backup Compliance**: Required for regulatory or business continuity reasons.
- **High Durability**: Ensures your volume data is not bound to a single region.
- **Multi-Region Architecture**: Prepares infrastructure for scaling or failover.

---

## 📦 What You Need

| Component         | Purpose                                                |
|------------------|--------------------------------------------------------|
| Amazon EC2        | Hosts the EBS volume                                   |
| Amazon EBS        | Stores persistent block-level storage                  |
| AWS CLI / Boto3   | For snapshot automation                                |
| IAM Role/Policy   | To allow EBS and EC2 snapshot actions                  |
| S3 (optional)     | For secondary backup of snapshots or metadata          |
| CloudWatch (opt.) | For monitoring replication status and automation logs  |

---

## 📅 When to Use This

- If you require **scheduled backups** of critical volume data to a separate region.
- When implementing **multi-region failover** and resilience.
- If your business needs **geo-redundant backups**.
- If you're preparing a **region migration** or DR drill.

---

## 🚀 How It Works

1. **Take a snapshot** of an existing EBS volume.
2. Use a script or Lambda to **copy the snapshot** to another region.
3. Monitor or automate this process using **CloudWatch Events** or **Step Functions**.
4. Restore from cross-region snapshots during failover or disaster events.
