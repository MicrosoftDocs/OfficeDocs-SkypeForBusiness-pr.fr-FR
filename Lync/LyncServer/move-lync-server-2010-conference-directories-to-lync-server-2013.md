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
ms.openlocfilehash: 049472022a26d7a3a6e8e78e20a20ccaa46ff5fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="3c018-102">Déplacer les annuaires des conférences</span><span class="sxs-lookup"><span data-stu-id="3c018-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c018-103">_**Dernière modification de la rubrique :** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="3c018-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="3c018-104">Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences de votre pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3c018-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="3c018-105">Pour déplacer un annuaire des conférences vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c018-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="3c018-106">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3c018-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3c018-107">Pour obtenir l’identité des annuaires des conférences de votre organisation, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="3c018-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="3c018-108">La commande précédente renvoie tous les annuaires des conférences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3c018-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="3c018-109">Pour cette raison, vous souhaiterez peut-être limiter les résultats au pool en cours de mise hors service.</span><span class="sxs-lookup"><span data-stu-id="3c018-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="3c018-110">Par exemple, si vous désaffectez le pool avec le nom de domaine complet pool01.contoso.net, utilisez cette commande pour limiter les données renvoyées aux annuaires de conférence à partir de ce pool :</span><span class="sxs-lookup"><span data-stu-id="3c018-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="3c018-111">Cette commande renvoie uniquement les annuaires des conférences dans lesquels la propriété ServiceID contient le nom de domaine complet pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="3c018-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="3c018-112">Pour déplacer les annuaires des conférences, exécutez la commande suivante pour chaque annuaire des conférences du pool :</span><span class="sxs-lookup"><span data-stu-id="3c018-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="3c018-113">Par exemple, pour déplacer l’annuaire des conférences 3, utilisez cette commande en spécifiant un pool Lync Server 2013 comme TargetPool :</span><span class="sxs-lookup"><span data-stu-id="3c018-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="3c018-114">Si vous souhaitez déplacer tous les annuaires des conférences d’un pool, utilisez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="3c018-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="3c018-115">Consultez le document « désinstallation de Microsoft Lync Server 2010 et suppression des rôles serveur » (qui peut être téléchargé à [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)partir de) pour obtenir des instructions détaillées, étape par étape, sur la désaffectation des pools Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="3c018-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="3c018-116">Lorsque vous déplacez des annuaires de conférence, vous pouvez rencontrer l’erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="3c018-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="3c018-117">Cette erreur se produit généralement lorsque Lync Server Management Shell requiert un jeu mis à jour d’autorisations Active Directory pour effectuer une tâche.</span><span class="sxs-lookup"><span data-stu-id="3c018-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="3c018-118">Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance du shell et réexécutez la commande afin de déplacer l’annuaire des conférences.</span><span class="sxs-lookup"><span data-stu-id="3c018-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

