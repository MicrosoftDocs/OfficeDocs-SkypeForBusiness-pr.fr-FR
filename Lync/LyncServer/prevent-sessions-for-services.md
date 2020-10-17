---
title: Empêcher l’exécution de sessions de services
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47202d91fdf0020a7692a9ff7b0c346ee3cb7aef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509271"
---
# <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Vous pouvez utiliser le panneau de configuration Microsoft Lync Server 2010 pour empêcher de nouvelles sessions pour tous les services Lync Server 2010 exécutés sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service Lync Server 2010 spécifique.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Pour empêcher l’exécution de nouvelles sessions de tous les services Lync Server sur un ordinateur

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.

4.  Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur.

5.  Cliquez sur **Action**.

6.  Cliquez sur **Empêcher de nouvelles sessions pour tous les services**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Pour empêcher l’exécution de nouvelles sessions d’un service spécifique

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.

4.  Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.

5.  Cliquez sur **Propriétés**.

6.  Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.

7.  Cliquez sur **Action**.

8.  Cliquez sur **Empêcher de nouvelles sessions pour le service**.

9.  Cliquez sur **Fermer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

