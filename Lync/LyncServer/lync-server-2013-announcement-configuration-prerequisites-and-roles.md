---
title: 'Lync Server 2013 : conditions préalables et rôles de configuration d’annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dde28cac806b517a410f5edfa7ecbcf19176ed4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Conditions préalables et rôles de configuration d’annonce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Annonce est une fonctionnalité de gestion des appels voix entreprise. Cette rubrique décrit ce que vous devez avoir en place avant de pouvoir configurer une annonce et les attributions de rôles dont vous avez besoin pour effectuer des tâches de configuration.

Cette section suppose que vous avez lu la documentation de planification relative à annonce (voir [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Conditions préalables de configuration d’annonce

L’application d’annonce requiert les composants suivants :

  - Service d’application

  - Application Response Group

  - Magasin de fichiers, pour conserver les fichiers audio

Tous ces composants sont installés par défaut lorsque vous déployez Voix Entreprise.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Rôles de configuration d’annonce

Vous pouvez utiliser les outils administratifs suivants pour configurer les annonces :

  - Panneau de configuration Lync Server

  - Lync Server Management Shell

La configuration de l’application d’annonce nécessite l’un des rôles d’administrateur suivants :

  - **CsVoiceAdministrator**   ce rôle d’administrateur peut créer, configurer et gérer toutes les stratégies et les paramètres liés à la voix, y compris les paramètres d’annonce.

  - **CsServerAdministrator**   ce rôle d’administrateur peut gérer, surveiller et dépanner les serveurs et les services, et configurer tous les paramètres d’annonce.

  - **CsAdministrator**   ce rôle d’administrateur peut effectuer toutes les tâches d’administration et modifier tous les paramètres.

  - **CsViewOnlyAdministrator**   ce rôle d’administrateur peut afficher le déploiement pour surveiller l’intégrité du déploiement.

<div>


> [!NOTE]  
> Pour plus d’informations sur les droits d’administrateur, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de voix entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

