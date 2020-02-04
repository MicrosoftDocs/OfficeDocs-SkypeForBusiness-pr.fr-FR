---
title: 'Lync Server 2013 : Conditions prérequises pour la configuration du parcage d’appel et des droits utilisateur'
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
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Conditions prérequises pour la configuration du parcage d’appel et des droits utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-10_

Le parc d’appels est une fonctionnalité de gestion des appels qui est installée par défaut lors du déploiement d’Enterprise Voice. Cette rubrique décrit ce que vous devez mettre en place avant de pouvoir configurer le parc d’appels et les droits d’utilisateur nécessaires à l’exécution des tâches de configuration.

<div>


> [!IMPORTANT]  
> Les fichiers de conservation de musique personnalisés pour l’application de parc d’appels ne sont pas sauvegardés dans le cadre du processus de reprise après sinistre de Lync Server 2013 et les fichiers sont perdus si les fichiers téléchargés sur le pool sont endommagés, endommagés ou supprimés. Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel.



</div>

Cette section part du principe que vous avez lu la documentation de planification liée au parc d’appels (pour plus d’informations, reportez-vous à la [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Conditions préalables à la configuration du parc d’appels

Le parc d’appels nécessite les composants suivants :

  - service d’application

  - application de parcage d’appel

Ces composants sont installés automatiquement lorsque vous déployez Enterprise Voice.

Si vous voulez que les appelants entendent de la musique pendant le stationnement de l’appel, un fichier en attente de musique est également requis. Un fichier de Music-Holding par défaut est installé automatiquement lorsque vous déployez Enterprise Voice. Vous pouvez remplacer le fichier par défaut par votre propre fichier audio. Le parc d’appels utilise le magasin de fichiers pour contenir le fichier audio.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Configuration du parc d’appels-droits d’utilisateur

Pour configurer le parc d’appels, vous pouvez utiliser les outils d’administration suivants :

  - Panneau de configuration Lync Server

  - Lync Server Management Shell

Ces outils vous permettent de configurer la table de stationnement d’appel et de configurer d’autres paramètres utilisés par le parc d’appels.

La configuration du parc d’appels nécessite l’un des rôles d’administration suivants, en fonction de la tâche :

  - **CsVoiceAdministrator :** Ce rôle d’administrateur peut créer, configurer et gérer l’ensemble des stratégies et paramètres relatifs à la voix.

  - **CsUserAdministrator :** Ce rôle d’administrateur peut activer le parc d’appels dans la politique vocale. Ce rôle d’administrateur dispose également d’un accès en lecture seule à toutes les configurations vocales.

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

