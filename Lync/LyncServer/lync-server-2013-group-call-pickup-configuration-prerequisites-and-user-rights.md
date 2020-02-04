---
title: Conditions préalables et droits d’utilisateur pour la configuration des appels de groupe
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Configuration requise pour les appels de groupe et droits d’utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

La cueillette de groupe est une fonctionnalité de gestion des appels qui est installée par défaut lors du déploiement d’Enterprise Voice. Cette rubrique décrit ce que vous devez mettre en place avant de pouvoir configurer la collecte d’appels de groupe et les droits d’utilisateur nécessaires à l’exécution des tâches de configuration.

Cette section part du principe que vous avez lu la documentation de planification liée au regroupement d’appels de groupe (voir [planification d’appels de groupe dans Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Configuration requise pour la configuration des appels de groupe

La collecte des appels de groupe nécessite les composants suivants :

  - service d’application

  - application de parcage d’appel

Ces composants sont installés automatiquement lorsque vous déployez Enterprise Voice.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Droits d’utilisateur de configuration des appels de groupe

Vous pouvez utiliser les outils d’administration suivants pour configurer la cueillette des appels de groupe :

  - Lync Server Management Shell

  - Outil du kit de ressources SEFAUtil

Utilisez Lync Server Management Shell pour créer et gérer des groupes de captures d’appels dans la table de stationnement d’appel. Utilisez l’outil de kit de ressources SEFAUtil pour attribuer un groupe de cueillette d’appel et activer le regroupement d’appels de groupe pour les utilisateurs ou pour désactiver la sélection d’appels de groupe pour les utilisateurs.

La configuration de la cueillette de groupe nécessite l’un des rôles d’administration suivants, en fonction de la tâche :

  - **CsVoiceAdministrator :** Ce rôle d’administrateur peut créer, configurer et gérer l’ensemble des stratégies et paramètres relatifs à la voix.

  - **CsUserAdministrator :** Ce rôle d’administrateur peut activer le prélèvement d’appels de groupe pour les utilisateurs. Ce rôle d’administrateur dispose également d’un accès en lecture seule à toutes les configurations vocales.

  - **CsServerAdministrator :** Ce rôle d’administrateur peut gérer, surveiller et résoudre les problèmes liés aux serveurs et services.

  - **CsAdministrator :** Ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.

<div>


> [!NOTE]
> Pour plus d’informations sur les droits d’administration, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur les rôles dans Lync Server 2013</A> dans la documentation de planification.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement d’Enterprise Voice dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planifier les fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

