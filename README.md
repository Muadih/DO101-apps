# DO101-apps

Apps for the DO101 course.
---
- name: Instalacja Google Chrome i Microsoft Edge na Fedora
  hosts: all
  become: yes

  tasks:

    - name: Dodaj repozytorium Google Chrome
      copy:
        dest: /etc/yum.repos.d/google-chrome.repo
        content: |
          [google-chrome]
          name=google-chrome
          baseurl=https://dl.google.com/linux/chrome/rpm/stable/x86_64
          enabled=1
          gpgcheck=1
          gpgkey=https://dl.google.com/linux/linux_signing_key.pub

    - name: Zainstaluj Google Chrome
      dnf:
        name: google-chrome-stable
        state: present

    - name: Dodaj repozytorium Microsoft Edge
      copy:
        dest: /etc/yum.repos.d/microsoft-edge.repo
        content: |
          [microsoft-edge]
          name=Microsoft Edge
          baseurl=https://packages.microsoft.com/yumrepos/edge
          enabled=1
          gpgcheck=1
          gpgkey=https://packages.microsoft.com/keys/microsoft.asc

    - name: Zainstaluj Microsoft Edge
      dnf:
        name: microsoft-edge-stable
        state: present

