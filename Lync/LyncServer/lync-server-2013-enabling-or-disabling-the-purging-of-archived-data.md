---
title: 'Lync Server 2013 : activation ou désactivation de la purge des données archivées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d8ee7858e339029fa29c803400ac836871515b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="9c3a6-102">Activation ou désactivation de la purge des données archivées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c3a6-102">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c3a6-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9c3a6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9c3a6-104">Dans le panneau de configuration Lync Server 2013, vous utilisez des configurations d’archivage pour activer et désactiver le vidage et configurer la mise en œuvre de la purge.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="9c3a6-105">Les configurations d’archivage sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c3a6-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="9c3a6-106">Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="9c3a6-107">Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière d’implémenter l’archivage de sites ou de pools spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="9c3a6-108">Vous commencez par définir des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="9c3a6-109">Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c3a6-110">Pour utiliser l’archivage pour les utilisateurs hébergés sur Lync Server 2013, vous devez configurer des stratégies d’archivage pour spécifier s’il faut activer l’archivage pour les communications internes, pour les communications externes ou pour les deux.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-110">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="9c3a6-111">Par défaut, l’archivage n’est pas activé pour les communications internes ou externes.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="9c3a6-112">Avant d’activer l’archivage dans une stratégie, vous devez spécifier les configurations d’archivage adéquates pour votre déploiement et, éventuellement, pour des sites et des pools spécifiques, comme cela est décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="9c3a6-113">Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving Policies in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="9c3a6-114">Si vous décidez après avoir déployé l’archivage dans lequel vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devez supprimer la configuration de la base de données SQL Server. à partir de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="9c3a6-115">Pour ce faire, vous devez utiliser le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="9c3a6-116">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving Database options in Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="9c3a6-117">Pour activer ou désactiver le vidage de l’archivage</span><span class="sxs-lookup"><span data-stu-id="9c3a6-117">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="9c3a6-118">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9c3a6-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9c3a6-120">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9c3a6-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9c3a6-121">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="9c3a6-122">Cliquez sur le nom de la configuration appropriée (globale, du site ou du pool) dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9c3a6-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="9c3a6-123">Pour activer le vidage, activez la case à cocher **Activer le vidage des données d’archivage** et effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c3a6-123">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="9c3a6-124">Pour vider tous les enregistrements, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-124">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="9c3a6-125">Pour ne purger que les données qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-125">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="9c3a6-126">Pour désactiver le vidage, désactivez la case à cocher **Activer le vidage des données d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-126">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="9c3a6-127">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9c3a6-128">Activation ou désactivation de la purge des données d’archivage à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c3a6-128">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9c3a6-129">L’activation et la désactivation de la purge automatisée des données d’archivage peuvent être gérées à l’aide de Windows PowerShell et de la cmdlet **Set-applet csarchivingconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9c3a6-129">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="9c3a6-130">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9c3a6-131">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="9c3a6-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="9c3a6-132">Pour activer le vidage de toutes les données d’archivage</span><span class="sxs-lookup"><span data-stu-id="9c3a6-132">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="9c3a6-133">Pour activer le vidage de toutes les données d’archivage, définissez la propriété **EnablePurging** sur true ($True).</span><span class="sxs-lookup"><span data-stu-id="9c3a6-133">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="9c3a6-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9c3a6-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="9c3a6-135">Une fois cette commande exécutée, Lync Server purge tous les enregistrements d’archivage antérieurs à la valeur spécifiée pour la propriété **KeepArchivingDataForDays** .</span><span class="sxs-lookup"><span data-stu-id="9c3a6-135">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="9c3a6-136">Pour activer la purge uniquement des données d’archivage exportées</span><span class="sxs-lookup"><span data-stu-id="9c3a6-136">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="9c3a6-137">Pour limiter la purge aux enregistrements d’archivage qui ont été exportés vers un fichier de données (à l’aide de la cmdlet [Export-applet csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), vous devez également définir la propriété PurgeExportedArchivesOnly sur True ($true).</span><span class="sxs-lookup"><span data-stu-id="9c3a6-137">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="9c3a6-138">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9c3a6-138">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="9c3a6-139">Une fois cette commande exécutée, Lync Server n’efface que les enregistrements d’archivage qui répondent à deux critères : 1) ils sont plus anciens que la valeur spécifiée pour la propriété **KeepArchivingDataForDays** ; et, 2) qu’ils ont été exportés à l’aide de la cmdlet **Export-applet csarchivingdata** .</span><span class="sxs-lookup"><span data-stu-id="9c3a6-139">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="9c3a6-140">Pour désactiver le vidage de toutes les données d’archivage</span><span class="sxs-lookup"><span data-stu-id="9c3a6-140">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="9c3a6-141">Pour désactiver le vidage automatique des enregistrements d’archivage, définissez la propriété **EnablePurging** sur False ($False).</span><span class="sxs-lookup"><span data-stu-id="9c3a6-141">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="9c3a6-142">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9c3a6-142">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="9c3a6-143">Pour plus d’informations, y compris des options supplémentaires pour purger les données d’archivage, voir la rubrique d’aide relative à la cmdlet [Set-applet csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9c3a6-143">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c3a6-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c3a6-144">See Also</span></span>


[<span data-ttu-id="9c3a6-145">Fonctionnement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c3a6-145">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="9c3a6-146">Configuration et affectation de stratégies d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c3a6-146">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="9c3a6-147">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</span><span class="sxs-lookup"><span data-stu-id="9c3a6-147">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

