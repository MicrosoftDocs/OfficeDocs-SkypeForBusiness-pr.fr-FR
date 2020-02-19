---
title: Conditions préalables à la configuration de la prise d’appel de groupe et droits de l’utilisateur
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
ms.openlocfilehash: 6344dea7e4ba4273905af6549ced3f900922e4e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Conditions préalables à la configuration de la prise d’appel de groupe et droits de l’utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

La prise d’appel de groupe est une fonctionnalité de gestion des appels installée par défaut lorsque vous déployez voix entreprise. Cette rubrique décrit ce que vous devez avoir en place avant de pouvoir configurer la prise d’appel de groupe et les droits d’utilisateur dont vous avez besoin pour effectuer des tâches de configuration.

Cette section suppose que vous avez lu la documentation de planification relative à la prise d’appel de groupe (voir [planification de la prise d’appel de groupe dans Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Conditions préalables à la configuration de la prise d’appel de groupe

La prise d’appel de groupe requiert les composants suivants :

  - service d’application

  - application de parcage d’appel

Ces composants sont installés automatiquement lorsque vous déployez voix entreprise.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Droits d’utilisateur de configuration de prise d’appel de groupe

Vous utilisez les outils d’administration suivants pour configurer la prise d’appel de groupe :

  - Lync Server Management Shell

  - Outil de kit de ressources SEFAUtil

Utilisez Lync Server Management Shell pour créer et gérer des groupes de prise d’appel dans la table des orbites de parcage d’appel. Utilisez l’outil Kit de ressources SEFAUtil pour affecter un groupe de prise d’appel et activer la prise d’appel de groupe pour les utilisateurs ou pour désactiver la prise d’appel de groupe pour les utilisateurs.

La configuration de la prise d’appel de groupe nécessite l’un des rôles d’administrateur suivants, en fonction de la tâche :

  - **CsVoiceAdministrator :** Ce rôle d’administrateur permet de créer, de configurer et de gérer toutes les stratégies et les paramètres liés à la voix.

  - **CsUserAdministrator :** Ce rôle d’administrateur peut activer la prise d’appel de groupe pour les utilisateurs. Il dispose aussi d’un accès en lecture seule à toutes les configurations de voix.

  - **CsServerAdministrator :** Ce rôle d’administrateur peut gérer, surveiller et dépanner les serveurs et les services.

  - **CsAdministrator :** Ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator, CsServerAdministrator et CsUserAdministrator.

<div>


> [!NOTE]
> Pour plus d’informations sur les droits d’administration, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification.



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

