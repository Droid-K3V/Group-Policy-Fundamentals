# Group Policy Fundamentals Project
Windows Server 2019 * Windows 10 * Active Directory * GPO Hardening

## 📕 Overview
This project builds a functional Active Directory domain with a Windows 10 workstation and implements core Group Policy objects used in real enterprise
environments. The goal was to design, deploy, and verify security-focused GPOs while documenting each step for professional review.

## 🧪 Lab Architecture
- **DC01** - Windows Server 2019 Domain Controller
- **WIN10-Client** - Windows 10 Pro workstation
- **Domain:** KEVINLAB.local
- **Test User:** mbrown (standard domain user)
- **Admin User:** Kevin (domain admin)

## 💻 GPOs Implemented
## 📃 1. Default Domain Policy (Password Policy)
- Minimum password length
- Maximum password age
- Password history
- Complexity requirements

## 🔒 2. Account Lockout Policy
- Lockout threshold
- Lockout duration
- Reset counter

## ❌ 3. Local Administrator Restrictions
- Restricted Groups: Domain Admins only
- Removed local admin rights from standard users

## 🎋 4. Login Banner Policy
- Legal notice caption
- Legal notice text

## ✖️ 5. User Experience Restrictions
- Blocked Control Panel
- Blocked CMD
- Blocked Registry Editor
- Removed Run menu
- Removed access to system settings

## 📄 6. Desktop Wallpaper Policy
- Enforced a domain-wide wallpaper for standard users
- Wallpaper stored in SYSVOL for universal access

## ✅ Verification
All GPOs were tested using **KEVINLAB\mbrown** to ensure correct user-side policy application.

## 🖥️ gpupdate
Policies refreshed using:
'gpupdate /force'

## 📝 Troubleshooting Notes
- Initial logon restrictions blocked all users; resolved by removing "Deny log on locally" from the Local Administrator Restrictions GPO.
- Wallpaper did not apply to admin accounts (expected behavior); verified successfully using standard user mbrown.
- SYSVOL path required exact domain spelling for wallpaper GPO to function.

## 🧠 What I learned
- How to design and link GPOs to the correct OUs
- How to troubleshoot GPO conflicts and logon rights
- How SYSVOL replication and UNC paths affect policy delivery
- How to validate GPOs using gpresult and local group membership
- How to document a fully AD/GPO project for professional review

## 📋 Screenshots
All screenshots are included in the **/Screenshots** folder and referenced throughout this README
