---
title: Déplacer des répertoires de conférences
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Déplacer des répertoires de conférences

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-04_

Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire de conférences de votre pool Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Pour déplacer un annuaire de conférences vers Lync Server 2013

1.  Ouvrez Lync Server Management Shell.

2.  Pour obtenir l’identité des annuaires de conférences au sein de votre organisation, exécutez les commandes suivantes:
    
        Get-CsConferenceDirectory
    
    Dans la mesure où cette applet de requête renvoie tous les annuaires de conférences de votre organisation, il est possible que vous souhaitiez limiter les résultats uniquement au pool que vous souhaitez désactiver. Par exemple, si vous voulez désactiver un pool avec le nom de domaine complet (FQDN) pool01.contoso.net:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Cette cmdlet renvoie tous les répertoires de conférence dans lesquels l’ID de service contient le nom de domaine complet pool01.contoso.net.

3.  Pour déplacer des répertoires de conférence, exécutez la commande suivante pour chaque annuaire de conférences de la liste:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Par exemple :
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Il est possible que vous receviez une erreur, comme indiqué ci-dessous, qui est provoquée par Lync Server Management Shell nécessitant un ensemble d’autorisations mis à jour à partir d’Active Directory. Pour résoudre ce problème, fermez la fenêtre active et ouvrez un nouveau Lync Server Management Shell, puis réexécutez la commande.



</div>

![Sortie d’erreur Move-CsConferenceDirectory] (images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Sortie d’erreur Move-CsConferenceDirectory")

</div>

</div>

<span> </span>

</div>

</div>

</div>

