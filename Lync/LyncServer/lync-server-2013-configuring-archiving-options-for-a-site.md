---
title: 'Lync Server 2013 : configuration des options d’archivage pour un site'
description: 'Lync Server 2013 : configuration des options d’archivage pour un site.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2db164d7c4c1cdda158387be62c0eb535fac662f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562560"
---
# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="955a4-103">Configuration des options d’archivage pour un site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="955a4-103">Configuring Archiving options for a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="955a4-104">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="955a4-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="955a4-p101">Vous pouvez spécifier l’application d’options d’archivage à des sites spécifiques en créant et en configurant les options appropriées dans une configuration d’archivage pour chacun de ces sites. La configuration d’un site remplace la configuration globale, mais uniquement pour le site spécifié dans la configuration du site.</span><span class="sxs-lookup"><span data-stu-id="955a4-p101">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites. A site configuration overrides the global configuration, but only for the site specified in the site configuration. Pool configurations override site configurations</span></span>

<span data-ttu-id="955a4-108">Pour plus d’informations sur le fonctionnement des configurations d’archivage, notamment la hiérarchie des configurations globale, de site et de pool, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="955a4-108">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="955a4-109">Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="955a4-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="955a4-110">Pour activer l’archivage, vous devez spécifier les stratégies d’archivage qui contrôlent l’archivage des communications internes et externes au niveau global et, si nécessaire, au niveau utilisateur et au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="955a4-110">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="955a4-111">Si vous configurez des stratégies de niveau utilisateur, vous devez également assigner les stratégies utilisateur à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="955a4-111">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="955a4-112">Pour plus d’informations sur la création et la configuration de stratégies d’archivage, voir <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and External Communications in Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="955a4-112">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="955a4-113">Pour configurer les options d’archivage au niveau du site</span><span class="sxs-lookup"><span data-stu-id="955a4-113">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="955a4-114">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="955a4-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="955a4-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="955a4-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="955a4-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="955a4-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="955a4-117">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="955a4-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="955a4-118">Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.</span><span class="sxs-lookup"><span data-stu-id="955a4-118">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="955a4-119">Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="955a4-119">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="955a4-120">Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="955a4-120">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="955a4-121">Afin d’activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.</span><span class="sxs-lookup"><span data-stu-id="955a4-121">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="955a4-122">Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée / conférence Web**.</span><span class="sxs-lookup"><span data-stu-id="955a4-122">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="955a4-123">Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="955a4-123">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="955a4-124">Dans **Créer un paramètre d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="955a4-124">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="955a4-125">Pour bloquer toute activité quand l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="955a4-125">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="955a4-126">Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="955a4-126">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="955a4-127">Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="955a4-127">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="955a4-128">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="955a4-128">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="955a4-129">Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="955a4-129">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="955a4-130">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="955a4-130">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

