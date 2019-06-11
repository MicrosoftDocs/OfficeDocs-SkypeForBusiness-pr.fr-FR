---
title: 'Lync Server 2013: gestion des options de configuration de l’archivage pour votre organisation, vos sites et vos pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10efbf23a503364de7034651d94ced43a8d7b750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="66e5a-102">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</span><span class="sxs-lookup"><span data-stu-id="66e5a-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66e5a-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="66e5a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="66e5a-104">Dans Lync Server 2013 panneau de configuration, vous utilisez des configurations d’archivage pour spécifier la façon dont l’archivage est implémenté.</span><span class="sxs-lookup"><span data-stu-id="66e5a-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="66e5a-105">Cela inclut les configurations d’archivage suivantes:</span><span class="sxs-lookup"><span data-stu-id="66e5a-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="66e5a-106">Configuration globale créée par défaut lors du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66e5a-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="66e5a-107">Configurations facultatives de niveau de site et de niveau groupe que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="66e5a-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="66e5a-108">Vous définissez initialement des configurations d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="66e5a-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="66e5a-109">Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la page **configuration** de l’archivage du groupe **archivage et surveillance** pour gérer les configurations au niveau global, au niveau du site et au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="66e5a-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="66e5a-110">Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, déploiement documentation ou documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="66e5a-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66e5a-111">Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il convient d’activer l’archivage des communications internes, pour les communications externes ou pour tous les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66e5a-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="66e5a-112">Par défaut, l’archivage n’est pas activé pour les communications internes et externes.</span><span class="sxs-lookup"><span data-stu-id="66e5a-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="66e5a-113">Si vous utilisez l’intégration de Microsoft Exchange, vous devez activer et configurer Exchange 2013 pour la prise en charge de l’archivage de tous les utilisateurs hébergés sur Exchange 2013 qui ont reçu leurs boîtes aux lettres dans le blocage sur place.</span><span class="sxs-lookup"><span data-stu-id="66e5a-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="66e5a-114">Avant de procéder à l’archivage, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, si vous le souhaitez, pour des sites et des groupes spécifiques, comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="66e5a-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="66e5a-115">Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="66e5a-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="66e5a-116">**Pour afficher les informations de configuration de l’archivage à l’aide des cmdlets Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="66e5a-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="66e5a-117">Vous pouvez afficher les informations de configuration de l’archivage à l’aide de Windows PowerShell et de l’applet **de cmdlet Get-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="66e5a-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="66e5a-118">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66e5a-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="66e5a-119">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="66e5a-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="66e5a-120">Dans Lync Server Management Shell, utilisez la commande suivante pour afficher les informations relatives à l’ensemble de vos paramètres de configuration de l’archivage:</span><span class="sxs-lookup"><span data-stu-id="66e5a-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="66e5a-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="66e5a-121">In This Section</span></span>

  - [<span data-ttu-id="66e5a-122">Créer une configuration d’archivage dans Lync Server 2013 pour gérer l’archivage de sites ou de groupes spécifiques</span><span class="sxs-lookup"><span data-stu-id="66e5a-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="66e5a-123">Activation ou désactivation de l’archivage des sessions de messagerie instantanée ou de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e5a-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="66e5a-124">Activation ou désactivation de la suppression de données archivées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e5a-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="66e5a-125">Activation ou désactivation du mode critique dans Lync Server 2013 pour bloquer ou autoriser des sessions de messagerie instantanée et de conférence Web en cas d’échec de l’archivage</span><span class="sxs-lookup"><span data-stu-id="66e5a-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [<span data-ttu-id="66e5a-126">Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e5a-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="66e5a-127">Activation ou désactivation de l’intégration de Lync Server 2013 avec le stockage Exchange</span><span class="sxs-lookup"><span data-stu-id="66e5a-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="66e5a-128">Suppression d’une configuration d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e5a-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66e5a-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66e5a-129">See Also</span></span>


[<span data-ttu-id="66e5a-130">Gestion de l’archivage Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e5a-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

