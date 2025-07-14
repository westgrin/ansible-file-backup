# Mini Project - Backup and Restore Files on a Linux Server using Ansible

## Project Overview
This project automates file backup and restoration on an Ubuntu server (54.227.3.228) using Ansible playbooks, backing up `/var/www/mywebsite` to `/backup`, building on previous projects (Jul 8-14, 2025).

## Setup
- Initiated on Jul 14, 2025, 2:40 PM WAT.
- Used WSL Ubuntu, VS Code, and Git Bash in `/mnt/c/Users/User/Documents/Workspace/ansible-file-backup`.
- System: 2 CPUs, 2GB free memory, 20GB free disk space.
- Target: AWS EC2 instance (Ubuntu 22.04, IP: 54.227.3.228).

## Execution Steps
1. **Confirm Prerequisites**:
   - Verified Ansible and SSH access to `ubuntu@54.227.3.228`.
   - Used `default` security group (`sg-06121807c5f142cf8`) allowing all traffic.
   - [Screenshot: `ansible_version_output_local.png` - Shows Ansible version.]
   - [Screenshot: `ssh_access_output_local.png` - Shows SSH to target.]
   - [Screenshot: `target_files_output_local.png` - Shows `/var/www/mywebsite` files.]
2. **Set Up Inventory**:
   - Created `inventory.ini` for Ubuntu target.
   - [Screenshot: `ansible_ping_output_local.png` - Shows ping response.]
3. **Backup Files**:
   - Ran `backup.yml` to back up `/var/www/mywebsite` to `/backup`.
   - [Screenshot: `ansible_backup_run_output_local.png` - Shows playbook run.]
   - [Screenshot: `backup_verification_output_local.png` - Shows `/backup` contents.]
4. **Restore Files**:
   - Ran `restore.yml` to restore files to `/var/www/mywebsite`.
   - [Screenshot: `pre_restore_output_local.png` - Shows empty `/var/www/mywebsite`.]
   - [Screenshot: `ansible_restore_run_output_local.png` - Shows playbook run.]
   - [Screenshot: `restore_verification_output_local.png` - Shows restored files.]
5. **Verify Website**:
   - Accessed `http://54.227.3.228` to confirm Nginx functionality.
   - [Screenshot: `nginx_curl_output_local.png` - Shows curl output.]
   - [Screenshot: `nginx_website_output_local.png` - Shows browser page.]
6. **Side Hustle Task**:
   - Automated backup with GitHub Actions.
   - Pushed to `https://github.com/westgrin/ansible-file-backup`.
   - [Screenshot: `github_actions_ansible_run_local.png` - Shows workflow run.]
7. **Clean Up (Optional)**:
   - Created `cleanup_backup.yml` to remove `/backup`.
   - Destroyed EC2 instance (if applicable).
   - [Screenshot: `terraform_destroy_output_local.png` - Shows destroy output.]

## Learning Summary
This project advanced my Ansible skills, building on Nginx deployment (Jul 14, 2025). It reinforced playbook creation for backup and restore tasks.

## Tools Used
- **WSL Ubuntu Terminal**: For Ansible and SSH commands.
- **VS Code**: For editing playbooks and `README.md`.
- **Git Bash**: For GitHub operations.
- **GitHub Actions**: For automation.
- **Ansible**: For file backup and restore.
- **Terraform**: For target node management.

## Project Deliverables
- **Documentation**: This `README.md` with steps and learning summary.
- **Screenshots**:
  - `ansible_version_output_local.png`
  - `ssh_access_output_local.png`
  - `target_files_output_local.png`
  - `ansible_ping_output_local.png`
  - `ansible_backup_run_output_local.png`
  - `backup_verification_output_local.png`
  - `pre_restore_output_local.png`
  - `ansible_restore_run_output_local.png`
  - `restore_verification_output_local.png`
  - `nginx_curl_output_local.png`
  - `nginx_website_output_local.png`
  - `github_actions_ansible_run_local.png`
  - `terraform_destroy_output_local.png` (if applicable)
- **Script Link**: [GitHub Repository](https://github.com/westgrin/ansible-file-backup)

## Local Development Instructions
1. Clone repository: `git clone https://github.com/westgrin/ansible-file-backup.git`
2. Install Ansible: `sudo apt install ansible -y`
3. Configure inventory: Edit `inventory.ini` with target details
4. Run playbooks: `ansible-playbook -i inventory.ini backup.yml` and `restore.yml`
5. Verify: Check `/backup` and `/var/www/mywebsite`

## Troubleshooting
- Ensured SSH access with `ssh ubuntu@54.227.3.228`.
- Used `default` security group allowing all traffic.
- Fixed playbook errors by verifying file paths.
- Set DNS to `8.8.8.8` for network issues.
- Verified system resources with `lscpu`, `free -h`, `df -h`.

## Conclusion
This project successfully automated file backup and restoration, enhancing my automation skills for server management.