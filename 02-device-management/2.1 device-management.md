	[toc]

# 目录结构（先建好）

```
Enterprise-IT-Support-Lab/
│
├── README.md
├── architecture-diagram.png
│
├── 01-user-lifecycle/
├── 02-device-management/
├── 03-troubleshooting/
└── screenshots/
```

![image-20260518114254364](./image/image-20260518114254364.png)

![image-20260518113923647](./image/image-20260518113923647.png)

# 🔵 四、第一阶段：Entra ID（用户管理）

## 🎯目标

你要完成：

- 创建用户
- 创建组
- 分配权限

------

## 🔧 Step 1：创建用户

路径：

> Entra Admin Center → Users → New User

创建：

- user1: john.doe
- user2: jane.smith

------

## 🔧 Step 2：创建 Group

- IT-Support
- Sales
- HR

------

## 🔧 Step 3：Assign user to group

写进 GitHub：

```
## User Lifecycle

### Step 1 - Create User
Created two test users in Microsoft Entra ID:
- john.doe
- jane.smith

### Step 2 - Group Assignment
Created groups:
- IT Support
- Sales

Assigned users to simulate enterprise identity structure.
```

------

# 💻 五、第二阶段：Intune Device Management（核心）

## 🎯目标

- enroll device
- push policy
- simulate enterprise endpoint

------

## 🔧 Step 1：Enable Intune

路径：

> Intune Admin Center → Devices

------

## 🔧 Step 2：Enroll Windows VM

在 VM 里：

- Settings → Accounts → Access work or school
- Connect to:
   `yourtenant.onmicrosoft.com`

------

## 🔧 Step 3：确认设备进入 Intune

路径：

> Intune → Devices → Windows

你应该看到你的 VM

------

## 🔧 Step 4：创建 Policy（重点）

### Device Compliance Policy

例如：

- Require password
- Minimum OS version
- BitLocker required

------

写进 GitHub：

```
## Device Management

### Device Enrollment
Enrolled Windows 10 VM into Microsoft Intune via Azure AD join.

### Compliance Policy
Configured device compliance policy:
- Require password
- Enforce encryption
- Minimum OS version check

### Result
Device successfully appears in Intune portal and is managed centrally.
```

------

# ⚠️ 六、第三阶段：模拟 3 个真实 IT 问题（最重要）

这一步决定你“像不像 1年经验的人”。

------

## 🔴 Scenario 1：Outlook Sync Issue

### 模拟：

- 登录 Outlook
- 不同步邮件

### 写法：

```
## Scenario 1 - Outlook Sync Issue

### Problem
User unable to sync emails in Outlook client.

### Diagnosis
Checked:
- Account status in Entra ID
- Exchange Online mailbox
- Network connectivity

### Fix
Re-added account and forced re-sync.

### Result
Outlook restored successful synchronization.
```

------

## 🔴 Scenario 2：Device not showing in Intune

```
## Scenario 2 - Device Enrollment Issue

### Problem
Windows VM not appearing in Intune dashboard.

### Diagnosis
Checked:
- Azure AD join status
- Device enrollment restrictions
- Sync status

### Fix
Re-enrolled device and triggered sync.

### Result
Device successfully registered in Intune.
```

------

## 🔴 Scenario 3：MFA lockout

```
## Scenario 3 - MFA Issue

### Problem
User unable to login due to MFA prompt failure.

### Diagnosis
Verified:
- Authentication methods
- Conditional Access policy

### Fix
Reset MFA methods for user account.

### Result
User regained access successfully.
```

------

# 🖼️ 七、截图（非常关键）

你必须截图：

- Entra users page
- Intune devices
- policy settings
- VM enrolled screen
- error/fix evidence

放在：

```
/screenshots/
```

------

# 🧠 八、Architecture Diagram（加分点）

用这个结构画图：

```
User → Entra ID → Intune → Device (VM)
                    ↓
              Compliance Policy
                    ↓
              Monitoring
```

工具：

- draw.io（推荐）
- 或 Excalidraw

------

# 📄 九、README.md（模板）

你必须写这个：

