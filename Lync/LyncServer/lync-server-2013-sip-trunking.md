---
title: 'Lync Server 2013 : Jonction SIP'
TOCTitle: Jonction SIP
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398619(v=OCS.15)
ms:contentKeyID: 49297841
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-08-13_

Le protocole SIP (Session Initiation Protocol) sert à initier et à gérer les sessions de communications Voix sur IP (VoIP) pour le service téléphonique de base et d’autres services de communication en temps réel, tels que messagerie instantanée, conférence, détection de présence et multimédia. Cette section fournit des informations de planification pour l’implémentation de *jonctions SIP* , un type de connexion SIP qui s’étend au-delà des limites de votre réseau local.

## Qu’est-ce que la jonction SIP ?

Une jonction SIP est une connexion IP qui établit un lien de communications SIP entre votre organisation et un fournisseur de services de téléphonie Internet (ITSP) à l’extérieur de votre pare-feu. En règle générale, une jonction SIP sert à connecter le site central de votre organisation à un fournisseur de services de téléphonie Internet (ITSP). Dans certains cas, vous pouvez également décider d’utiliser la jonction SIP pour connecter votre site de succursale à un fournisseur de services de téléphonie Internet (ITSP).

## Différences entre les jonctions SIP et les connexions SIP directes

Le terme *jonction* est dérivé de la technologie de commutation. Il fait référence à une ligne physique dédiée qui connecte les équipements téléphoniques de commutation. Tout comme leurs prédécesseurs (les jonctions de multiplexage temporel \[TDM\]), les jonctions SIP sont des connexions entre deux réseaux SIP distincts, l’entreprise Lync Server 2013 et le fournisseur de services de téléphonie Internet. Contrairement aux jonctions de commutation, les jonctions SIP sont des connexions virtuelles pouvant être établies sur n’importe quel type de connexion de jonction SIP pris en charge. Pour plus d’informations sur les types de connexion pris en charge, reportez-vous à [Implémentation d’une jonction SIP dans Lync Server 2013](lync-server-2013-how-do-i-implement-sip-trunking.md).

En revanche, les connexions SIP directes sont des connexions SIP qui ne franchissent pas les limites du réseau local (c’est-à-dire qu’elles se connectent à une passerelle RTC ou à un PBX dans votre réseau interne). Pour plus d’informations sur l’utilisation des connexions SIP directes avec Lync Server 2013, reportez-vous à [Connexions SIP directes dans Lync Server 2013](lync-server-2013-direct-sip-connections.md).

## Dans cette section

  - [Vue d’ensemble d’une jonction SIP dans Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md)

  - [Implémentation d’une jonction SIP dans Lync Server 2013](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Composants et topologies utilisés pour une jonction SIP dans Lync Server 2013](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Jonction SIP de site de succursale dans Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)

  - [Liste de vérification du déploiement de la jonction SIP pour Lync Server 2013](lync-server-2013-sip-trunk-deployment-checklist.md)

