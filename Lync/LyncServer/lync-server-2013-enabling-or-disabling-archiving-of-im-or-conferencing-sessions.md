---
title: Activation ou désactivation de l’archivage des sessions de messagerie instantanée ou de conférence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be9782bfa73f30fbefaec0a51d91024b3c40ba55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="bc976-102">Activation ou désactivation de l’archivage des sessions de messagerie instantanée ou de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc976-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc976-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="bc976-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="bc976-104">Dans Lync Server 2013 panneau de configuration, vous utilisez des configurations d’archivage pour activer et désactiver l’archivage des messages instantanés ou des sessions de conférence.</span><span class="sxs-lookup"><span data-stu-id="bc976-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="bc976-105">Cela inclut les configurations d’archivage suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc976-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="bc976-106">Configuration globale créée par défaut lors du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc976-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="bc976-107">Configurations facultatives de niveau de site et de niveau groupe que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="bc976-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="bc976-108">Vous définissez initialement des configurations d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="bc976-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="bc976-109">Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.</span><span class="sxs-lookup"><span data-stu-id="bc976-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bc976-110">Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il convient d’activer l’archivage pour les communications internes, pour les communications externes ou pour les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc976-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="bc976-111">Par défaut, l’archivage n’est pas activé pour les communications internes et externes.</span><span class="sxs-lookup"><span data-stu-id="bc976-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="bc976-112">Avant d’activer l’archivage dans toutes les stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, si vous le souhaitez, pour des sites et des groupes spécifiques, comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="bc976-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="bc976-113">Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bc976-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="bc976-114">Si vous décidez après le déploiement de l’archivage dans lequel vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devez supprimer la configuration de la base de données SQL Server à partir de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="bc976-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="bc976-115">Pour ce faire, vous devez utiliser le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="bc976-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="bc976-116">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-changing-archiving-database-options.md">modifier les options de base de données d’archivage dans Lync Server 2013</A> dans la documentation sur les opérations</span><span class="sxs-lookup"><span data-stu-id="bc976-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="bc976-117">Pour activer ou désactiver l’archivage des sessions de messagerie instantanée ou de conférence</span><span class="sxs-lookup"><span data-stu-id="bc976-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="bc976-118">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="bc976-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bc976-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc976-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bc976-120">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bc976-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bc976-121">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="bc976-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="bc976-122">Sélectionnez la configuration de pool, de site ou globale appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bc976-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="bc976-123">Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.</span><span class="sxs-lookup"><span data-stu-id="bc976-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="bc976-124">Pour activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.</span><span class="sxs-lookup"><span data-stu-id="bc976-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="bc976-125">Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="bc976-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="bc976-126">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="bc976-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc976-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc976-127">See Also</span></span>


[<span data-ttu-id="bc976-128">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</span><span class="sxs-lookup"><span data-stu-id="bc976-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="bc976-129">Configuration et affectation de stratégies d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc976-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

