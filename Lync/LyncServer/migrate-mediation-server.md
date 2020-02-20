---
title: Migrer le serveur de médiation
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7786ecfd72ac32de74c9947f0effa1fad0c9603
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Migrer le serveur de médiation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Votre serveur de médiation est fusionné dans votre topologie pilote Lync Server 2013 lorsque vous exécutez l’Assistant Fusion et publipostage. Vous configurez le serveur de médiation Lync Server 2013, cependant, une fois tous les utilisateurs migrés, car un pool Office Communications Server 2007 R2 ne peut pas communiquer avec un serveur de médiation Lync Server 2013. Lors de la migration côte à côte, le pool Lync Server 2013 communique avec le serveur de médiation Office Communications Server 2007 R2.

Lorsque vous configurez votre serveur de médiation Lync Server 2013, vous devez également mettre à niveau ou remplacer vos passerelles Office Communications Server 2007 R2. Les passerelles Office Communications Server 2007 R2 ne prennent pas en charge le serveur de médiation Lync Server 2013. Vous devez déployer des passerelles certifiées pour Lync Server 2013 et les associer au serveur de médiation Lync Server 2013. Cette étape est requise pour pouvoir désaffecter entièrement votre déploiement d’Office Communications Server 2007 R2.

Les rubriques de cette section décrivent les tâches de configuration que vous devez effectuer une fois que vous avez terminé la migration du serveur de médiation Lync Server 2013. La transition du serveur de médiation colocalisé vers un serveur de médiation autonome est une tâche facultative.

  - [Configurer le serveur de médiation](configure-mediation-server.md)

  - [Modifier les itinéraires de communications vocales pour utiliser le nouveau serveur de médiation Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Transition d’un serveur de médiation colocalisé à un serveur de médiation autonome (facultatif)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

