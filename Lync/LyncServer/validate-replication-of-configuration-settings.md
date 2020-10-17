---
title: Valider la réplication des paramètres de configuration
description: Validez la réplication des paramètres de configuration.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26d8e9326da8b865f4e2ca3181975fb899300636
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552600"
---
# <a name="validate-replication-of-configuration-settings"></a>Valider la réplication des paramètres de configuration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant la cmdlet Lync Server 2013 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin central de gestion ou sur un ordinateur appartenant à un domaine sur lequel sont installés les composants principaux de Lync Server 2013.

Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ». Si c’est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** et attendez que la réplication se termine avant d’exécuter à nouveau la cmdlet **Get-CsManagementStoreReplicationStatus** .

</div>

<span> </span>

</div>

</div>

</div>

