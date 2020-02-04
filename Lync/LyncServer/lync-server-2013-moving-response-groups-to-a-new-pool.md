---
title: 'Lync Server 2013 : déplacer des groupes de réponse vers un nouveau pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="d08c5-102">Déplacer des groupes de réponse vers un nouveau pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d08c5-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d08c5-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d08c5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d08c5-104">Lync Server 2013 introduit une nouvelle cmdlet support pour le déplacement de groupes de réponse d’un pool vers un autre, même si le nom de domaine complet (FQDN) est différent.</span><span class="sxs-lookup"><span data-stu-id="d08c5-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="d08c5-105">Suivez les étapes décrites dans la procédure ci-dessous pour déplacer les groupes de réponse d’un pool frontal vers un autre à l’aide d’un nom de domaine complet différent.</span><span class="sxs-lookup"><span data-stu-id="d08c5-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d08c5-106">Dans un environnement de coexistence, vous pouvez déplacer des groupes de réponse uniquement entre&nbsp;les pools front end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d08c5-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="d08c5-107">Pour déplacer des groupes de réponses vers un pool avec un nom de domaine complet différent</span><span class="sxs-lookup"><span data-stu-id="d08c5-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="d08c5-108">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d08c5-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d08c5-109">Exportez les groupes de réponses dans le pool de sources.</span><span class="sxs-lookup"><span data-stu-id="d08c5-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="d08c5-110">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d08c5-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="d08c5-111">Exemple :</span><span class="sxs-lookup"><span data-stu-id="d08c5-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="d08c5-112">Pour supprimer les groupes de réponse du pool de sources lors de l’exportation, incluez le paramètre – RemoveExportedConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d08c5-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="d08c5-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d08c5-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="d08c5-114">Importez les groupes de réponses dans le pool de destination et attribuez le pool de destination comme nouveau propriétaire.</span><span class="sxs-lookup"><span data-stu-id="d08c5-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="d08c5-115">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d08c5-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="d08c5-116">Si vous voulez également copier les paramètres au niveau de l’application du groupe de réponses du pool de sources vers le pool de destination, incluez le paramètre – ReplaceExistingRgsSettings.</span><span class="sxs-lookup"><span data-stu-id="d08c5-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="d08c5-117">Vous pouvez définir un seul ensemble de paramètres de niveau application par pool.</span><span class="sxs-lookup"><span data-stu-id="d08c5-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="d08c5-118">Si vous copiez les paramètres au niveau de l’application à partir du pool de sources vers le pool de destination, les paramètres du pool de sources remplacent ceux du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="d08c5-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="d08c5-119">Si vous ne copiez pas les paramètres au niveau de l’application à partir du pool de sources, les paramètres existants du pool de destination s’appliquent aux groupes de réponse importés.</span><span class="sxs-lookup"><span data-stu-id="d08c5-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="d08c5-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d08c5-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d08c5-121">Les paramètres au niveau de l’application incluent la configuration par défaut de Music-Holding, le fichier audio de musique par défaut, la période de grâce aux retours de l’agent et la configuration du contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="d08c5-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="d08c5-122">Pour afficher ces paramètres de configuration, exécutez l’applet <STRONG>de passe Get-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d08c5-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="d08c5-123">Pour plus d’informations sur cette cmdlet, voir <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="d08c5-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="d08c5-124">Assurez-vous que l’importation réussie s’affiche avec la configuration de groupe de réponse importée en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="d08c5-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="d08c5-125">Vérifiez que tous les flux de travail étaient importés.</span><span class="sxs-lookup"><span data-stu-id="d08c5-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="d08c5-126">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d08c5-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d08c5-127">Vérifiez que toutes les files d’attente ont été importées.</span><span class="sxs-lookup"><span data-stu-id="d08c5-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="d08c5-128">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d08c5-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d08c5-129">Vérifiez que tous les groupes d’agents ont été importés.</span><span class="sxs-lookup"><span data-stu-id="d08c5-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="d08c5-130">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d08c5-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="d08c5-131">Vérifiez que toutes les heures d’activité ont été importées.</span><span class="sxs-lookup"><span data-stu-id="d08c5-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="d08c5-132">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d08c5-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="d08c5-133">Vérifiez que tous les ensembles de jours fériés ont été importés.</span><span class="sxs-lookup"><span data-stu-id="d08c5-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="d08c5-134">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d08c5-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="d08c5-135">Vérifiez que l’importation est réussie en passant un appel à l’un des groupes de réponses et en vérifiant que l’appel est géré correctement.</span><span class="sxs-lookup"><span data-stu-id="d08c5-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="d08c5-136">Demandez aux agents membres de groupes d’agents formels de se connecter à leurs groupes d’agents dans le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="d08c5-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="d08c5-137">Si vous n’avez pas encore supprimé les groupes de réponses du pool de sources, supprimez les groupes de réponses du pool de sources.</span><span class="sxs-lookup"><span data-stu-id="d08c5-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="d08c5-138">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d08c5-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="d08c5-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d08c5-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

