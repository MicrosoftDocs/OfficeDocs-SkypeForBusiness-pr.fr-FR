---
title: 'Lync Server 2013 : configuration du groupe Response Group'
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
ms.openlocfilehash: c40f48b52759bfc12441a558b85de89d149f4bf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a>Configuration du groupe Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Response Group est une fonctionnalité voix entreprise qui achemine et met en file d’attente les appels entrants vers des groupes de personnes, appelés *agents*, comme un support technique ou un service clientèle.

Les composants nécessaires à Response Group sont installés et activés automatiquement sur le serveur frontal ou le serveur Standard Edition Server lorsque vous déployez Voix Entreprise. Pour rendre Response Group accessible aux utilisateurs, vous devez configurer des groupes d’agents, des files d’attente, puis des workflows. En outre, un administrateur Response Group peut déléguer la configuration d’un flux de travail existant à un responsable de groupe Response Group, qui peut ensuite modifier et reconfigurer le flux de travail, ainsi que les groupes d’agents et les files d’attente associés.

Cette section vous guide tout au long de la configuration du groupe Response Group Lync Server 2013. Il part du principe que vous avez déjà lu les sections de planification relatives au Response Group et que vous avez déployé un serveur Enterprise Edition ou un serveur Standard Edition avec voix entreprise.

<div>


> [!TIP]  
> Pour plus d’informations sur la création d’un groupe Response Group à l’aide de Lync Server Management Shell, notamment un exemple de script, reportez-vous à <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>la rubrique « Creating Your First Response Group using Lync Server Management Shell » à l’adresse.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Autorisations et conditions préalables à la configuration du groupe Response Group dans Lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Processus de déploiement du groupe Response Group dans Lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Vue d’ensemble des scénarios de création de flux de travail dans Lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Créer des groupes d’agents Response Group Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Créer des files d’attente Response Group dans Lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [Module Définition des heures d’ouverture d’un groupe Response Group dans Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)

  - [Module Définir les groupes de congés Response Group dans Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Créer des flux de travail Response Group dans Lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [Module Vérifier le déploiement de Response Group dans Lync Server 2013](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

