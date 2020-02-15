---
title: 'Lync Server 2013 : restauration des paramètres de Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1557640fa021faf7313af834eb06f94f1c7432a2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="ca117-102">Restauration des paramètres Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca117-102">Restoring Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca117-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ca117-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ca117-104">Si vous avez déployé l’application Response Group et que vous avez besoin de restaurer un serveur principal ou un serveur Standard Edition, vous devez également restaurer les paramètres de configuration Response Group.</span><span class="sxs-lookup"><span data-stu-id="ca117-104">If you deployed the Response Group application and you need to restore a Back End Server or a Standard Edition server, you also need to restore the Response Group configuration settings.</span></span>

<div>

## <a name="to-restore-response-group-configuration-settings"></a><span data-ttu-id="ca117-105">Pour restaurer les paramètres de configuration du Response Group</span><span class="sxs-lookup"><span data-stu-id="ca117-105">To restore Response Group configuration settings</span></span>

1.  <span data-ttu-id="ca117-106">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="ca117-106">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    <span data-ttu-id="ca117-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ca117-107">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

