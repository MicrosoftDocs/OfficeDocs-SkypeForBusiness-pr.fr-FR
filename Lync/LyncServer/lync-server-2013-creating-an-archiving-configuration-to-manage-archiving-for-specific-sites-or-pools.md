---
title: 'Lync Server 2013 : création d’une configuration d’archivage pour gérer l’archivage de sites ou de pools spécifiques'
description: 'Lync Server 2013 : création d’une configuration d’archivage pour gérer l’archivage de sites ou de pools spécifiques.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ab19f2d8900693ef0fcb14d8f6d862b22c355bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563110"
---
# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="ed0e5-103">Création d’une configuration d’archivage dans Lync Server 2013 pour gérer l’archivage de sites ou de pools spécifiques</span><span class="sxs-lookup"><span data-stu-id="ed0e5-103">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed0e5-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ed0e5-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ed0e5-105">Dans le panneau de configuration Lync Server 2013, vous utilisez des configurations d’archivage pour contrôler l’implémentation de l’archivage dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-105">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="ed0e5-106">Les configurations d’archivage sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed0e5-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="ed0e5-107">Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="ed0e5-108">Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière d’implémenter l’archivage de sites ou de pools spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="ed0e5-109">Vous commencez par définir des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="ed0e5-110">Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed0e5-111">Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il faut activer l’archivage pour les communications internes, pour les communications externes ou pour les deux pour les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="ed0e5-112">Par défaut, l’archivage n’est pas activé pour les communications internes ou externes.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="ed0e5-113">Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-113">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="ed0e5-114">Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving Policies in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="ed0e5-115">Si vous décidez après avoir déployé l’archivage dans lequel vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données d’archivage et les fichiers sur les serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devez supprimer la configuration de la base de données SQL Server de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="ed0e5-116">Pour ce faire, vous devez utiliser le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="ed0e5-117">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving Database options in Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="ed0e5-118">Pour créer une configuration d’archivage pour un site ou un pool</span><span class="sxs-lookup"><span data-stu-id="ed0e5-118">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="ed0e5-119">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ed0e5-120">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ed0e5-121">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ed0e5-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ed0e5-122">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="ed0e5-123">Dans la page **configuration de l’archivage** , cliquez sur **nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed0e5-123">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ed0e5-124">Pour créer une configuration d’archivage de site, cliquez sur **configuration du site** puis, dans **Sélectionner un site**, sélectionnez le site à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-124">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="ed0e5-125">Pour créer une configuration d’archivage de pool, cliquez sur **configuration du pool** , puis, dans **Sélectionner un pool**, sélectionnez le pool à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-125">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="ed0e5-126">Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed0e5-126">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="ed0e5-127">Afin d’activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-127">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="ed0e5-128">Pour activer l’archivage pour les sessions de messagerie instantanée et les conférences Web, cliquez sur **archiver les sessions de messagerie instantanée et de conférence Web**.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-128">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="ed0e5-129">Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-129">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="ed0e5-130">Dans **Créer un paramètre d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed0e5-130">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="ed0e5-131">Pour bloquer toute activité quand l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-131">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="ed0e5-132">Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="ed0e5-132">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="ed0e5-133">Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed0e5-133">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="ed0e5-134">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-134">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="ed0e5-135">Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-135">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="ed0e5-136">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ed0e5-137">Création de paramètres de configuration d’archivage à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed0e5-137">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ed0e5-138">Les paramètres de configuration de l’archivage peuvent être créés à l’aide de Windows PowerShell et de l’applet de commande New-CsArchivingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-138">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="ed0e5-139">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-139">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ed0e5-140">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="ed0e5-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="ed0e5-141">Pour créer une nouvelle collection de paramètres de configuration d’archivage pour un site</span><span class="sxs-lookup"><span data-stu-id="ed0e5-141">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="ed0e5-142">La commande suivante crée une nouvelle collection de paramètres de configuration d’archivage pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="ed0e5-142">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="ed0e5-143">Pour créer une nouvelle collection de paramètres de configuration d’archivage qui autorise uniquement l’archivage de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="ed0e5-143">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="ed0e5-144">Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-144">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="ed0e5-145">Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-145">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="ed0e5-146">Par exemple, pour créer une collection de paramètres de configuration d’archivage qui, par défaut, autorise l’archivage des sessions de messagerie instantanée, utilisez uniquement une commande comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="ed0e5-146">For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="ed0e5-147">Pour spécifier plusieurs valeurs de propriétés lors de la création des paramètres de configuration d’archivage</span><span class="sxs-lookup"><span data-stu-id="ed0e5-147">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="ed0e5-148">Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="ed0e5-148">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="ed0e5-149">Par exemple, cette commande configure les nouveaux paramètres pour archiver les sessions de messagerie instantanée et bloquer la messagerie instantanée du service d’archivage n’est pas disponible :</span><span class="sxs-lookup"><span data-stu-id="ed0e5-149">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="ed0e5-150">Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [New-applet csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ed0e5-150">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed0e5-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed0e5-151">See Also</span></span>


[<span data-ttu-id="ed0e5-152">Fonctionnement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0e5-152">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="ed0e5-153">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</span><span class="sxs-lookup"><span data-stu-id="ed0e5-153">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

