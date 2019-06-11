---
title: Migration du serveur de médiation
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Migration du serveur de médiation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Votre serveur de médiation est fusionné dans votre topologie pilote Lync Server 2013 lorsque vous exécutez l’Assistant Fusion. Toutefois, vous configurez le serveur de médiation Lync Server 2013, après la migration de tous les utilisateurs, car un pool Office Communications Server 2007 R2 ne peut pas communiquer avec un serveur de médiation Lync Server 2013. Pendant la migration côte à côte, le pool Lync Server 2013 communique avec le serveur de médiation Office Communications Server 2007 R2.

Lorsque vous configurez votre serveur de médiation Lync Server 2013, vous devez également mettre à niveau ou remplacer vos passerelles Office Communications Server 2007 R2. Les passerelles Office Communications Server 2007 R2 ne prennent pas en charge le serveur de médiation Lync Server 2013. Vous devez déployer des passerelles certifiées pour Lync Server 2013 et les associer à l’aide du serveur de médiation Lync Server 2013. Cette étape est nécessaire avant de pouvoir désaffecter entièrement votre déploiement d’Office Communications Server 2007 R2.

Les rubriques de cette section décrivent les tâches de configuration que vous devez effectuer lorsque vous avez terminé la migration de Lync Server 2013 Mediation Server. Le passage du serveur de médiation colocalisé à un serveur de médiation autonome est une tâche facultative.

  - [Configurer le serveur de médiation](configure-mediation-server.md)

  - [Changer les itinéraires vocaux pour utiliser le nouveau serveur de médiation Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Transition d’un serveur de médiation colocalisé vers un serveur de médiation autonome (facultatif)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

