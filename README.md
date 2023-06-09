# Exemples Ansible

Ce repo est un exemple d'arborescence de projet Ansible.

## Description des fichiers et dossiers

Liste des fichiers

```
├── group_vars/             <-- Variables par groupe
├── host_vars/              <-- Variables par host
├── inventory/              <-- Dossier contenant plusieurs inventaires pour différencier les environnements
│   ├── production.yml      <-- Inventaires en production
│   └── staging.yml         <-- Inventaires en test
├── site.yml                <-- Playbook principale faisant appel aux autres playbooks
├── roles/                  <-- Dossier contenant tout les rôles
│   └── nginx/              <-- Exemples de rôle appelé nginx (ex: ce rôle pourrait installer un serveur nginx)
│       ├── defaults/       
│       │   └── main.yml    <-- Fichier contenant les variables par défauts du rôle, ces variables peuvent être modifié 
│       ├── files/          <-- Dossier contenant des fichiers qui ne seront pas modifiés (ex: avec le module copy)
│       ├── handlers/        
│       │   └── main.yml    <-- Fichier qui contient les tâches pouvant être appelé (ex: dans notre exemple une tâche de restart du service nginx)
│       ├── meta/
│       │   └── main.yml    <-- Meta description du rôle
│       ├── tasks/          
│       │   └── main.yml    <-- Fichier contenant les tâches exécutées pour ce rôle (ex: dans notre exemple l'installation de nginx)
│       ├── templates/      <-- Dossier contenant des templates qui seront modifiés (template jinja2 avec extension .j2, ex: dans notre exemple la page index)
│       ├── tests/          <-- Dossier contenant un inventaire et un playbook afin d'avoir un environnement de tests pour le rôle
│       └── vars/           <-- Variables associées au rôle
└── webservers.yml          <-- Il faut mieux créer un playbook par groupe afin de modularisé au plus possible (ex: ici nous avons un groupe web_servers)
```