---
title: Déplacement des annuaires de conférences
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences dans votre pool hérité.
ms.openlocfilehash: b7526d8c3c032bf8b1f9052dce7da7e8a87b66b5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372804"
---
# <a name="move-conference-directories"></a><span data-ttu-id="d9458-103">Déplacement des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="d9458-103">Move Conference Directories</span></span>

<span data-ttu-id="d9458-104">Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences dans votre pool hérité.</span><span class="sxs-lookup"><span data-stu-id="d9458-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="d9458-105">Pour déplacer un annuaire des conférences vers Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d9458-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="d9458-106">Ouvrez le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d9458-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="d9458-107">Pour obtenir l’identité des annuaires de conférence dans votre organisation, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d9458-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="d9458-108">La commande précédente renvoie tous les annuaires des conférences dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d9458-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="d9458-109">Pour cette raison, vous voudrez limiter les résultats vers le pool est désactivé.</span><span class="sxs-lookup"><span data-stu-id="d9458-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="d9458-110">Par exemple, si vous mettez hors service le pool avec la pool01.contoso.net (FQDN) de nom de domaine complet, utilisez cette commande pour limiter les données renvoyées dans les répertoires de conférence à partir de ce pool :</span><span class="sxs-lookup"><span data-stu-id="d9458-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="d9458-111">Cette commande renvoie uniquement les annuaires des conférences où la propriété ServiceID contient le FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="d9458-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="d9458-112">Pour déplacer les annuaires des conférences, exécutez la commande suivante pour chaque annuaire des conférences dans le pool :</span><span class="sxs-lookup"><span data-stu-id="d9458-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="d9458-113">Par exemple, pour déplacer un annuaire des conférences 3, utilisez cette commande, en spécifiant un Skype pour Business Server 2019 pool comme le TargetPool :</span><span class="sxs-lookup"><span data-stu-id="d9458-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="d9458-114">Si vous souhaitez déplacer tous les annuaires de conférence sur un pool, utilisez une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d9458-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="d9458-115">Télécharger [Microsoft désinstallation hérité et suppression de rôles de serveur](https://go.microsoft.com/fwlink/p/?linkId=246227) pour des instructions détaillées sur la mise hors service des pools hérités complètes.</span><span class="sxs-lookup"><span data-stu-id="d9458-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="d9458-116">Lors du déplacement des annuaires des conférences, vous pouvez rencontrer l’erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="d9458-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="d9458-117">Cette erreur se produit généralement lorsque le Skype pour Business Server Management Shell nécessite un ensemble d’autorisations Active Directory pour pouvoir exécuter une tâche de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d9458-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="d9458-118">Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance de l’interpréteur de commandes et réexécutez la commande pour déplacer l’annuaire des conférences.</span><span class="sxs-lookup"><span data-stu-id="d9458-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

