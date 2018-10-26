---
title: Enregistrements DNS (Domain Name System) requis
TOCTitle: Enregistrements DNS (Domain Name System) requis
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398386(v=OCS.15)
ms:contentKeyID: 49297305
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enregistrements DNS (Domain Name System) requis

 

_**Dernière rubrique modifiée :** 2012-06-18_

Pour déployer Lync Server, vous devez créer des enregistrements DNS (Domain Name System) qui permettent la découverte des clients et des serveurs, ainsi que, de façon facultative, la prise en charge de la connexion automatique des clients si votre organisation le permet.

Lync Server utilise DNS (Domain Name System) des façons suivantes :

  - pour détecter les serveurs ou pools internes pour les communications de serveur à serveur ;

  - pour permettre aux clients de détecter le pool de serveurs frontaux ou serveur Standard Edition utilisé pour diverses transactions SIP ;

  - pour permettre aux périphériques de communications unifiées (UC, Unified Communications) qui ne sont pas connectés de détecter le pool de serveurs frontaux ou serveur Standard Edition exécutant le service web de mise à jour des périphériques, d’obtenir des mises à jour et d’envoyer des journaux ;

  - pour permettre aux serveurs et clients externes de se connecter aux serveurs Edge ou au proxy inverse HTTP afin d’utiliser les fonctions de messagerie instantanée et de conférence ;

  - pour permettre aux périphériques de communications unifiées externes de se connecter au service web de mise à jour des périphériques via les serveurs Edge ou le proxy inverse HTTP et d’obtenir des mises à jour ;

  - pour permettre aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des appareils.

## Dans cette section

  - [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Configuration DNS requise pour les pools frontaux](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Enregistrements DNS requis pour les serveurs Standard Edition Server](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Enregistrements DNS requis pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Enregistrements DNS requis pour la connexion automatique des clients dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Exigences relatives au système DNS pour la mobilité](lync-server-2013-dns-requirements-for-mobility.md)

  - [Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md)

