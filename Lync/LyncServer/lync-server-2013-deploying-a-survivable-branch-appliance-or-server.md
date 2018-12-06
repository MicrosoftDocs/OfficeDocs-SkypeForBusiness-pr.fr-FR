---
title: "Lync Server 2013 : Dépl. d’un Surv. Branch Appl. ou d’un Surv. Branch Serv."
TOCTitle: Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398849(v=OCS.15)
ms:contentKeyID: 49298835
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-12-10_

La résistance de Voix Entreprise concerne la résistance d’un site de succursale. Elle permet aux utilisateurs d’un tel site de continuer à utiliser le service Voix Entreprise au cas où la liaison au site central ne serait plus disponible.

Pour les sites des petites et moyennes succursales (de 25 à 1 000 utilisateurs), nous conseillons de déployer un Survivable Branch Appliance qui acheminera les appels sur le réseau téléphonique commuté (RTC) en utilisant sa passerelle RTC intégrée ou une jonction SIP à un fournisseur de services téléphonique. Un Survivable Branch Appliance est un dispositif tiers qui inclut un serveur lame exécutant le système d’exploitation Windows Server 2008 R2, le serveur d’inscriptions Lync Server 2013, le logiciel du serveur de médiation et une passerelle RTC dans un seul et même châssis d’appliance.

Pour les sites de succursale de 1 000 à 5 000 utilisateurs, sans réseau étendu résistant, nous conseillons de connecter un serveur Survivable Branch Server à une passerelle RTC ou via une jonction SIP à un fournisseur de services téléphoniques. Un serveur Survivable Branch Server est un ordinateur Windows Server sur lequel sont installés le serveur d’inscriptions et le logiciel du serveur de médiation.

> [!NOTE]  
> Pour les sites de succursale de plus de 5 000 utilisateurs et des administrateurs Lync Server dédiés, nous conseillons un déploiement complet de Lync Server 2013, distinct de celui du site central.<br />
Pour plus d’informations sur le choix de la solution de résistance la plus adaptée aux sites de succursale de votre entreprise, notamment les conditions préalables ainsi que les points à prendre en considération en matière de planification, reportez-vous à <a href="lync-server-2013-branch-site-resiliency-requirements.md">Configuration requise pour la résistance des sites de succursale pour Lync Server 2013</a> dans la documentation de planification.

## Dans cette section

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013 - Tâches pour un site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server sur un site de succursale avec Lync Server 2013 - tâche de site de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configuration des utilisateurs pour la résistance de sites de succursale dans Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Annexes : Survivable Branch Appliances et serveurs Survivable Branch Server dans Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

## Voir aussi

#### Autres ressources

[Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md)

