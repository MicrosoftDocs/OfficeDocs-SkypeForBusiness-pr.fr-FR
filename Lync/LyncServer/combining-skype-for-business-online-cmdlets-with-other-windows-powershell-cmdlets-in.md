---
title: Combinaison des applets de commande Skype entreprise Online et d’autres applets de commande Windows PowerShell dans
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7455ba7d98ecc11fcfc6e0c255eb430e213d3f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Combinaison des applets de commande Skype entreprise Online et d’autres applets de commande Windows PowerShell dans

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-05_

Lorsque vous vous connectez à Skype entreprise Online à l’aide de Windows PowerShell, approximativement 40 applets de commande Skype entreprise Online seront disponibles pour votre utilisation. Toutefois, vous n’êtes pas limité à l’utilisation de ces applets de commande 40 lors de la gestion de Skype entreprise online. En plus des applets de commande Skype entreprise Online, vous pouvez également utiliser d’autres applets de commande Windows PowerShell installés sur votre ordinateur. (Lorsque vous installez Windows PowerShell 3,0, des centaines d’applets de commande Windows PowerShell de base sont également installées.) Vos commandes peuvent combiner des applets de commande Skype entreprise Online et d’autres cmdlets disponibles sur votre ordinateur.

Bien qu’un cours complet dans Windows PowerShell 3,0 dépasse le cadre de cet article, voici quelques exemples qui montrent pourquoi vous pouvez souhaiter mélanger et associer des applets de commande. Tout d’abord, aucune des applets de commande Skype entreprise Online n’inclut de commande Imprimer et aucune commande de ce type n’est disponible dans la console Windows PowerShell. Comment puis-je obtenir une impression des informations extraites par une cmdlet ? La première consiste à récupérer les informations, puis à envoyer ces informations à la cmdlet **out-Printer** :

    Get-CsTenant | Out-Printer

Étant donné qu’aucun paramètre supplémentaire n’est inclus, toutes les informations renvoyées par **la cmdlet Out-Printer** sont imprimées sur l’imprimante par défaut.

De même, aucune des applets de commande Skype entreprise Online n’inclut un paramètre qui vous permet d’enregistrer des données dans un fichier. Mais cela est correct : cette commande utilise la cmdlet **out-file** pour enregistrer les informations renvoyées dans le fichier texte C\\:\\logs locataires. txt :

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Cette commande utilise la cmdlet **Select-Object** pour limiter les données renvoyées et affichées à l’écran. Dans cet exemple, la cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) récupère les informations de tous vos utilisateurs de Skype entreprise Online, puis la cmdlet **Select-Object** est utilisée pour limiter les données affichées à la valeur Identity de l’utilisateur et à sa stratégie d’archivage :

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Étant donné que des centaines d’applets de commande peuvent être utilisées sur votre ordinateur, il se peut que vous ayez des difficultés à identifier les cmdlets qui sont des applets de commande Skype entreprise Online et celles qui ne le sont pas. Pour renvoyer la liste des applets de commande Skype entreprise Online (et uniquement les applets de commande Skype entreprise Online), vous devez d’abord déterminer le nom du module Windows PowerShell temporaire qui contient toutes les applets de commande Skype entreprise online. Pour ce faire, exécutez la commande suivante à partir de l’invite Windows PowerShell :

    Get-Module

Des informations semblables aux suivantes s’affichent à l’écran :

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Le module avec le script ModuleType est le module qui contient les applets de commande Skype entreprise online. Pour renvoyer la liste de ces cmdlets, exécutez la cmdlet **Get-Command** , en utilisant le nom du module de script comme nom de module :

    Get-Command -Module tmp_5astd3uh.m5v

Il est possible que vous puissiez avoir plusieurs modules avec un ModuleType égal à script. Dans ce cas, vous pouvez exécuter la commande suivante pour déterminer quel module inclut la cmdlet **Get-CsTenant** :

    Get-Command Get-CsTenant

Le module renvoyé pour la cmdlet **Get-CsTenant** sera le module contenant toutes les applets de commande Skype entreprise Online :

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Voir aussi


[Présentation de Windows PowerShell et de Skype entreprise Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

