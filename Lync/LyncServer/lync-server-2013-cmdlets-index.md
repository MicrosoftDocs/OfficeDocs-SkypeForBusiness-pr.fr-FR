---
title: 'Lync Server 2013 : index cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64dd8edcb3f21cbdbdaf2b5a29c7e813675c9136
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a><span data-ttu-id="96bdd-102">Index des cmdlets Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96bdd-102">Lync Server 2013 cmdlets index</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96bdd-103">_**Dernière modification de la rubrique :** 2016-04-12_</span><span class="sxs-lookup"><span data-stu-id="96bdd-103">_**Topic Last Modified:** 2016-04-12_</span></span>

<span data-ttu-id="96bdd-104">Microsoft Lync Server 2013 est fourni avec plus de 700 cmdlets qui permettent aux administrateurs de gérer Lync Server 2013 à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="96bdd-104">Microsoft Lync Server 2013 ships with more than 700 cmdlets that enable administrators to manage Lync Server 2013 from the command line.</span></span> <span data-ttu-id="96bdd-105">Les applets de applet de serveur Lync sont généralement utilisés avec Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="96bdd-105">The Lync Server cmdlets are typically used with the Lync Server Management Shell.</span></span> <span data-ttu-id="96bdd-106">Une des façons d’utiliser Lync Server Management Shell consiste à se connecter à un ordinateur exécutant un serveur Lync Server ou un rôle serveur, cliquez sur **Démarrer**, **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="96bdd-106">One way to use the Lync Server Management Shell is to log on to a computer running a Lync Server service or server role, click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="96bdd-107">Après l’ouverture de Management Shell, vous pouvez obtenir de l’aide pour une applet de commande directement à partir de la ligne de commande en tapant une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="96bdd-107">After the Management Shell is open you can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="96bdd-108">La commande précédente permet d’obtenir de l’aide concernant l’applet de commande **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="96bdd-108">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="96bdd-109">Pour afficher l’aide d’une cmdlet différente, remplacez **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="96bdd-109">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="96bdd-110">Pour obtenir la liste complète des applets de commande disponibles pour gérer Lync Server, tapez les informations suivantes à l’invite de commandes de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="96bdd-110">To retrieve a full list of cmdlets available for managing Lync Server, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="96bdd-111">Pour plus d’informations sur l’utilisation de Lync Server Management Shell, voir le blog Lync Server [http://go.microsoft.com/fwlink/p/?linkId=203150](http://go.microsoft.com/fwlink/p/?linkid=203150)Windows PowerShell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="96bdd-111">For details about using the Lync Server Management Shell, see the Lync Server Windows PowerShell blog at [http://go.microsoft.com/fwlink/p/?linkId=203150](http://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

<div>

## <a name="lync-server-2013-cmdlets"></a><span data-ttu-id="96bdd-112">Applets de applet Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96bdd-112">Lync Server 2013 Cmdlets</span></span>

<span data-ttu-id="96bdd-113">Voici une liste des applets de commande fournis avec Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="96bdd-113">Following is a list of the cmdlets that ship with Lync Server 2013:</span></span>

  - <span data-ttu-id="96bdd-114">[Add-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703199(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-114">[Add-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703199(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-115">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-115">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-116">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-116">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-117">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-117">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-118">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-118">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-119">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-119">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-120">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-120">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-121">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-121">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-122">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-122">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-123">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-123">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-124">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-124">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-125">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-125">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-126">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-126">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-127">[Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-127">[Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-128">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-128">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-129">[Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-129">[Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-130">[Disable-CsUser](https://technet.microsoft.com/en-us/library/Gg398747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-130">[Disable-CsUser](https://technet.microsoft.com/en-us/library/Gg398747(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-131">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-131">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-132">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-132">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-133">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-133">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-134">[Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-134">[Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-135">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-135">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-136">[Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-136">[Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-137">[Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-137">[Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-138">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-138">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-139">[Enable-CsUser](https://technet.microsoft.com/en-us/library/Gg398711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-139">[Enable-CsUser](https://technet.microsoft.com/en-us/library/Gg398711(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-140">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-140">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-141">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-141">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-142">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-142">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-143">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-143">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-144">[Export-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-144">[Export-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205011(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-145">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-145">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-146">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-146">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-147">[Get-CsAdContact](https://technet.microsoft.com/en-us/library/Gg412776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-147">[Get-CsAdContact](https://technet.microsoft.com/en-us/library/Gg412776(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-148">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-148">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-149">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-149">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-150">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-150">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-151">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-151">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-152">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-152">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-153">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-153">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-154">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-154">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-155">[Get-CsAdUser](https://technet.microsoft.com/en-us/library/Gg398592(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-155">[Get-CsAdUser](https://technet.microsoft.com/en-us/library/Gg398592(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-156">[Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-156">[Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-157">[Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-157">[Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-158">[Get-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-158">[Get-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398937(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-159">[Get-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398655(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-159">[Get-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398655(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-160">[Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-160">[Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-161">[Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-161">[Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-162">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-162">[Get-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-163">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-163">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-164">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-164">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-165">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-165">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-166">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-166">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-167">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-167">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-168">[Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-168">[Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-169">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-169">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-170">[Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-170">[Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-171">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-171">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-172">[Get-CsClientAccessLicense](https://technet.microsoft.com/en-us/library/JJ204853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-172">[Get-CsClientAccessLicense](https://technet.microsoft.com/en-us/library/JJ204853(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-173">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-173">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-174">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-174">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-175">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-175">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-176">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-176">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-177">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-177">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-178">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-178">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-179">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-179">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-180">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-180">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-181">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-181">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-182">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-182">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-183">[Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-183">[Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-184">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-184">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-185">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-185">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-186">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-186">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-187">[Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-187">[Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-188">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-188">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-189">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-189">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-190">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-190">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-191">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-191">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-192">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-192">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-193">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-193">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-194">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-194">[Get-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-195">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-195">[Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-196">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-196">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-197">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-197">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-198">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-198">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-199">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-199">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-200">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-200">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-201">[Get-CsEffectivePolicy](https://technet.microsoft.com/en-us/library/JJ204636(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-201">[Get-CsEffectivePolicy](https://technet.microsoft.com/en-us/library/JJ204636(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-202">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-202">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-203">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-203">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-204">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-204">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-205">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-205">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-206">[Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-206">[Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-207">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-207">[Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-208">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-208">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-209">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-209">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-210">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-210">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-211">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-211">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-212">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-212">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-213">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-213">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-214">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-214">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-215">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-215">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-216">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-216">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-217">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-217">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-218">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-218">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-219">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-219">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-220">[Get-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg412849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-220">[Get-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg412849(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-221">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-221">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-222">[Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-222">[Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-223">[Get-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-223">[Get-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398128(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-224">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-224">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-225">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-225">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-226">[Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-226">[Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-227">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-227">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-228">[Get-Csnetworkconfiguration permettent](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-228">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-229">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-229">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-230">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-230">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-231">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-231">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-232">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-232">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-233">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-233">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-234">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-234">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-235">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-235">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-236">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-236">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-237">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-237">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-238">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-238">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-239">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-239">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-240">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-240">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-241">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-241">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-242">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-242">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-243">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-243">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-244">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-244">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-245">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-245">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-246">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-246">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-247">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-247">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-248">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-248">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-249">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-249">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-250">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-250">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-251">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-251">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-252">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-252">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-253">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-253">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-254">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-254">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-255">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-255">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-256">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-256">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-257">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-257">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-258">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-258">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-259">[Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-259">[Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-260">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-260">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-261">[Get-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-261">[Get-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-262">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-262">[Get-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-263">[Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-263">[Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-264">[Get-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425793(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-264">[Get-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425793(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-265">[Get-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg412762(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-265">[Get-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg412762(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-266">[Get-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg412983(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-266">[Get-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg412983(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-267">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398284(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-267">[Get-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398284(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-268">[Get-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-268">[Get-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412759(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-269">[Get-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-269">[Get-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425766(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-270">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-270">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-271">[Get-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg425948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-271">[Get-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg425948(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-272">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-272">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-273">[Get-CsService](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-273">[Get-CsService](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-274">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-274">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-275">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-275">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-276">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-276">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-277">[Get-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703200(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-277">[Get-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703200(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-278">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-278">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-279">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-279">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-280">[Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-280">[Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-281">[Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-281">[Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-282">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-282">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-283">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-283">[Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-284">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-284">[Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-285">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-285">[Get-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-286">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-286">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-287">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-287">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-288">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-288">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-289">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-289">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-290">[Get-CsUICulture](https://technet.microsoft.com/en-us/library/Gg412900(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-290">[Get-CsUICulture](https://technet.microsoft.com/en-us/library/Gg412900(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-291">[Get-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg412792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-291">[Get-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg412792(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-292">[Get-CsUser](https://technet.microsoft.com/en-us/library/Gg398125(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-292">[Get-CsUser](https://technet.microsoft.com/en-us/library/Gg398125(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-293">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398978(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-293">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398978(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-294">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-294">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-295">[Get-CsUserPoolInfo](https://technet.microsoft.com/en-us/library/Gg398615(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-295">[Get-CsUserPoolInfo](https://technet.microsoft.com/en-us/library/Gg398615(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-296">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-296">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-297">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-297">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-298">[Get-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-298">[Get-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204838(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-299">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-299">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-300">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-300">[Get-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-301">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-301">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-302">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-302">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-303">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-303">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-304">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-304">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-305">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-305">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-306">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-306">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-307">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-307">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-308">[Get-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-308">[Get-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-309">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-309">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-310">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-310">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-311">[Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-311">[Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-312">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-312">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-313">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-313">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-314">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-314">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-315">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-315">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-316">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-316">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-317">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-317">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-318">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-318">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-319">[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-319">[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-320">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-320">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-321">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-321">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-322">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-322">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-323">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-323">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-324">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-324">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-325">[Grant-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205388(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-325">[Grant-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205388(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-326">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-326">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-327">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-327">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-328">[Import-CsAnnouncementFile](https://technet.microsoft.com/en-us/library/Gg398472(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-328">[Import-CsAnnouncementFile](https://technet.microsoft.com/en-us/library/Gg398472(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-329">[Importation-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-329">[Import-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-330">[Importation-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-330">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-331">[Importation-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-331">[Import-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-332">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-332">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-333">[Importation-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-333">[Import-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-334">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-334">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-335">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-335">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-336">[Importation-CsRgsAudioFile](https://technet.microsoft.com/en-us/library/Gg412830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-336">[Import-CsRgsAudioFile](https://technet.microsoft.com/en-us/library/Gg412830(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-337">[Import-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-337">[Import-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205245(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-338">[Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-338">[Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-339">[Installation-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-339">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-340">[Installation-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-340">[Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-341">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-341">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-342">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-342">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-343">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-343">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-344">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-344">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-345">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-345">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-346">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-346">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-347">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-347">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-348">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-348">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-349">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-349">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-350">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-350">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-351">[Invoke-CsUcsRollback](https://technet.microsoft.com/en-us/library/JJ204661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-351">[Invoke-CsUcsRollback](https://technet.microsoft.com/en-us/library/JJ204661(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-352">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-352">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-353">[Merge-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-353">[Merge-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-354">[Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-354">[Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-355">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-355">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-356">[Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-356">[Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-357">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-357">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-358">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-358">[Move-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-359">[Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-359">[Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-360">[Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-360">[Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-361">[Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-361">[Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-362">[Move-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg398782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-362">[Move-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg398782(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-363">[Move-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-363">[Move-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-364">[Nouveau-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-364">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-365">[Nouveau-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-365">[New-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-366">[Nouveau-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-366">[New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-367">[New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-367">[New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-368">[Nouveau-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398522(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-368">[New-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398522(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-369">[Nouveau-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-369">[New-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-370">[Nouveau-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-370">[New-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-371">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-371">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-372">[Nouveau-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-372">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-373">[Nouveau-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-373">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-374">[Nouveau-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-374">[New-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-375">[Nouveau-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-375">[New-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-376">[Nouveau-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-376">[New-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-377">[Nouveau-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-377">[New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-378">[Nouveau-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-378">[New-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-379">[Nouveau-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-379">[New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-380">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-380">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-381">[Nouveau-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-381">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-382">[New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-382">[New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-383">[New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-383">[New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-384">[New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-384">[New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-385">[New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-385">[New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-386">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-386">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-387">[New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-387">[New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-388">[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-388">[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-389">[Nouveau-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-389">[New-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-390">[Nouveau-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-390">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-391">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-391">[New-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-392">[Nouveau-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-392">[New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-393">[Nouveau-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-393">[New-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-394">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-394">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-395">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-395">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-396">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-396">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-397">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-397">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-398">[New-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-398">[New-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-399">[Nouveau-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-399">[New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-400">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-400">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-401">[Nouveau-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-401">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-402">[New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-402">[New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-403">[Nouveau-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-403">[New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-404">[Nouveau-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-404">[New-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-405">[Nouveau-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-405">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-406">[Nouveau-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-406">[New-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-407">[Nouveau-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-407">[New-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-408">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-408">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-409">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-409">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-410">[Nouveau-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-410">[New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-411">[New-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-411">[New-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-412">[Nouveau-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg425881(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-412">[New-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg425881(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-413">[New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-413">[New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-414">[New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-414">[New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-415">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-415">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-416">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-416">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-417">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-417">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-418">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-418">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-419">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-419">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-420">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/en-us/library/Gg425718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-420">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/en-us/library/Gg425718(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-421">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-421">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-422">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-422">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-423">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-423">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-424">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-424">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-425">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-425">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-426">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-426">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-427">[Nouveau-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-427">[New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-428">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-428">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-429">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-429">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-430">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-430">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-431">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-431">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-432">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-432">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-433">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-433">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-434">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-434">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-435">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-435">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-436">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-436">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-437">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-437">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-438">[New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-438">[New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-439">[Nouveau-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-439">[New-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-440">[Nouveau-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-440">[New-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-441">[Nouveau-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-441">[New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-442">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-442">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-443">[Nouveau-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-443">[New-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-444">[Nouveau-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-444">[New-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-445">[New-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-445">[New-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-446">[Nouveau-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg413065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-446">[New-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg413065(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-447">[Nouveau-CsRgsAnswer](https://technet.microsoft.com/en-us/library/Gg412812(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-447">[New-CsRgsAnswer](https://technet.microsoft.com/en-us/library/Gg412812(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-448">[Nouveau-CsRgsCallAction](https://technet.microsoft.com/en-us/library/Gg398136(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-448">[New-CsRgsCallAction](https://technet.microsoft.com/en-us/library/Gg398136(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-449">[Nouveau-CsRgsHoliday](https://technet.microsoft.com/en-us/library/Gg398075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-449">[New-CsRgsHoliday](https://technet.microsoft.com/en-us/library/Gg398075(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-450">[Nouveau-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398403(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-450">[New-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398403(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-451">[Nouveau-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398291(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-451">[New-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398291(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-452">[New-CsRgsPrompt](https://technet.microsoft.com/en-us/library/Gg398486(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-452">[New-CsRgsPrompt](https://technet.microsoft.com/en-us/library/Gg398486(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-453">[Nouveau-CsRgsQuestion](https://technet.microsoft.com/en-us/library/Gg398186(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-453">[New-CsRgsQuestion](https://technet.microsoft.com/en-us/library/Gg398186(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-454">[Nouveau-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-454">[New-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398989(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-455">[Nouveau-CsRgsTimeRange](https://technet.microsoft.com/en-us/library/Gg399040(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-455">[New-CsRgsTimeRange](https://technet.microsoft.com/en-us/library/Gg399040(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-456">[Nouveau-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398246(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-456">[New-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398246(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-457">[Nouveau-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-457">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-458">[Nouveau-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398096(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-458">[New-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398096(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-459">[Nouveau-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-459">[New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-460">[Nouveau-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-460">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-461">[Nouveau-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-461">[New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-462">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-462">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-463">[Nouveau-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-463">[New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-464">[Nouveau-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-464">[New-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-465">[Nouveau-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-465">[New-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-466">[Nouveau-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-466">[New-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-467">[Nouveau-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-467">[New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-468">[Nouveau-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-468">[New-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-469">[Nouveau-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-469">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-470">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-470">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-471">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-471">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-472">[Nouveau-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-472">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-473">[Nouveau-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-473">[New-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-474">[Nouveau-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-474">[New-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-475">[New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-475">[New-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-476">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-476">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-477">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-477">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-478">[New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-478">[New-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-479">[Nouveau-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-479">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-480">[New-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398651(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-480">[New-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398651(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-481">[Nouveau-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-481">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-482">[Nouveau-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-482">[New-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-483">[New-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-483">[New-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205072(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-484">[Nouveau-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-484">[New-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-485">[Nouveau-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-485">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-486">[Nouveau-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-486">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-487">[Nouveau-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-487">[New-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-488">[Nouveau-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-488">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-489">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-489">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-490">[Nouveau-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-490">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-491">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-491">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-492">[New-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-492">[New-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-493">[Nouveau-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-493">[New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-494">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-494">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-495">[New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-495">[New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-496">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-496">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-497">[Publisher-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-497">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-498">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-498">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-499">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-499">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-500">[Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-500">[Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-501">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-501">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-502">[Remove-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg412766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-502">[Remove-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg412766(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-503">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-503">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-504">[Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-504">[Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-505">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-505">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-506">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-506">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-507">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-507">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-508">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-508">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-509">[Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-509">[Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-510">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-510">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-511">[Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-511">[Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-512">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-512">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-513">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-513">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-514">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-514">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-515">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-515">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-516">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-516">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-517">[Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-517">[Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-518">[Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-518">[Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-519">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-519">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-520">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-520">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-521">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-521">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-522">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-522">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-523">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-523">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-524">[Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-524">[Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-525">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-525">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-526">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-526">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-527">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-527">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-528">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-528">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-529">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-529">[Remove-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-530">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-530">[Remove-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-531">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-531">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-532">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-532">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-533">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-533">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-534">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-534">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-535">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-535">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-536">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-536">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-537">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-537">[Remove-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-538">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-538">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-539">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-539">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-540">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-540">[Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-541">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-541">[Remove-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-542">[Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-542">[Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-543">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-543">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-544">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-544">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-545">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-545">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-546">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-546">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-547">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-547">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-548">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-548">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-549">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-549">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-550">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-550">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-551">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-551">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-552">[Remove-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg425803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-552">[Remove-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg425803(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-553">[Remove-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-553">[Remove-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-554">[Remove-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-554">[Remove-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398705(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-555">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-555">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-556">[Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-556">[Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-557">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-557">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-558">[Remove-Csnetworkconfiguration permettent](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-558">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-559">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-559">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-560">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-560">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-561">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-561">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-562">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-562">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-563">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-563">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-564">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-564">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-565">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-565">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-566">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-566">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-567">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-567">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-568">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-568">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-569">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-569">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-570">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-570">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-571">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-571">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-572">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-572">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-573">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-573">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-574">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-574">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-575">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-575">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-576">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-576">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-577">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-577">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-578">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-578">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-579">[Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-579">[Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-580">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-580">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-581">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-581">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-582">[Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-582">[Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-583">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-583">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-584">[Remove-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-584">[Remove-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-585">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-585">[Remove-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-586">[Remove-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-586">[Remove-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-587">[Remove-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg398969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-587">[Remove-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg398969(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-588">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398521(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-588">[Remove-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398521(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-589">[Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398568(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-589">[Remove-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398568(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-590">[Remove-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398576(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-590">[Remove-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398576(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-591">[Remove-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398765(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-591">[Remove-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398765(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-592">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-592">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-593">[Remove-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398366(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-593">[Remove-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398366(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-594">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-594">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-595">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-595">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-596">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-596">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-597">[Remove-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-597">[Remove-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703201(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-598">[Remove-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703203(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-598">[Remove-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703203(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-599">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-599">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-600">[Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-600">[Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-601">[Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-601">[Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-602">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-602">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-603">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-603">[Remove-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-604">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-604">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-605">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-605">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-606">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-606">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-607">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-607">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-608">[Remove-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398209(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-608">[Remove-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398209(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-609">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398982(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-609">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398982(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-610">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-610">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-611">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-611">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-612">[Remove-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-612">[Remove-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204629(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-613">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-613">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-614">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-614">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-615">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-615">[Remove-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-616">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-616">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-617">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-617">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-618">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-618">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-619">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-619">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-620">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-620">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-621">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-621">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-622">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-622">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-623">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-623">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-624">[Requête-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-624">[Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-625">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-625">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-626">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-626">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-627">[Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-627">[Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-628">[Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-628">[Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-629">[Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-629">[Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-630">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-630">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-631">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-631">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-632">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-632">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-633">[Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-633">[Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-634">[Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-634">[Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-635">[Set-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg425752(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-635">[Set-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg425752(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-636">[Set-CsApplicationServer](https://technet.microsoft.com/en-us/library/Gg398562(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-636">[Set-CsApplicationServer](https://technet.microsoft.com/en-us/library/Gg398562(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-637">[Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-637">[Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-638">[Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-638">[Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-639">[Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-639">[Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-640">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-640">[Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-641">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-641">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-642">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-642">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-643">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-643">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-644">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-644">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-645">[Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-645">[Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-646">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-646">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-647">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-647">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-648">[Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-648">[Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-649">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-649">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-650">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-650">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-651">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-651">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-652">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-652">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-653">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-653">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-654">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-654">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-655">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-655">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-656">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-656">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-657">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-657">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-658">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-658">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-659">[Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-659">[Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-660">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-660">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-661">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-661">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-662">[Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-662">[Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-663">[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-663">[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-664">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-664">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-665">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-665">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-666">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-666">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-667">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-667">[Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-668">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-668">[Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-669">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-669">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-670">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-670">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-671">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-671">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-672">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15)) Set-CsDialPlan</span><span class="sxs-lookup"><span data-stu-id="96bdd-672">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))Set-CsDialPlan</span></span>

  - <span data-ttu-id="96bdd-673">[Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-673">[Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-674">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-674">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-675">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-675">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-676">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-676">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-677">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-677">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-678">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-678">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-679">[Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-679">[Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-680">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-680">[Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-681">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-681">[Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-682">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-682">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-683">[Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-683">[Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-684">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-684">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-685">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-685">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-686">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-686">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-687">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-687">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-688">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-688">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-689">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-689">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-690">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-690">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-691">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-691">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-692">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-692">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-693">[Set-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg413045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-693">[Set-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg413045(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-694">[Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-694">[Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-695">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-695">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-696">[Set-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398580(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-696">[Set-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398580(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-697">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-697">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-698">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-698">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-699">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-699">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-700">[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-700">[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-701">[Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-701">[Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-702">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-702">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-703">[Set-Csnetworkconfiguration permettent](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-703">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-704">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-704">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-705">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-705">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-706">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-706">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-707">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-707">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-708">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-708">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-709">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-709">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-710">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-710">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-711">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-711">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-712">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-712">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-713">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-713">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-714">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-714">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-715">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-715">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-716">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-716">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-717">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-717">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-718">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-718">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-719">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-719">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-720">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-720">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-721">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-721">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-722">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-722">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-723">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-723">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-724">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-724">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-725">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-725">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-726">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-726">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-727">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-727">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-728">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-728">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-729">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-729">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-730">[Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-730">[Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-731">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-731">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-732">[Set-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-732">[Set-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-733">[Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-733">[Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-734">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-734">[Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-735">[Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-735">[Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-736">[Set-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-736">[Set-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425955(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-737">[Set-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg425728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-737">[Set-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg425728(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-738">[Set-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-738">[Set-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398736(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-739">[Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg412929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-739">[Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg412929(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-740">[Set-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-740">[Set-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412947(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-741">[Set-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-741">[Set-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425845(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-742">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-742">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-743">[Set-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg412850(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-743">[Set-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg412850(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-744">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-744">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-745">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-745">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-746">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-746">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-747">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-747">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-748">[Set-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703202(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-748">[Set-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703202(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-749">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-749">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-750">[Set-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-750">[Set-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-751">[Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-751">[Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-752">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-752">[Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-753">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-753">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-754">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-754">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-755">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-755">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-756">[Set-CsUICulture](https://technet.microsoft.com/en-us/library/Gg398354(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-756">[Set-CsUICulture](https://technet.microsoft.com/en-us/library/Gg398354(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-757">[Set-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg399033(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-757">[Set-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg399033(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-758">[Set-CsUser](https://technet.microsoft.com/en-us/library/Gg398510(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-758">[Set-CsUser](https://technet.microsoft.com/en-us/library/Gg398510(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-759">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg413018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-759">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg413018(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-760">[Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-760">[Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-761">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-761">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-762">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-762">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-763">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-763">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-764">[Set-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205414(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-764">[Set-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205414(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-765">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-765">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-766">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-766">[Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-767">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-767">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-768">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-768">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-769">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-769">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-770">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-770">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-771">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-771">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-772">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-772">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-773">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-773">[Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-774">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-774">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-775">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-775">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-776">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-776">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-777">[Démarrer-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-777">[Start-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-778">[Stop-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-778">[Stop-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-779">[Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-779">[Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-780">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-780">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-781">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-781">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-782">[Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-782">[Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-783">[Test-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/JJ205117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-783">[Test-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/JJ205117(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-784">[Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-784">[Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-785">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-785">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-786">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-786">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-787">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-787">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-788">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-788">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-789">[Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-789">[Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-790">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-790">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-791">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-791">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-792">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-792">[Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-793">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-793">[Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-794">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-794">[Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-795">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-795">[Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-796">[Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-796">[Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-797">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-797">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-798">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-798">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-799">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-799">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-800">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-800">[Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-801">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-801">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-802">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-802">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-803">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-803">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-804">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-804">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-805">[Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-805">[Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-806">[Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-806">[Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-807">[Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-807">[Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-808">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-808">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-809">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-809">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-810">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-810">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-811">[Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-811">[Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-812">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-812">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-813">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-813">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-814">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-814">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-815">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-815">[Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-816">[Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-816">[Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-817">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-817">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-818">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-818">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-819">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-819">[Test-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-820">[Test-CsUnifiedContactStore](https://technet.microsoft.com/en-us/library/JJ204662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-820">[Test-CsUnifiedContactStore](https://technet.microsoft.com/en-us/library/JJ204662(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-821">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-821">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-822">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-822">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-823">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-823">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-824">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-824">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-825">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-825">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-826">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-826">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-827">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-827">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-828">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-828">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-829">[Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-829">[Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-830">[Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-830">[Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-831">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-831">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-832">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-832">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-833">[Unlock-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-833">[Unlock-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-834">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-834">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-835">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-835">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-836">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-836">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-837">[Update-CsTenantMeetingUrl](https://technet.microsoft.com/en-us/library/Dn424754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-837">[Update-CsTenantMeetingUrl](https://technet.microsoft.com/en-us/library/Dn424754(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-838">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-838">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span></span>

  - <span data-ttu-id="96bdd-839">[Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96bdd-839">[Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

