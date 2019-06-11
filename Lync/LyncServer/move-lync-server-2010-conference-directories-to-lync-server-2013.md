---
title: Déplacement des annuaires de conférences Lync Server 2010 vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa32bb5be86d72d4f18d11bb85d5ce0b57a96725
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="15905-102">Déplacement des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="15905-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15905-103">_**Dernière modification de la rubrique:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="15905-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="15905-104">Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire de conférences de votre pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="15905-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="15905-105">Pour déplacer un annuaire de conférences vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15905-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="15905-106">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="15905-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="15905-107">Pour obtenir l’identité des annuaires de conférences au sein de votre organisation, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="15905-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="15905-108">La commande précédente renvoie tous les annuaires de conférences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="15905-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="15905-109">Pour cette raison, il est possible que vous souhaitiez limiter les résultats au pool en cours de désactivation.</span><span class="sxs-lookup"><span data-stu-id="15905-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="15905-110">Par exemple, si vous désaffectez le pool avec le nom de domaine complet (FQDN) pool01.contoso.net, utilisez cette commande pour limiter les données renvoyées aux annuaires de conférences à partir du pool:</span><span class="sxs-lookup"><span data-stu-id="15905-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="15905-111">Cette commande renvoie uniquement les répertoires de conférences dans lesquels la propriété ServiceID contient le nom de domaine complet pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="15905-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="15905-112">Pour déplacer des répertoires de conférence, exécutez la commande suivante pour chaque annuaire de conférences de la liste:</span><span class="sxs-lookup"><span data-stu-id="15905-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="15905-113">Par exemple, pour déplacer l’annuaire de conférence 3, utilisez cette commande en spécifiant un pool Lync Server 2013 en tant que TargetPool:</span><span class="sxs-lookup"><span data-stu-id="15905-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="15905-114">Si vous souhaitez déplacer tous les répertoires de conférence sur un pool, utilisez une commande similaire à celle qui suit:</span><span class="sxs-lookup"><span data-stu-id="15905-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="15905-115">Pour obtenir des instructions complètes et détaillées sur la désaffectation des pools 2010 de Lync, voir le document «désinstallation de Microsoft Lync Server 2010 et suppression des rôles de serveur» (qui peut être téléchargé à partir de [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)).</span><span class="sxs-lookup"><span data-stu-id="15905-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="15905-116">Lorsque vous déplacez des répertoires de conférence, vous pouvez rencontrer l’erreur suivante:</span><span class="sxs-lookup"><span data-stu-id="15905-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="15905-117">Cette erreur se produit généralement lorsque Lync Server Management Shell nécessite un ensemble mis à jour d’autorisations Active Directory pour effectuer une tâche.</span><span class="sxs-lookup"><span data-stu-id="15905-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="15905-118">Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance de l’interpréteur de commandes, puis réexécutez la commande afin de déplacer le répertoire de conférence.</span><span class="sxs-lookup"><span data-stu-id="15905-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

