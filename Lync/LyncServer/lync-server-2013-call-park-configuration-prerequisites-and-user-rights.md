---
title: 'Lync Server 2013 : conditions préalables et droits d’utilisateur pour la configuration du parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39fd811a39a1221ec522c7ca3874d0de4f340b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Conditions préalables et droits d’utilisateur pour la configuration du parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-10_

Le parcage d’appel est une fonctionnalité de gestion des appels installée par défaut lorsque vous déployez voix entreprise. Cette rubrique décrit ce que vous devez avoir en place avant de pouvoir configurer le parcage d’appel et les droits d’utilisateur dont vous avez besoin pour effectuer des tâches de configuration.

<div>


> [!IMPORTANT]  
> Les fichiers de conservation de musique personnalisés pour l’application de parcage d’appel ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence Lync Server 2013 et les fichiers sont perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés. Conservez toujours une copie de sauvegarde distincte des fichiers de conservation musicaux personnalisés que vous avez téléchargés pour le parcage d’appel.



</div>

Cette section suppose que vous avez lu la documentation de planification relative au parcage d’appel (voir [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Conditions préalables à la configuration du parcage d’appel

Le parcage d’appel requiert les composants suivants :

  - service d’application

  - application de parcage d’appel

Ces composants sont installés automatiquement lorsque vous déployez voix entreprise.

Si vous voulez que les appelants entendent de la musique lors du parcage des appels, un fichier d’attente musicale est également requis. Un fichier d’attente musicale par défaut est installé automatiquement lorsque vous déployez voix entreprise. Vous pouvez le remplacer par un fichier d’attente musicale de votre choix. Le parcage d’appel utilise le magasin de fichiers pour stocker le fichier audio.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Droits d’utilisateur pour la configuration du parcage d’appel

Vous pouvez utiliser les outils d’administration suivants pour configurer le parcage d’appel :

  - Panneau de configuration Lync Server

  - Lync Server Management Shell

Ces outils vous permettent de configurer la table d’orbites de parcage d’appel et de configurer les autres paramètres utilisés par le parcage d’appel.

La configuration du parcage d’appel nécessite l’un des rôles d’administrateur suivants, en fonction de la tâche :

  - **CsVoiceAdministrator :** Ce rôle d’administrateur permet de créer, de configurer et de gérer toutes les stratégies et les paramètres liés à la voix.

  - **CsUserAdministrator :** Ce rôle d’administrateur peut activer le parcage d’appel dans la stratégie de voix. Il dispose aussi d’un accès en lecture seule à toutes les configurations de voix.

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

