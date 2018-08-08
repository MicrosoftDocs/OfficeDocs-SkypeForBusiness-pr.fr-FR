---
title: Publier des modifications en attente de la configuration de routage voix dans Skype pour les entreprises
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Résumé : Apprenez à vérifier, publier ou annuler les modifications de configuration routage des communications vocales dans Skype pour Business Server à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: 8df40de8861c16b2ab3dc40bb9f3fadec95a4842
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006512"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="0eb07-103">Publier des modifications en attente de la configuration de routage voix dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="0eb07-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="0eb07-104">**Résumé :** Découvrez comment passez en revue, publier ou annuler les modifications de configuration routage des communications vocales dans Skype pour Business Server à l’aide de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="0eb07-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="0eb07-105">Après avoir modifié les paramètres de configuration dans les pages du groupe **Routage des communications vocales**, effectuez cette procédure pour consulter, publier ou annuler les modifications en attente.</span><span class="sxs-lookup"><span data-stu-id="0eb07-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0eb07-106">Vérifiez qu’un seul utilisateur à la fois modifie les paramètres de configuration du routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="0eb07-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0eb07-p101">Toutes les modifications en attente doivent être publiées en même temps en exécutant la commande **Tout valider**. Vous ne pouvez pas sélectionner les modifications en attente que vous voulez publier. Avant de publier les modifications en attente, exécutez la commande **Vérifier les modifications non validées** et annulez les modifications de configuration que vous ne voulez pas publier.</span><span class="sxs-lookup"><span data-stu-id="0eb07-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0eb07-110">Si vous quittez les pages du groupe **Routage des communications vocales** avant d’avoir validé les modifications en attente, toutes les modifications en attente seront perdues.</span><span class="sxs-lookup"><span data-stu-id="0eb07-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="0eb07-111">Cependant, vous pouvez exporter la configuration active (y compris les modifications en attente) vers un fichier de configuration des communications vocales, puis importer et publier la configuration mise à jour.</span><span class="sxs-lookup"><span data-stu-id="0eb07-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="0eb07-112">Pour plus d’informations, voir [exporter ou importer une configuration de routage voix fichier Skype pour les entreprises](voice-route-configuration-import-export.md).</span><span class="sxs-lookup"><span data-stu-id="0eb07-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="0eb07-113">Pour consulter, publier ou annuler les modifications de la configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="0eb07-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="0eb07-114">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0eb07-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="0eb07-115">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="0eb07-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0eb07-116">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="0eb07-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="0eb07-117">Effectuez les modifications souhaitées au niveau de la configuration dans chacune des pages du groupe **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="0eb07-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="0eb07-118">Pour consulter les modifications en attente sans les publier, sélectionnez **Vérifier les modifications non validées** dans le menu **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0eb07-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="0eb07-119">Si vous souhaitez annuler l’une des modifications en attente, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0eb07-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="0eb07-120">Sélectionnez **Annuler toutes les modifications non validées** dans le menu **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0eb07-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="0eb07-121">Accédez à l’onglet de la page **Routage des communications vocales** qui contient les modifications en attente que vous souhaitez annuler, cliquez sur **Valider**, puis sur **Annuler les modifications sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="0eb07-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="0eb07-122">Une fois que vous avez vérifié toutes les modifications en attente et annulé celles que vous ne souhaitez pas publier, cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="0eb07-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="0eb07-123">Dans la boîte de dialogue **Paramètres de configuration de la voix non validés** qui contient la liste de toutes les modifications en attente, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0eb07-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="0eb07-124">Skype pour le panneau de configuration serveur Business a validé les modifications, le message **publié avec succès la configuration de routage voix** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="0eb07-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

