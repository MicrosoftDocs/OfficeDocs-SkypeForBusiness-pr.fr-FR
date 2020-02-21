---
title: Valider la réplication des paramètres de configuration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b238b0431c266204daa9ecdfc6cf72986fd9e40b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="3f79d-102">Valider la réplication des paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="3f79d-102">Validate replication of configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f79d-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3f79d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3f79d-104">Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant la cmdlet Lync Server 2013 **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin central de gestion ou sur un ordinateur appartenant à un domaine sur lequel sont installés les composants principaux de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f79d-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="3f79d-105">Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ».</span><span class="sxs-lookup"><span data-stu-id="3f79d-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="3f79d-106">Si c’est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** et attendez que la réplication se termine avant d’exécuter à nouveau la cmdlet **Get-CsManagementStoreReplicationStatus** .</span><span class="sxs-lookup"><span data-stu-id="3f79d-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

