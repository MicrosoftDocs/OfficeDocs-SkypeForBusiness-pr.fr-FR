---
title: Déplacement des annuaires de conférences
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire de conférences de votre pool hérité.
ms.openlocfilehash: 1cd4a3a3359ec1638c3ae93c6ce81d8ba2227b96
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988939"
---
# <a name="move-conference-directories"></a><span data-ttu-id="0ae60-103">Déplacement des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="0ae60-103">Move Conference Directories</span></span>

<span data-ttu-id="0ae60-104">Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire de conférences de votre pool hérité.</span><span class="sxs-lookup"><span data-stu-id="0ae60-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="0ae60-105">Pour déplacer un annuaire de conférences vers Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="0ae60-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="0ae60-106">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0ae60-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="0ae60-107">Pour obtenir l’identité des annuaires de conférences au sein de votre organisation, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0ae60-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="0ae60-108">La commande précédente renvoie tous les annuaires de conférences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0ae60-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="0ae60-109">Pour cette raison, il est possible que vous souhaitiez limiter les résultats au pool en cours de désactivation.</span><span class="sxs-lookup"><span data-stu-id="0ae60-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="0ae60-110">Par exemple, si vous désaffectez le pool avec le nom de domaine complet (FQDN) pool01.contoso.net, utilisez cette commande pour limiter les données renvoyées aux annuaires de conférences à partir du pool :</span><span class="sxs-lookup"><span data-stu-id="0ae60-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="0ae60-111">Cette commande renvoie uniquement les répertoires de conférences dans lesquels la propriété ServiceID contient le nom de domaine complet pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="0ae60-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="0ae60-112">Pour déplacer des répertoires de conférence, exécutez la commande suivante pour chaque annuaire de conférences de la liste :</span><span class="sxs-lookup"><span data-stu-id="0ae60-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="0ae60-113">Par exemple, pour déplacer l’annuaire de conférences 3, utilisez cette commande en spécifiant un pool Skype entreprise Server 2019 en tant que TargetPool :</span><span class="sxs-lookup"><span data-stu-id="0ae60-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="0ae60-114">Si vous souhaitez déplacer tous les répertoires de conférence sur un pool, utilisez une commande similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0ae60-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="0ae60-115">Télécharger la [désinstallation de l’ancien et](https://go.microsoft.com/fwlink/p/?linkId=246227) de la suppression de rôles de serveur pour obtenir des instructions complètes et détaillées sur la mise en service des pools hérités.</span><span class="sxs-lookup"><span data-stu-id="0ae60-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="0ae60-116">Lorsque vous déplacez des répertoires de conférence, vous pouvez rencontrer l’erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="0ae60-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="0ae60-117">Cette erreur se produit généralement lorsque Skype entreprise Server Management Shell nécessite un ensemble mis à jour d’autorisations Active Directory pour effectuer une tâche.</span><span class="sxs-lookup"><span data-stu-id="0ae60-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="0ae60-118">Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance de l’interpréteur de commandes, puis réexécutez la commande pour déplacer l’annuaire de conférence.</span><span class="sxs-lookup"><span data-stu-id="0ae60-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

