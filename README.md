# DO101-apps

Apps for the DO101 course.
---
- name: Instalacja Visual Studio Code na Fedora
  hosts: all
  become: yes

  tasks:
    - name: Dodaj repozytorium Visual Studio Code
      get_url:
        url: https://packages.microsoft.com/yumrepos/vscode
        dest: /etc/yum.repos.d/vscode.repo
        mode: '0644'

    - name: Dodaj Microsoft GPG key
      rpm_key:
        state: present
        key: https://packages.microsoft.com/keys/microsoft.asc

    - name: Zainstaluj Visual Studio Code
      dnf:
        name: code
        state: present
