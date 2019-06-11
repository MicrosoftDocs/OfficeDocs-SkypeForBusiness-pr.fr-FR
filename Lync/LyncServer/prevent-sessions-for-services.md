---
title: Empêcher l’exécution de sessions de services
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f3ed7c788db120782966541bfea9813328d90c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-04_

Vous pouvez utiliser le panneau de configuration Microsoft Lync Server 2010 pour empêcher les nouvelles sessions de tous les services Lync Server 2010 en cours d’exécution sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service Lync Server 2010 spécifique.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Pour empêcher de nouvelles sessions pour tous les services Lync Server sur un ordinateur

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez le Paneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).

4.  Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services pour lesquels vous voulez éviter de nouvelles sessions, puis cliquez dessus.

5.  Cliquez sur **action**.

6.  Cliquez sur **empêcher de nouvelles sessions pour tous les services**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Pour empêcher de nouvelles sessions pour un service spécifique

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez le Paneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).

4.  Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant le service que vous voulez démarrer ou arrêter, puis cliquez dessus.

5.  Cliquez sur **Propriétés**.

6.  Triez la liste des services, si nécessaire, puis cliquez sur le service pour lequel vous souhaitez éviter de nouvelles sessions.

7.  Cliquez sur **action**.

8.  Cliquez sur **empêcher de nouvelles sessions pour le service**.

9.  Cliquez sur **Fermer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

