---
title: 'Lync Server 2013 : Fonctionnalités de résistance de site de succursale'
TOCTitle: Fonctionnalités de résistance de site de succursale
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398715(v=OCS.15)
ms:contentKeyID: 49298031
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fonctionnalités de résistance de site de succursale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-10_

Si vous fournissez la résistance des sites de succursale et que la connexion de réseau étendu d’un site de succursale à un site central échoue si ce dernier est inaccessible, les fonctionnalités vocales suivantes seront encore disponibles :


  - Appels RTC entrants et sortants

  - Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

  - Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

  - Messagerie instantanée entre deux utilisateurs

  - Services de transfert d’appel, de sonnerie simultanée des points de terminaison, de délégation d’appel et d’appel d’équipe, mais seulement si le délégant et le délégué (par exemple, un responsable et l’administrateur de ce dernier), ou tous les membres de l’équipe, sont configurés sur le même site.

  - Enregistrements des détails des appels (CDR)

  - Conférence rendez-vous par réseau téléphonique commuté (RTC) avec standard automatique de conférence

  - Fonctionnalités de messagerie vocale, si vous configurez les paramètres de réacheminement de messagerie vocale (Pour plus d’informations, reportez-vous à [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Authentification et autorisations des utilisateurs

Les fonctionnalités suivantes seront disponibles uniquement si votre solution de résistance est un déploiement complet de Lync Server sur le site de succursale :

  - messagerie instantanée, conférence A/V et web

  - routage basé sur la présence et Ne pas déranger (DND (quand les appels ne sonnent pas sur les postes dont le statut est Ne pas déranger)

  - Mise à jour des paramètres de transfert d’appel

  - application Response Group et application de parcage d’appel

  - Approvisionnement de nouveaux téléphones et clients, mais uniquement si les services de domaine Active Directory sont présents sur le site de succursale.

  - Enhanced 9-1-1 (E9-1-1)
    
    Si E9-1-1 est déployé et que la jonction SIP n’est pas disponible sur le site central en raison d’une défaillance de la liaison de réseau étendu, le Survivable Branch Appliance achemine alors les appels E9-1-1 vers la passerelle de la succursale locale. Pour activer cette fonctionnalité, les stratégies de voix des utilisateurs du site de succursale doivent acheminer les appels vers la passerelle locale en cas de panne du réseau étendu (WAN).

> [!NOTE]  
> SBA (survivable branch office) n’est pas pris en charge pour XMPP. Les utilisateurs hébergés dans des configurations SBA ne peuvent pas envoyer de messages instantanés ni voir la présence avec les contacts XMPP.
