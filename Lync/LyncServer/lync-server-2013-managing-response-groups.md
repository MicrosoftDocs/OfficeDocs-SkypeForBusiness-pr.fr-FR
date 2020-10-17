---
title: 'Lync Server 2013 : gestion des groupes Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00736a94cc383a362a3f952519acc603c5beefab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507191"
---
# <a name="managing-response-groups-in-lync-server-2013"></a>Gestion des groupes Response Group dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2018-02-01_

Les groupes Response Group sont une fonctionnalité de gestion des appels qui vous permet de mettre en file d’attente les appels passés vers une zone spécifique, telle qu’un service de support technique, puis de les acheminer vers un groupe de personnes désignées, appelées des *agents*.

Pour gérer les groupes Response Group, vous devez configurer des groupes d’agents, des files d’attente et des flux de travail, qui définissent ce qui arrive à un appel entre le moment où il est passé et le moment où un agent y répond.

<div>


> [!NOTE]  
> Si vous avez plus de 300 flux de travail dans un seul pool dans votre déploiement de Response Group, il est préférable d’utiliser des applets de commande Lync Server Management Shell pour créer les flux de travail. Si vous utilisez l’outil de configuration de groupes Response Group en vue de créer des flux de travail pour un pool qui en contient plus de 300, le chargement de la page web sera plus long. Le nombre d’agents indirectement associés aux flux de travail par le biais des files d’attente a également un effet proportionnel au chargement de la page.



</div>

Les rubriques de cette section comportent des procédures détaillées pour les tâches que vous pouvez effectuer pour personnaliser et gérer l’application Response Group dans votre déploiement.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Gestion des groupes d’agents Response Group dans Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)

  - [Gestion des files d’attente Response Group dans Lync Server 2013](lync-server-2013-managing-response-group-queues.md)

  - [Gestion des flux de travail Response Group dans Lync Server 2013](lync-server-2013-managing-response-group-workflows.md)

  - [Gestion des paramètres de groupe Response Group au niveau de l’application dans Lync Server 2013](lync-server-2013-managing-application-level-response-group-settings.md)

  - [Transfert de groupes Response Group vers un nouveau pool dans Lync Server 2013](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [Gestion des groupes Response Group dans Lync Server 2013 lors d’un sinistre](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

