---
title: 'Lync Server 2013 : Configuration du groupe Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94bc731ac00a4ff774930f506282b6aef16cbaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a>Configuration du groupe Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Response Group est une fonctionnalité de voix entreprise qui achemine et met en file d’attente les appels entrants vers des groupes de personnes, appelés *agents*, tels qu’un service d’assistance ou un service clientèle.

Les composants requis par le groupe de réponse sont installés et activés automatiquement sur le serveur frontal ou le serveur Standard Edition lors du déploiement de voix entreprise. Pour rendre le groupe de réponses disponible pour les utilisateurs, vous devez configurer des groupes d’agents, des files d’attente, puis des flux de travail. Par ailleurs, un administrateur de groupe de réponse peut déléguer la configuration d’un flux de travail existant à un gestionnaire de groupe de réponse, qui peut ensuite modifier et reconfigurer le flux de travail ainsi que ses groupes d’agents et files d’attente associés.

Cette section vous guide dans la configuration du groupe de réponse Lync Server 2013. Il part du principe que vous avez déjà lu les sections de planification associées au Response Group et avez déployé un serveur Enterprise Edition ou un serveur Standard Edition avec Enterprise Voice.

<div>


> [!TIP]  
> Pour plus d’informations sur la création d’un groupe de réponse à l’aide de Lync Server Management Shell, y compris un exemple de script, reportez-vous <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>à la section « Création de votre premier groupe de réponse avec Lync Server Management Shell ».



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Autorisations et conditions prérequises pour la configuration de Response Group dans Lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Processus de déploiement pour Response Group dans Lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Vue d’ensemble des scénarios de création de flux de travail dans Lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Création des groupes d’agents Response Group Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Création des files d’attente Response Group dans Lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [Facultatif Définir les heures d’activité du groupe de réponses dans Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)

  - [Facultatif Définir des jeux de vacances de groupe de réponse dans Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Création des flux de travail Response Group dans Lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [Facultatif Vérifier le déploiement de Response Group dans Lync Server 2013](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planifier les fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

