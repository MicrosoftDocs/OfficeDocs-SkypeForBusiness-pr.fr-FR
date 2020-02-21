---
title: 'Lync Server 2013 : configuration des options d’archivage pour un site'
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
ms.openlocfilehash: 818018a742a12a98b019375d9991393b1ddea37f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="52699-102">Configuration des options d’archivage pour un site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52699-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52699-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="52699-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="52699-p101">Vous pouvez spécifier l’application d’options d’archivage à des sites spécifiques en créant et en configurant les options appropriées dans une configuration d’archivage pour chacun de ces sites. La configuration d’un site remplace la configuration globale, mais uniquement pour le site spécifié dans la configuration du site.</span><span class="sxs-lookup"><span data-stu-id="52699-p101">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites. A site configuration overrides the global configuration, but only for the site specified in the site configuration. Pool configurations override site configurations</span></span>

<span data-ttu-id="52699-107">Pour plus d’informations sur le fonctionnement des configurations d’archivage, notamment la hiérarchie des configurations globale, de site et de pool, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="52699-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52699-108">Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="52699-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52699-109">Pour activer l’archivage, vous devez spécifier les stratégies d’archivage qui contrôlent l’archivage des communications internes et externes au niveau global et, si nécessaire, au niveau utilisateur et au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="52699-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="52699-110">Si vous configurez des stratégies de niveau utilisateur, vous devez également assigner les stratégies utilisateur à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="52699-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="52699-111">Pour plus d’informations sur la création et la configuration de stratégies d’archivage, voir <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and External Communications in Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="52699-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="52699-112">Pour configurer les options d’archivage au niveau du site</span><span class="sxs-lookup"><span data-stu-id="52699-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="52699-113">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="52699-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="52699-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52699-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="52699-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="52699-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="52699-116">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="52699-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="52699-117">Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.</span><span class="sxs-lookup"><span data-stu-id="52699-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="52699-118">Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="52699-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="52699-119">Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="52699-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="52699-120">Afin d’activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.</span><span class="sxs-lookup"><span data-stu-id="52699-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="52699-121">Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée / conférence Web**.</span><span class="sxs-lookup"><span data-stu-id="52699-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="52699-122">Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="52699-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="52699-123">Dans **Créer un paramètre d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="52699-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="52699-124">Pour bloquer toute activité quand l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="52699-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="52699-125">Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="52699-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="52699-126">Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="52699-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="52699-127">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="52699-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="52699-128">Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="52699-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="52699-129">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="52699-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

