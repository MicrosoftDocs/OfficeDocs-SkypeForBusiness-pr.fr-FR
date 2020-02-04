---
title: 'Lync Server 2013 : Annexe A : Utilisation d’applets de commande pour déployer un Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2da84e03cc05607a47f1fe5af4a8b7987946df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Annexe A : Utilisation d’applets de commande pour déployer un Survivable Branch Appliance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-07_

Cette rubrique décrit le déploiement d’une unité de branchement Survivable à l’aide de Lync Server Management Shell. Suivez cette procédure sur le site central.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>Pour déployer à distance une unité de branchement Survivable

1.  Suivez la procédure décrite dans [Ajouter des sites de succursales à votre topologie dans Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) pour ajouter un nouveau site de succursale.

2.  Rejoignez le site de succursale au domaine.

3.  Ajoutez le groupe RTCUniversalSBATechnicians au groupe Administrateurs local.

4.  Redémarrez le serveur, puis ouvrez une session en tant que membre du groupe RTCUniversalSBATechnicians.

5.  Dans Lync Server Management Shell, tapez les commandes suivantes en remplaçant les espaces réservés par les informations appropriées pour votre organisation :
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

