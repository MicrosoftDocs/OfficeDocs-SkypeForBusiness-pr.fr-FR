---
title: 'Lync Server 2013 : gestion des options de configuration de l’archivage pour votre organisation, vos sites et vos pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd9b777f3c7dbfc008f0b985a9c1512aaeb52d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498361"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="4e58e-102">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</span><span class="sxs-lookup"><span data-stu-id="4e58e-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e58e-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4e58e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4e58e-104">Dans le panneau de configuration Lync Server 2013, vous utilisez des configurations d’archivage pour spécifier le mode d’implémentation de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="4e58e-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="4e58e-105">Les configurations d’archivage sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e58e-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="4e58e-106">Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e58e-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="4e58e-107">Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière d’implémenter l’archivage de sites ou de pools spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4e58e-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="4e58e-108">Vous commencez par définir des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement.</span><span class="sxs-lookup"><span data-stu-id="4e58e-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="4e58e-109">Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la page Configuration de l' **archivage** du groupe **archivage et surveillance** pour gérer les configurations au niveau global, au niveau du site et au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="4e58e-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="4e58e-110">Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="4e58e-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e58e-111">Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour indiquer si l’archivage doit être activé pour les communications internes, pour les communications externes ou pour les deux pour tous les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e58e-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="4e58e-112">Par défaut, l’archivage n’est pas activé pour les communications internes ou externes.</span><span class="sxs-lookup"><span data-stu-id="4e58e-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="4e58e-113">Si vous utilisez l’intégration de Microsoft Exchange, vous devez activer et configurer Exchange 2013 afin de prendre en charge l’archivage pour tous les utilisateurs hébergés sur Exchange 2013 dont les boîtes aux lettres ont été placées en conservation In-Place.</span><span class="sxs-lookup"><span data-stu-id="4e58e-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="4e58e-114">Avant d’activer l’archivage, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="4e58e-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="4e58e-115">Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving Policies in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4e58e-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="4e58e-116">**Pour afficher les informations de configuration d’archivage à l’aide des applets de commande Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4e58e-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="4e58e-117">Vous pouvez afficher les informations de configuration d’archivage à l’aide de Windows PowerShell et de la cmdlet **Get-applet csarchivingconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4e58e-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="4e58e-118">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e58e-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4e58e-119">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="4e58e-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="4e58e-120">Dans Lync Server Management Shell, utilisez la commande suivante pour afficher les informations sur tous les paramètres de configuration de l’archivage :</span><span class="sxs-lookup"><span data-stu-id="4e58e-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e58e-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4e58e-121">In This Section</span></span>

  - [<span data-ttu-id="4e58e-122">Création d’une configuration d’archivage dans Lync Server 2013 pour gérer l’archivage de sites ou de pools spécifiques</span><span class="sxs-lookup"><span data-stu-id="4e58e-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="4e58e-123">Activation ou désactivation de l’archivage des sessions de messagerie instantanée ou de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58e-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="4e58e-124">Activation ou désactivation de la purge des données archivées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58e-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="4e58e-125">Activation ou désactivation du mode critique dans Lync Server 2013 pour bloquer ou autoriser les sessions de messagerie instantanée et de conférence Web en cas d’échec de l’archivage</span><span class="sxs-lookup"><span data-stu-id="4e58e-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="4e58e-126">Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58e-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="4e58e-127">Activation ou désactivation de l’intégration de Lync Server 2013 avec le stockage Exchange</span><span class="sxs-lookup"><span data-stu-id="4e58e-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="4e58e-128">Suppression d’une configuration d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58e-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e58e-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e58e-129">See Also</span></span>


[<span data-ttu-id="4e58e-130">Gestion de l’archivage Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58e-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

