---
title: Déplacement des annuaires de conférences
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire de conférence dans votre pool hérité.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752496"
---
# <a name="move-conference-directories"></a><span data-ttu-id="aa284-103">Déplacement des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="aa284-103">Move Conference Directories</span></span>

<span data-ttu-id="aa284-104">Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences de votre pool hérité.</span><span class="sxs-lookup"><span data-stu-id="aa284-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="aa284-105">Pour déplacer un annuaire des conférences vers Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="aa284-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="aa284-106">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aa284-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="aa284-107">Pour obtenir l’identité des annuaires des conférences de votre organisation, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="aa284-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="aa284-108">La commande précédente renvoie tous les annuaires des conférences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aa284-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="aa284-109">Pour cette raison, vous souhaiterez peut-être limiter les résultats au pool en cours de mise hors service.</span><span class="sxs-lookup"><span data-stu-id="aa284-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="aa284-110">Par exemple, si vous désaffectez le pool avec le nom de domaine complet pool01.contoso.net, utilisez cette commande pour limiter les données renvoyées aux annuaires de conférence à partir de ce pool :</span><span class="sxs-lookup"><span data-stu-id="aa284-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="aa284-111">Cette commande renvoie uniquement les annuaires des conférences dans lesquels la propriété ServiceID contient le nom de domaine complet pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="aa284-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="aa284-112">Pour déplacer les annuaires des conférences, exécutez la commande suivante pour chaque annuaire des conférences du pool :</span><span class="sxs-lookup"><span data-stu-id="aa284-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="aa284-113">Par exemple, pour déplacer l’annuaire des conférences 3, utilisez cette commande en spécifiant un pool Skype entreprise Server 2019 comme TargetPool :</span><span class="sxs-lookup"><span data-stu-id="aa284-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="aa284-114">Si vous souhaitez déplacer tous les annuaires des conférences d’un pool, utilisez une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="aa284-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="aa284-115">Télécharger la [désinstallation de Microsoft héritage et suppression des rôles de serveur](https://go.microsoft.com/fwlink/p/?linkId=246227) pour obtenir des instructions détaillées, étape par étape sur la mise hors service des pools hérités.</span><span class="sxs-lookup"><span data-stu-id="aa284-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="aa284-116">Lorsque vous déplacez des annuaires de conférence, vous pouvez rencontrer l’erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="aa284-116">When moving conference directories, you might encounter the following error:</span></span>
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="aa284-117">Cette erreur se produit généralement lorsque Skype entreprise Server Management Shell nécessite un ensemble mis à jour d’autorisations Active Directory pour effectuer une tâche.</span><span class="sxs-lookup"><span data-stu-id="aa284-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="aa284-118">Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance du shell et réexécutez la commande pour déplacer l’annuaire des conférences.</span><span class="sxs-lookup"><span data-stu-id="aa284-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

