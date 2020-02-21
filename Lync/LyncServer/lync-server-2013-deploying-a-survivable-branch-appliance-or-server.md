---
title: 'Lync Server 2013 : déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server'
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
ms.openlocfilehash: 63e3379e2c703df1d4ce66eda0942befb1569c7e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-10_

La voix entreprise fiable fait référence à la résistance des sites de succursale, c’est-à-dire à la possibilité de fournir un service voix entreprise continu aux utilisateurs de sites de succursales, si le lien vers le site central devient indisponible.

Pour les sites de succursale de petite et moyenne taille (sites de succursale avec 25 à 1 000 utilisateurs), nous vous recommandons de déployer un Survivable Branch appliance, qui mettra fin aux appels de réseau téléphonique commuté (PSTN) à l’aide de sa passerelle PSTN intégrée ou d’une jonction SIP vers un téléphone. fournisseur de services. Un Survivable Branch Appliance est un périphérique tiers qui inclut un serveur de Blades exécutant le système d’exploitation Windows Server 2008 R2, le serveur d’inscriptions Lync Server 2013, le logiciel de serveur de médiation et une passerelle PSTN, tous dans un seul châssis d’appareil.

Pour les sites de succursale avec 1 000 à 5 000 utilisateurs et pas de réseau étendu (WAN) résilient, nous recommandons un serveur Survivable Branch Server connecté à une passerelle PSTN ou une jonction SIP avec un fournisseur de services téléphoniques. Un serveur Survivable Branch Server est un ordinateur Windows Server sur lequel est installé le logiciel de serveur d’inscriptions et de médiation.

<div>


> [!NOTE]  
> Pour les sites de succursale comportant plus de 5 000 utilisateurs et des administrateurs Lync Server dédiés, nous vous recommandons d’utiliser un déploiement complet de Lync Server 2013, distinct de celui du site central.<BR>Pour plus d’informations sur le choix de la meilleure solution de résilience pour les sites de succursale de votre organisation, notamment les conditions préalables et les considérations de planification, voir <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site Resiliency Requirements for Lync Server 2013</A> dans la documentation de planification.



</div>

<div>


> [!NOTE]  
> Les utilisateurs hébergés sur une appliance Survivable Branch Lync Server ne peuvent pas créer de nouvelles salles de conversation ni afficher la carte de salle pour les salles existantes.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013-tâches de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec la tâche Lync Server 2013-Branch site](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Configuration des utilisateurs pour la résistance des sites de succursale dans Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Utilisateurs domestiques sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Annexes : Survivable Branch Appliances and Servers dans Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de Microsoft Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

