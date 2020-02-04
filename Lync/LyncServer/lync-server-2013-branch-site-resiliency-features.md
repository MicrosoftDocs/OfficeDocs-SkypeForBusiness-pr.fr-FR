---
title: 'Lync Server 2013 : Fonctionnalités de résistance de site de succursale'
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
ms.openlocfilehash: a490de36322914235346cbc141784aab2c24f2ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Fonctionnalités de résistance de site de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-10_

Si vous fournissez la résistance des sites de succursale et que la connexion de réseau étendu d’un site de succursale à un site central échoue si ce dernier est inaccessible, les fonctionnalités vocales suivantes seront encore disponibles :

<div>


  - Appels RTC entrants et sortants

  - Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents

  - Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert

  - Messagerie instantanée entre deux utilisateurs

  - Services de transfert d’appel, de sonnerie simultanée des points de terminaison, de délégation d’appel et d’appel d’équipe, mais seulement si le délégant et le délégué (par exemple, un responsable et l’administrateur de ce dernier), ou tous les membres de l’équipe, sont configurés sur le même site.

  - Enregistrements des détails des appels (CDR)

  - Conférence rendez-vous par réseau téléphonique commuté (RTC) avec standard automatique de conférence

  - Fonctionnalités de messagerie vocale si vous configurez les paramètres de réacheminement de la messagerie vocale. (Pour plus d’informations, consultez [Configuration requise pour la résilience du site de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Authentification et autorisations des utilisateurs

Les fonctionnalités suivantes ne seront disponibles que si votre solution de résilience est un déploiement de Lync Server à une échelle complète sur le site de la succursale :

  - Messagerie instantanée, conférence A/V et web

  - Routage basé sur la présence et Ne pas déranger (DND (quand les appels ne sonnent pas sur les postes dont le statut est Ne pas déranger)

  - Mise à jour des paramètres de transfert d’appel

  - Application de groupe de réponse et application de parc d’appels

  - Attribution de nouveaux téléphones et clients, mais uniquement si les services de domaine Active Directory sont présents au niveau du site de succursale.

  - Enhanced 9-1-1 (E9-1-1)
    
    Si E9-1-1 est déployé et que le Trunk SIP sur le site central n’est pas disponible parce que la liaison WAN est en panne, l’application branche Survivable achemine les appels E9-1-1 vers la passerelle locale. Pour activer cette fonctionnalité, les stratégies de voix des utilisateurs du site de succursale doivent acheminer les appels vers la passerelle locale en cas de panne du réseau étendu (WAN).

<div>


> [!NOTE]  
> SBA (survivable branch office) n’est pas pris en charge pour XMPP. Les utilisateurs hébergés dans des configurations SBA ne seront pas en mesure d’envoyer des messages instantanés ou de voir la présence de contacts XMPP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

