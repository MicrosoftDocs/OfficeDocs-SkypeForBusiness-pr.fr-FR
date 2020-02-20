---
title: Déplacement des annuaires de conférences Lync Server 2010 vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d356af649dbee7dd367eb356ec564a06fa83aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Déplacer les annuaires des conférences

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-28_

Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences de votre pool Lync Server 2010.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Pour déplacer un annuaire des conférences vers Lync Server 2013

1.  Ouvrez Lync Server Management Shell.

2.  Pour obtenir l’identité des annuaires des conférences de votre organisation, exécutez la commande suivante :
    
        Get-CsConferenceDirectory
    
    La commande précédente renvoie tous les annuaires des conférences de votre organisation. Pour cette raison, vous souhaiterez peut-être limiter les résultats au pool en cours de mise hors service. Par exemple, si vous désaffectez le pool avec le nom de domaine complet pool01.contoso.net, utilisez cette commande pour limiter les données renvoyées aux annuaires de conférence à partir de ce pool :
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Cette commande renvoie uniquement les annuaires des conférences dans lesquels la propriété ServiceID contient le nom de domaine complet pool01.contoso.net.

3.  Pour déplacer les annuaires des conférences, exécutez la commande suivante pour chaque annuaire des conférences du pool :
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Par exemple, pour déplacer l’annuaire des conférences 3, utilisez cette commande en spécifiant un pool Lync Server 2013 comme TargetPool :
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Si vous souhaitez déplacer tous les annuaires des conférences d’un pool, utilisez une commande semblable à la suivante :
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Consultez le document « désinstallation de Microsoft Lync Server 2010 et suppression des rôles serveur » (qui peut être téléchargé à [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)partir de) pour obtenir des instructions détaillées, étape par étape, sur la désaffectation des pools Lync 2010.

Lorsque vous déplacez des annuaires de conférence, vous pouvez rencontrer l’erreur suivante :

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Cette erreur se produit généralement lorsque Lync Server Management Shell requiert un jeu mis à jour d’autorisations Active Directory pour effectuer une tâche. Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance du shell et réexécutez la commande afin de déplacer l’annuaire des conférences.

</div>

</div>

<span> </span>

</div>

</div>

</div>

