---
title: 'Lync Server 2013 : Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca6fae79854356951701eaf6040fb436e787acd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-10_

Le mode de résilience d’entreprise résilient désigne la résilience du site de succursale, c’est-à-dire la possibilité de fournir un service voix entreprise continu aux utilisateurs de sites de succursales en cas d’indisponibilité du lien vers le site central.

Pour les petites et moyennes succursales (sites de succursales avec 25 à 1 000 utilisateurs), nous vous recommandons de déployer une application de succursales survivant, qui met fin aux appels RTC (réseau téléphonique commuté) par le biais de sa passerelle RTC intégrée ou d’un trunking SIP à un téléphone. prestataire de services. Une branche Survivable est un périphérique tiers qui inclut un serveur Blade exécutant le système d’exploitation Windows Server 2008 R2, le Bureau d’enregistrement Lync Server 2013, le logiciel serveur de médiation et une passerelle RTC, le tout dans un seul châssis d’appareil.

Pour les sites de succursales avec 1 000 à 5 000 et sans réseau étendu fiable, nous recommandons un serveur de succursale survivant connecté à une passerelle PSTN ou un Trunk SIP à un fournisseur de services de téléphonie. Un serveur de succursales survivant est un ordinateur Windows Server sur lequel est installé le logiciel de bureau d’enregistrement et de médiation.

<div>


> [!NOTE]  
> Pour les sites de succursales ayant plus de 5 000 utilisateurs et les administrateurs Lync Server dédiés, nous vous recommandons d’utiliser un déploiement complet de Lync Server 2013, distinct de celui du site central.<BR>Pour plus d’informations sur le choix de la meilleure solution de résilience pour les sites de succursales au sein de votre organisation, notamment la configuration requise et les considérations en matière de planification, voir <A href="lync-server-2013-branch-site-resiliency-requirements.md">exigences de résilience de succursale pour Lync Server 2013</A> dans la documentation de planification.



</div>

<div>


> [!NOTE]  
> Les utilisateurs qui sont hébergés sur une unité de branchement Survivable Lync Server ne peuvent pas créer de nouvelles salles de conversation ou afficher la carte de la salle pour les salles existantes.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013 - Tâches pour un site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server sur un site de succursale avec Lync Server 2013 - tâche de site de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configuration des utilisateurs pour la résistance de sites de succursale dans Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Annexes : Survivable Branch Appliances et serveurs Survivable Branch Server dans Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

