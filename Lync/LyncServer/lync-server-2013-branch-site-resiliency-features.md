---
title: 'Lync Server 2013 : fonctionnalités de résistance de site de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf5f477bcb5620112789a338339b6ca00bf9c3c5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Fonctionnalités de résistance de site de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-10_

Si vous fournissez la résistance des sites de succursale et que la connexion WAN d’un site de succursale à un site central échoue si ce dernier est inaccessible, les fonctionnalités vocales suivantes seront encore disponibles :

<div>


  - Appels PSTN entrants et sortants

  - Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

  - Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

  - Messagerie instantanée entre deux utilisateurs

  - Services de transfert d’appel, de sonnerie simultanée des points de terminaison, de délégation d’appel et d’appel d’équipe, mais seulement si le délégant et le délégué (par exemple, un responsable et l’administrateur de ce dernier), ou tous les membres de l’équipe, sont configurés sur le même site.

  - Enregistrements des détails des appels (CDR)

  - Conférence rendez-vous par réseau téléphonique commuté (PSTN) avec standard automatique de conférence

  - Les fonctionnalités de messagerie vocale, si vous configurez les paramètres de réacheminement de la messagerie vocale. (Pour plus d’informations, consultez la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Authentification et autorisations des utilisateurs

Les fonctionnalités suivantes seront disponibles uniquement si votre solution de résilience est un déploiement Lync Server complet sur le site de succursale :

  - messagerie instantanée, conférence A/V et web

  - routage basé sur la présence et Ne pas déranger (DND (quand les appels ne sonnent pas sur les postes dont le statut est Ne pas déranger)

  - Mise à jour des paramètres de transfert d’appel

  - Application Response Group et application parcage d’appel

  - Mise en service des nouveaux téléphones et clients, mais uniquement si les services de domaine Active Directory sont présents sur le site de succursale.

  - Enhanced 9-1-1 (E9-1-1)
    
    Si E9-1-1 est déployé et que la jonction SIP sur le site central n’est pas disponible car la liaison de réseau étendu est inactive, le Survivable Branch Appliance achemine les appels E9-1-1 vers la passerelle de succursale locale. Pour activer cette fonctionnalité, les stratégies de voix des utilisateurs du site de succursale doivent acheminer les appels vers la passerelle locale en cas de panne du réseau étendu (WAN).

<div>


> [!NOTE]  
> SBA (Survivable Branch Office) n’est pas pris en charge pour XMPP. Les utilisateurs hébergés dans une configuration SBA ne peuvent pas envoyer de messages instantanés ou voir la présence avec des contacts XMPP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

