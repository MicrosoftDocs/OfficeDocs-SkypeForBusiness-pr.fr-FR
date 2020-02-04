---
title: 'Lync Server 2013 : publier les modifications en attente apportées à la configuration de l’acheminement vocal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="24cf6-102">Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24cf6-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24cf6-103">_**Dernière modification de la rubrique :** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="24cf6-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="24cf6-104">Après avoir modifié les paramètres de configuration dans les pages du groupe **Routage des communications vocales**, effectuez cette procédure pour consulter, publier ou annuler les modifications en attente.</span><span class="sxs-lookup"><span data-stu-id="24cf6-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24cf6-105">Vérifiez qu’un seul utilisateur à la fois modifie les paramètres de configuration du routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="24cf6-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="24cf6-p101">Toutes les modifications en attente doivent être publiées en même temps en exécutant la commande <STRONG>Tout valider</STRONG>. Vous ne pouvez pas sélectionner les modifications en attente que vous voulez publier. Avant de publier les modifications en attente, exécutez la commande <STRONG>Vérifier les modifications non validées</STRONG> et annulez les modifications de configuration que vous ne voulez pas publier.</span><span class="sxs-lookup"><span data-stu-id="24cf6-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="24cf6-109">Si vous quittez les pages du groupe <STRONG>Routage des communications vocales</STRONG> avant d’avoir validé les modifications en attente, toutes les modifications en attente seront perdues.</span><span class="sxs-lookup"><span data-stu-id="24cf6-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="24cf6-110">Cependant, vous pouvez exporter la configuration active (y compris les modifications en attente) vers un fichier de configuration des communications vocales, puis importer et publier la configuration mise à jour.</span><span class="sxs-lookup"><span data-stu-id="24cf6-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="24cf6-111">Pour plus d’informations, voir <A href="lync-server-2013-export-a-voice-route-configuration-file.md">exporter un fichier de configuration de l’itinéraire vocal dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="24cf6-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="24cf6-112">Pour consulter, publier ou annuler les modifications de la configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="24cf6-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="24cf6-113">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="24cf6-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="24cf6-114">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="24cf6-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="24cf6-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24cf6-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24cf6-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="24cf6-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24cf6-117">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="24cf6-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="24cf6-118">Effectuez les modifications souhaitées au niveau de la configuration dans chacune des pages du groupe **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="24cf6-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="24cf6-119">Pour consulter les modifications en attente sans les publier, sélectionnez **Vérifier les modifications non validées** dans le menu **Valider**.</span><span class="sxs-lookup"><span data-stu-id="24cf6-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="24cf6-120">Si vous souhaitez annuler l’une des modifications en attente, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="24cf6-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="24cf6-121">Sélectionnez **Annuler toutes les modifications non validées** dans le menu **Valider**.</span><span class="sxs-lookup"><span data-stu-id="24cf6-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="24cf6-122">Accédez à l’onglet de la page **Routage des communications vocales** qui contient les modifications en attente que vous souhaitez annuler, cliquez sur **Valider**, puis sur **Annuler les modifications sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="24cf6-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="24cf6-123">Une fois que vous avez vérifié toutes les modifications en attente et annulé celles que vous ne souhaitez pas publier, cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="24cf6-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="24cf6-124">Dans la boîte de dialogue **Paramètres de configuration de la voix non validés** qui contient la liste de toutes les modifications en attente, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="24cf6-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="24cf6-125">Lorsque le panneau de configuration de Lync Server a validé les modifications, le message **configuration de routage vocale correctement publié** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="24cf6-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