```
# Enterprise IT Support Lab

## Overview
This project simulates a real-world enterprise IT environment using Microsoft Entra ID and Intune.

## Technologies
- Microsoft Entra ID
- Microsoft Intune
- Windows 10 VM

## Features
- User lifecycle management
- Device enrollment
- Compliance policies
- Troubleshooting scenarios

## Scenarios
- Outlook sync issue
- Device enrollment failure
- MFA lockout

## Learning Outcomes
- Identity management
- Endpoint management
- Enterprise troubleshooting

## Screenshots
See /screenshots folder
```

------

# 🚀 十、你完成后的“面试效果”

你可以这样说：

> I built a simulated enterprise environment using Entra ID and Intune to practice real-world IT support scenarios including device enrollment, identity management, and troubleshooting.

------

# 💡 十一、关键成功标准（非常重要）

这个项目成功的标准不是“能跑”，而是：

## ✔ 有结构

## ✔ 有截图

## ✔ 有 troubleshooting

## ✔ 有 documentation

## ✔ 像真实 IT support case

------

# ⚠️ 最重要提醒（很多人做错）

不要：

- 只点界面不记录
- 没有 GitHub
- 没有 scenario
- 没有 troubleshooting

要：

- 像“写真实工作日志”

------

# 👉 如果你下一步想加速

我可以帮你继续做：

### ✔ Project 2（Azure Lab）一步一步搭建

### ✔ Project 3（Automation）直接帮你做成“面试杀器”

### ✔ GitHub README高级版本（HR一看就加分）

### ✔ 面试回答模板（这个项目怎么讲最强）



# 🖥️ Incident Report: [Issue Title]

---

## 📌 1. Summary (问题概述)

Brief description of the issue:

User reported [brief issue description].

Example:
User was unable to log into Outlook and access email services.

---

## 👤 2. Affected User / System

- User: [username]
- Device: [device name / VM]
- Department: [HR / Finance / Test Lab]
- Location: [if applicable]

---

## 🚨 3. Problem Description

Detailed explanation of the issue:

- When did it happen?
- What error was shown?
- Impact on user/business?

Example:
User reported Outlook repeatedly prompting for password and failing to sync emails.

---

## 🔍 4. Investigation Steps

### Step 1: Check identity status (Entra ID)

Checked user account status in Microsoft Entra ID.

![Entra ID User Status](../screenshots/entra-user-status.png)

---

### Step 2: Check device status (Intune)

Verified device enrollment status in Intune portal.

![Intune Device Status](../screenshots/intune-device-status.png)

---

### Step 3: Check service health (Exchange Online / M365)

Checked Microsoft 365 service health dashboard.

![Service Health](../screenshots/service-health.png)

---

### Step 4: Reproduce issue (Client side)

Attempted login from Windows VM to reproduce issue.

![Login Error](../screenshots/outlook-login-error.png)

---

## 🧠 5. Root Cause Analysis

The issue was caused by:

- [e.g. expired credentials / device not enrolled / policy misconfiguration]

Example:
Device was not properly enrolled in Intune, causing authentication policy mismatch.

---

## 🛠️ 6. Resolution (Fix Applied)

Actions taken:

- Re-enrolled device into Intune
- Reset user authentication
- Triggered sync from endpoint
- Reconfigured Outlook profile

---

## ✅ 7. Result / Outcome

- Issue resolved successfully
- User regained access to Outlook
- Device now compliant in Intune
- No further incidents reported

---

## 🔁 8. Preventive Actions (Very Important ⭐)

To prevent recurrence:

- Enforced Intune auto-enrollment policy
- Verified Conditional Access settings
- Documented troubleshooting steps
- Monitored device compliance

---

## 📸 9. Evidence (Optional Summary Index)

| Screenshot               | Description         |
| ------------------------ | ------------------- |
| entra-user-status.png    | User account status |
| intune-device-status.png | Device enrollment   |
| outlook-login-error.png  | Error reproduction  |

(All screenshots stored in `/screenshots` folder)

---

## 📚 10. Skills Demonstrated

- Microsoft Entra ID (Azure AD)
- Microsoft Intune
- Microsoft 365 troubleshooting
- Endpoint management
- Incident troubleshooting
- Root cause analysis

---

## 🧾 11. Notes

This incident was simulated in a lab environment for IT support training and portfolio demonstration purposes.