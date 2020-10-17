---
title: 'Lync Server 2013 : activation de la déviation du trafic multimédia réseau'
description: 'Lync Server 2013 : activation de la déviation du trafic multimédia réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1218376903aa42e1ea55205e3a9e8d16aade9a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546550"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="ca4ef-103">Activation de la déviation du trafic multimédia réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca4ef-103">Enabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca4ef-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ca4ef-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ca4ef-105">Les paramètres de contournement de média s’appliquent globalement à un déploiement de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-105">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="ca4ef-106">La déviation du trafic multimédia autorise les appels à contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-106">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="ca4ef-107">Pour plus d’informations sur l’utilisation de la déviation du trafic multimédia, reportez-vous à la rubrique [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la section Planning.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-107">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="ca4ef-108">Vous pouvez activer et configurer le contournement de média à partir du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-108">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="ca4ef-109">Pour activer et configurer la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="ca4ef-109">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="ca4ef-110">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ca4ef-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ca4ef-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca4ef-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ca4ef-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Globale**.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-113">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="ca4ef-p103">Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="ca4ef-116">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="ca4ef-117">Sur la page **modifier les paramètres globaux** , activez la case à cocher **activer le contournement de média** .</span><span class="sxs-lookup"><span data-stu-id="ca4ef-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="ca4ef-118">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca4ef-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="ca4ef-119">**Toujours ignorer**     Sélectionnez cette option pour essayer la déviation du trafic multimédia sur tous les appels.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="ca4ef-120">Cette option n’est pas disponible si le contrôle d’admission des appels (CAC) est activé.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="ca4ef-121">Si CAC n’est pas activé, sélectionnez cette option dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca4ef-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="ca4ef-122">Il n’est pas nécessaire de contrôler la bande passante.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="ca4ef-123">Il n’est pas nécessaire d’utiliser une configuration affinée pour déterminer à quel moment la déviation doit se produire.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="ca4ef-124">Il existe une connectivité complète entre les passerelles et les clients.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="ca4ef-125">**Utiliser la configuration**     des sites et des régions Si le contrôle d’admission des accès est activé, cette option est sélectionnée par défaut et ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="ca4ef-126">Lorsque cette option est sélectionnée, les sites de configuration réseau et les régions seront utilisés pour déterminer quand la déviation du trafic multimédia est possible.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="ca4ef-127">Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement pour les sites qui ne sont pas mappés.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="ca4ef-128">Activez la case à cocher **activer le contournement pour les sites non mappés** uniquement si vous avez un ou plusieurs grands sites associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central important) et que vous disposez également de sites de succursale associés à la même région qui ont des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="ca4ef-129">Lorsque vous activez le contournement pour les sites non mappés, la configuration est rationalisée, car vous spécifiez uniquement les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="ca4ef-130">Nous vous recommandons de ne pas activer la case à cocher **activer le contournement pour les sites non mappés** si le contrôle d’admission des tâches est activé.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="ca4ef-131">Cliquez sur \*\*OK \*\* pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="ca4ef-131">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca4ef-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca4ef-132">See Also</span></span>


[<span data-ttu-id="ca4ef-133">Désactivation de la déviation du trafic multimédia réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca4ef-133">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="ca4ef-134">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca4ef-134">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="ca4ef-135">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca4ef-135">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

