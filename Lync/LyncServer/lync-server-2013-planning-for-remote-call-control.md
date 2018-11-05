---
title: 'Lync Server 2013 : Planification du contrôle d’appel distant'
TOCTitle: Planification du contrôle d’appel distant
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558658(v=OCS.15)
ms:contentKeyID: 49297479
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification du contrôle d’appel distant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-05_

Dans Lync Server 2013, la prise en charge des scénarios de contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones PBX (autocommutateur privé) en utilisant Lync 2013 sur leurs ordinateurs de bureau. Cette section décrit les fonctionnalités de contrôle d’appel distant et les conditions nécessaires au déploiement du contrôle d’appel distant.

L’intégration entre un PBX et Lync Server 2013 permet aux utilisateurs activés pour le contrôle d’appel distant d’utiliser l’interface utilisateur de Lync 2013 pour contrôler les appels sur leurs téléphones PBX des différentes façons suivantes :

> [!NOTE]  
> En définitive, les capacités de l’autocommutateur privé (PBX) qui héberge le téléphone PBX d’un utilisateur déterminent les fonctionnalités de contrôle d’appel distant mises à la disposition de cet utilisateur.

  - Passer un appel sortant

  - Répondre à un appel entrant

  - Répondre à un appel entrant avec un message instantané
    
    > [!NOTE]  
    > C’est-à-dire, lorsque le numéro de téléphone de l’appelant peut être associé à une adresse de messagerie instantanée figurant dans la liste d’adresses globale (GAL) de votre organisation ou dans la liste des contacts Lync de l’appelé, ou appartenant à l’organisation d’un partenaire fédéré.

  - Transférer un appel

  - Transférer un appel entrant

  - Mettre des appels en attente

  - Basculer entre plusieurs appels simultanés

  - Répondre à un deuxième appel pendant un appel en cours (c’est-à-dire, mise en attente d’un appel)

  - Composer des chiffres de numérotation en fréquences vocales (DTMF)

  - Dans la fenêtre de conversation, taper des notes dans le programme de prise de note Microsoft Office OneNote

Par ailleurs, lorsqu’un utilisateur est activé pour le contrôle d’appel distant, Lync 2013 fournit à l’utilisateur les informations d’appel suivantes :

  - Identification d’un appelant par son nom lorsque le numéro de téléphone de l’appelant est présent dans la liste des contacts d’un client de messagerie et de collaboration Microsoft Office Outlook de l’utilisateur pour lequel le contrôle d’appel distant est activé, dans la liste des contacts Lync ou la liste d’adresses globale de votre organisation.

  - Appels entrants et sortants précédents, enregistrés dans le dossier Historique des conversations d’Outlook.

  - Notifications d’appels manqués, envoyées vers le dossier Boîte de réception Outlook de l’utilisateur, mais uniquement générées si Lync est en cours d’exécution lors de la réception de l’appel entrant.

## Contrôle d’appel distant et Voix Entreprise

Même si les fonctionnalités de contrôle d’appel distant sont distinctes des fonctionnalités Voix Entreprise et que les utilisateurs ne peuvent pas être activés pour ces deux entités, Voix Entreprise fournit un sous-ensemble de fonctionnalités également accessibles aux utilisateurs activés pour le contrôle d’appel distant. Si Voix Entreprise est déployée, les utilisateurs activés pour le contrôle d’appel distant peuvent utiliser Lync pour accéder aux fonctionnalités Voix Entreprise suivantes :

  - Passer et recevoir des appels audio depuis/vers un autre client Lync

  - Prendre part à la partie audio d’une conférence qui a été créée par un utilisateur activé pour Voix Entreprise

## Dans cette section

  - [Tâches de déploiement du contrôle d’appel distant dans Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

