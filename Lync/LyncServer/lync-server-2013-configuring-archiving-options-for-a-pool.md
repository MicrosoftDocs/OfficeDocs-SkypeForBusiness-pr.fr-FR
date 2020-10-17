---
title: 'Lync Server 2013 : configuration des options d’archivage pour un pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d658eb8a2ada7a7c797406faf5224f134eedc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502291"
---
# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="63fb0-102">Configuration des options d’archivage pour un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63fb0-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63fb0-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="63fb0-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="63fb0-p101">Vous pouvez spécifier des options d’archivage à appliquer à des pools spécifiques en créant et en configurant des options dans une configuration de l’archivage pour chacun de ces pools. La configuration d’un pool remplace la configuration globale et la configuration d’un site, mais uniquement pour le pool spécifié dans la configuration du pool.</span><span class="sxs-lookup"><span data-stu-id="63fb0-p101">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="63fb0-106">Pour plus d’informations sur le fonctionnement des configurations d’archivage, notamment la hiérarchie des configurations globale, de site et de pool, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="63fb0-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63fb0-107">Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="63fb0-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="63fb0-108">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="63fb0-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="63fb0-109">Pour configurer des options d’archivage au niveau du pool</span><span class="sxs-lookup"><span data-stu-id="63fb0-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="63fb0-110">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="63fb0-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="63fb0-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63fb0-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="63fb0-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, reportez-vous à la rubrique [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="63fb0-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63fb0-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="63fb0-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="63fb0-114">Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.</span><span class="sxs-lookup"><span data-stu-id="63fb0-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="63fb0-115">Dans **Sélectionner un service**, sélectionnez le pool à configurer pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="63fb0-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="63fb0-116">Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options d’archivage suivantes :</span><span class="sxs-lookup"><span data-stu-id="63fb0-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="63fb0-117">**Désactiver l’archivage**</span><span class="sxs-lookup"><span data-stu-id="63fb0-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="63fb0-118">**Archiver les sessions de messagerie instantanée**</span><span class="sxs-lookup"><span data-stu-id="63fb0-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="63fb0-119">**Archiver les sessions de messagerie instantanée et de conférence web**</span><span class="sxs-lookup"><span data-stu-id="63fb0-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="63fb0-120">Dans la page **Créer un paramètre d’archivage**, effectuez également l’opération suivante :</span><span class="sxs-lookup"><span data-stu-id="63fb0-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="63fb0-121">Pour bloquer toute activité lorsque l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="63fb0-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="63fb0-122">Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="63fb0-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="63fb0-123">Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="63fb0-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="63fb0-124">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="63fb0-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="63fb0-125">Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="63fb0-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="63fb0-126">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="63fb0-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

