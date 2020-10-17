---
title: Déplacer les annuaires des conférences
description: Déplacez les annuaires des conférences.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a91c30c0bedc84c684a096f5ea482fa911dc798
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549730"
---
# <a name="move-conference-directories"></a>Déplacer les annuaires des conférences

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences de votre pool Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Pour déplacer un annuaire des conférences vers Lync Server 2013

1.  Ouvrez Lync Server Management Shell.

2.  Pour obtenir l’identité des annuaires de conférence dans votre organisation, exécutez les commandes suivantes :
    
        Get-CsConferenceDirectory
    
    Étant donné que l’applet de commande renvoie tous les annuaires des conférences dans votre organisation, vous pouvez limiter les résultats au seul pool que vous voulez désaffecter. Par exemple, si vous souhaitez désaffecter un pool avec le nom de domaine complet (FQDN) pool01.contoso.net :
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Cette applet de commande renvoie tous les annuaires des conférences où l’ID de service contient le FQDN pool01.contoso.net.

3.  Pour déplacer les annuaires des conférences, exécutez ce qui suit pour chaque annuaire des conférences dans le pool :
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Par exemple :
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Il se peut que vous rencontriez une erreur, comme indiqué ci-dessous, qui est causée par Lync Server Management Shell nécessitant un jeu d’autorisations mis à jour à partir d’Active Directory. Pour résoudre l’erreur, fermez la fenêtre active et ouvrez un nouveau Lync Server Management Shell et exécutez à nouveau la commande.



</div>

![Sortie d’erreur Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Sortie d’erreur Move-CsConferenceDirectory")

</div>

</div>

<span> </span>

</div>

</div>

</div>

