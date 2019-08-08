---
title: Combiner les applets de applet de Skype entreprise Online avec d’autres cmdlets Windows PowerShell dans
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcd352521285e619c9ceeb55a0699b4d4ea73e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>Combiner les applets de applet de Skype entreprise Online avec d’autres cmdlets Windows PowerShell dans

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-07-05_

Lorsque vous vous connectez à Skype entreprise Online à l’aide de Windows PowerShell 40, vous pouvez utiliser les applets de applet de ligne Skype entreprise online. Toutefois, vous n’êtes pas limité à l’utilisation de ces applets de connexion 40 lors de la gestion de Skype entreprise online. Outre les applets de connexion Skype entreprise Online, vous pouvez également utiliser n’importe quelle applet de cmdlet Windows PowerShell installée sur votre ordinateur. (Lors de l’installation de Windows PowerShell 3,0, des centaines d’applets de construction Windows PowerShell sont également installés.) Vos commandes peuvent mélanger et faire correspondre des applets de commande Skype entreprise Online et d’autres cmdlets disponibles sur votre ordinateur.

Bien que le cours complet dans Windows PowerShell 3,0 ne dépasse pas le cadre de cet article, voici quelques exemples qui vous montrent pourquoi vous voudrez peut-être mélanger et faire correspondre des cmdlets. Tout d’abord, aucune des applets de commande de Skype entreprise Online ne comprend une commande Imprimer et aucune commande de ce type n’est disponible dans la console Windows PowerShell. Comment obtenir une impression des informations récupérées par une cmdlet? Pour récupérer les informations, vous pouvez récupérer les informations, puis les envoyer à l’applet de **connexion Out-Printer** :

    Get-CsTenant | Out-Printer

Dans la mesure où aucun paramètre supplémentaire n’est inclus, toutes les informations renvoyées par l’applet de **connexion hors imprimante** seront imprimées sur l’imprimante par défaut.

De même, aucune des applets de connexion Skype entreprise Online ne comprend un paramètre qui vous permet d’enregistrer les données dans un fichier. Ce n’est pas tout: cette commande utilise l’applet de commande **out-file** pour enregistrer les informations renvoyées dans le\\fichier\\texte C: logs clients. txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

Cette commande utilise l’applet de commande **Select-Object** pour limiter les données renvoyées et affichées à l’écran. Dans cet exemple, l’applet de connexion [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) récupère des informations pour tous vos utilisateurs de Skype entreprise Online, et l’applet de connexion **Select-Object** est utilisée pour limiter les données affichées à la valeur d’identité de l’utilisateur et à sa stratégie d’archivage:

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

Étant donné que des centaines de cmdlets peuvent être utilisées sur votre ordinateur, il est possible que vous ayez des difficultés à identifier les applets de applet de connexion de Skype entreprise Online et celles qui ne le sont pas. Pour renvoyer une liste des applets de applet de Skype entreprise Online (et uniquement les applets de connexion Skype entreprise Online), vous devez d’abord déterminer le nom du module Windows PowerShell temporaire contenant toutes les applets de connexion Skype entreprise online. Pour cela, exécutez la commande suivante à partir de l’invite Windows PowerShell:

    Get-Module

Des informations similaires à ce qui suit s’affichent à l’écran:

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

Le module avec le script ModuleType est le module qui contient les applets de connexion Skype entreprise online. Pour renvoyer la liste de ces applets de commande, exécutez l’applet de **commande Get-Command** en utilisant le nom du module de script comme nom de module:

    Get-Command -Module tmp_5astd3uh.m5v

Il est possible que vous puissiez avoir plusieurs modules avec un ModuleType égal à script. Dans ce cas, vous pouvez exécuter la commande suivante pour déterminer le module qui inclut l’applet **de commande Get-CsTenant** :

    Get-Command Get-CsTenant

Le module renvoyé pour l’applet de connexion **Get-CsTenant** sera le module contenant toutes les applets de connexion Skype entreprise Online:

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>Voir aussi


[Présentation de Windows PowerShell et Skype Entreprise Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

