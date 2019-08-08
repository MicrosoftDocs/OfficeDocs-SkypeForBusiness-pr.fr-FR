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

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="785c8-102">Combiner les applets de applet de Skype entreprise Online avec d’autres cmdlets Windows PowerShell dans</span><span class="sxs-lookup"><span data-stu-id="785c8-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="785c8-103">_**Dernière modification de la rubrique:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="785c8-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="785c8-104">Lorsque vous vous connectez à Skype entreprise Online à l’aide de Windows PowerShell 40, vous pouvez utiliser les applets de applet de ligne Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="785c8-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="785c8-105">Toutefois, vous n’êtes pas limité à l’utilisation de ces applets de connexion 40 lors de la gestion de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="785c8-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="785c8-106">Outre les applets de connexion Skype entreprise Online, vous pouvez également utiliser n’importe quelle applet de cmdlet Windows PowerShell installée sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="785c8-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="785c8-107">(Lors de l’installation de Windows PowerShell 3,0, des centaines d’applets de construction Windows PowerShell sont également installés.) Vos commandes peuvent mélanger et faire correspondre des applets de commande Skype entreprise Online et d’autres cmdlets disponibles sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="785c8-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="785c8-108">Bien que le cours complet dans Windows PowerShell 3,0 ne dépasse pas le cadre de cet article, voici quelques exemples qui vous montrent pourquoi vous voudrez peut-être mélanger et faire correspondre des cmdlets.</span><span class="sxs-lookup"><span data-stu-id="785c8-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="785c8-109">Tout d’abord, aucune des applets de commande de Skype entreprise Online ne comprend une commande Imprimer et aucune commande de ce type n’est disponible dans la console Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="785c8-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="785c8-110">Comment obtenir une impression des informations récupérées par une cmdlet?</span><span class="sxs-lookup"><span data-stu-id="785c8-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="785c8-111">Pour récupérer les informations, vous pouvez récupérer les informations, puis les envoyer à l’applet de **connexion Out-Printer** :</span><span class="sxs-lookup"><span data-stu-id="785c8-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="785c8-112">Dans la mesure où aucun paramètre supplémentaire n’est inclus, toutes les informations renvoyées par l’applet de **connexion hors imprimante** seront imprimées sur l’imprimante par défaut.</span><span class="sxs-lookup"><span data-stu-id="785c8-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="785c8-113">De même, aucune des applets de connexion Skype entreprise Online ne comprend un paramètre qui vous permet d’enregistrer les données dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="785c8-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="785c8-114">Ce n’est pas tout: cette commande utilise l’applet de commande **out-file** pour enregistrer les informations renvoyées dans le\\fichier\\texte C: logs clients. txt:</span><span class="sxs-lookup"><span data-stu-id="785c8-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="785c8-115">Cette commande utilise l’applet de commande **Select-Object** pour limiter les données renvoyées et affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="785c8-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="785c8-116">Dans cet exemple, l’applet de connexion [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) récupère des informations pour tous vos utilisateurs de Skype entreprise Online, et l’applet de connexion **Select-Object** est utilisée pour limiter les données affichées à la valeur d’identité de l’utilisateur et à sa stratégie d’archivage:</span><span class="sxs-lookup"><span data-stu-id="785c8-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="785c8-117">Étant donné que des centaines de cmdlets peuvent être utilisées sur votre ordinateur, il est possible que vous ayez des difficultés à identifier les applets de applet de connexion de Skype entreprise Online et celles qui ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="785c8-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="785c8-118">Pour renvoyer une liste des applets de applet de Skype entreprise Online (et uniquement les applets de connexion Skype entreprise Online), vous devez d’abord déterminer le nom du module Windows PowerShell temporaire contenant toutes les applets de connexion Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="785c8-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="785c8-119">Pour cela, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="785c8-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="785c8-120">Des informations similaires à ce qui suit s’affichent à l’écran:</span><span class="sxs-lookup"><span data-stu-id="785c8-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="785c8-121">Le module avec le script ModuleType est le module qui contient les applets de connexion Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="785c8-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="785c8-122">Pour renvoyer la liste de ces applets de commande, exécutez l’applet de **commande Get-Command** en utilisant le nom du module de script comme nom de module:</span><span class="sxs-lookup"><span data-stu-id="785c8-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="785c8-123">Il est possible que vous puissiez avoir plusieurs modules avec un ModuleType égal à script.</span><span class="sxs-lookup"><span data-stu-id="785c8-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="785c8-124">Dans ce cas, vous pouvez exécuter la commande suivante pour déterminer le module qui inclut l’applet **de commande Get-CsTenant** :</span><span class="sxs-lookup"><span data-stu-id="785c8-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="785c8-125">Le module renvoyé pour l’applet de connexion **Get-CsTenant** sera le module contenant toutes les applets de connexion Skype entreprise Online:</span><span class="sxs-lookup"><span data-stu-id="785c8-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="785c8-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="785c8-126">See Also</span></span>


<span data-ttu-id="785c8-127">[Présentation de Windows PowerShell et Skype Entreprise Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="785c8-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

