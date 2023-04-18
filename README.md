# Exemples Ansible

Ce repo est un exemple d'arborescence de projet Ansible.

## Description des fichiers et dossiers

```
├── group_vars/             <-- Variables par groupe
│ 
├── host_vars/              <-- Variables par host
│ 
├── inventory/              <-- Dossier contenant plusieurs inventaires pour différencier les environnements
│   ├── production.yml      <-- Inventaires en production
│   └── staging.yml         <-- Inventaires en test
│ 
├── main.yml                <-- Playbook principale faisant appel aux autres playbooks
│ 
├── README.md               
│ 
├── roles/                  <-- Dossier contenant tout les rôles
│   └── nginx/              <-- Exemples de rôle
│       ├── defaults/       
│       │   └── main.yml    <-- Fichier contenant les variables par défauts du rôle
│       ├── files/          <-- Dossier contenant des fichiers qui ne seront pas modifiés (ex: avec le module copy)
│       ├── handlers/        
│       │   └── main.yml    <-- Fichier qui contient les tâches pouvant être appelé grâce au module 'notify'
│       ├── meta/
│       │   └── main.yml    <-- Meta description du rôle
│       ├── README.md
│       ├── tasks/          
│       │   └── main.yml    <-- Fichier contenant les tâches exécutées pour ce rôle
│       ├── templates/      <-- Dossier contenant des templates qui seront modifiés (template jinja2 avec extension .j2 pour)
│       ├── tests/          <-- Dossier contenant un inventaire et un playbook afin d'avoir un environnement de tests pour le rôle
│       └── vars/           <-- Variable associés au rôle
│ 
└── web_servers.yml         <-- Il faut mieux créer un playbook par groupe afin de modularisé au plus possible
```