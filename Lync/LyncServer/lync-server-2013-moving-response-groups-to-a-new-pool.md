---
title: 'Lync Server 2013 : transfert de groupes Response Group vers un nouveau pool'
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
ms.openlocfilehash: 562d519e278096acf589482124eeb9cdf7ebf189
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="e73ed-102">Transfert de groupes Response Group vers un nouveau pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e73ed-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e73ed-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e73ed-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e73ed-104">Lync Server 2013 introduit une nouvelle prise en charge des cmdlets pour le transfert de groupes Response Group d’un pool vers un autre, même si le nom de domaine complet (FQDN) est différent.</span><span class="sxs-lookup"><span data-stu-id="e73ed-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="e73ed-105">Suivez les étapes de la procédure ci-après pour déplacer des groupes Response Group d’un pool frontal vers un autre.</span><span class="sxs-lookup"><span data-stu-id="e73ed-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e73ed-106">Dans un environnement de coexistence, vous pouvez déplacer des groupes Response Group uniquement entre&nbsp;des pools frontaux Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e73ed-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="e73ed-107">Pour déplacer les groupes Response Group avec un nom de domaine complet différent</span><span class="sxs-lookup"><span data-stu-id="e73ed-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="e73ed-108">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e73ed-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e73ed-p101">Exportez les groupes Response Group dans le pool source. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p101">Export the response groups in the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="e73ed-111">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e73ed-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="e73ed-p102">Pour supprimer les groupes Response Group du pool source durant l’exportation, incluez le paramètre –RemoveExportedConfiguration. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p102">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter. For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="e73ed-p103">Importez les groupes Response Group vers le pool de destination et affectez ce dernier comme nouveau propriétaire. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p103">Import the response groups to the destination pool and assign the destination pool as the new owner. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="e73ed-116">Si vous souhaitez également copier les paramètres de niveau application de Response Group depuis le pool source vers le pool de destination, incluez le paramètre – ReplaceExistingRgsSettings.</span><span class="sxs-lookup"><span data-stu-id="e73ed-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="e73ed-117">Vous ne pouvez définir qu’un seul ensemble de paramètres de niveau d’application par pool.</span><span class="sxs-lookup"><span data-stu-id="e73ed-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="e73ed-118">Si vous copiez les paramètres de niveau d’application du pool source vers le pool de destination, les paramètres du pool source remplacent ceux du pool de destination.</span><span class="sxs-lookup"><span data-stu-id="e73ed-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="e73ed-119">Si vous ne copiez pas les paramètres de niveau d’application du pool source, les paramètres existants du pool de destination s’appliquent aux groupes Response Group importés.</span><span class="sxs-lookup"><span data-stu-id="e73ed-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="e73ed-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e73ed-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e73ed-121">Les paramètres de niveau d’application comprennent la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de la reprise d’appel parqué des agents ainsi que la configuration du contexte de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e73ed-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="e73ed-122">Pour afficher ces paramètres de configuration, exécutez l’applet de commande <STRONG>Get-CsRgsConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e73ed-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="e73ed-123">Pour plus d’informations sur cette applet de commande, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-applet csrgsconfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="e73ed-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="e73ed-124">Vérifiez que l’importation est réussie en affichant la configuration des groupes Response Group importés. Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e73ed-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="e73ed-p106">Vérifiez que tous les flux de travail ont été importés. Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p106">Verify that all the workflows were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="e73ed-p107">Vérifiez que toutes les files d’attente ont été importées. Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p107">Verify that all the queues were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="e73ed-p108">Vérifiez que tous les groupes d’agents ont été importés. Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p108">Verify that all the agent groups were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="e73ed-p109">Vérifiez que toutes les heures ouvrées ont été importées. Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p109">Verify that all the hours of business were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="e73ed-p110">Vérifiez que tous les groupes de congés ont été importés. Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p110">Verify that all the holiday sets were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="e73ed-135">Vérifiez que l’importation est réussie en appelant un des groupes Response Group et en vérifiant que l’appel est correctement traité.</span><span class="sxs-lookup"><span data-stu-id="e73ed-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="e73ed-136">Demandez aux agents membres des groupes d’agents formels de s’inscrire à leurs groupes d’agents dans le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="e73ed-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="e73ed-p111">Si vous n’avez pas précédemment supprimé les groupes Response Group du pool source, supprimez-les. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="e73ed-p111">If you did not previously remove response groups from the source pool, remove the response groups from the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="e73ed-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e73ed-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

