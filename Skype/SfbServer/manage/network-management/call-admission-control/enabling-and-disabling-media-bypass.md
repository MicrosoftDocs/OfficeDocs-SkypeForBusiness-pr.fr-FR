---
title: Activation et désactivation du contournement de média
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Utilisez les procédures de cet article pour activer ou désactiver le contournement de média à l’aide du Panneau de contrôle Skype Entreprise Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816494"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="856b2-103">Activation et désactivation du contournement de média dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="856b2-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="856b2-104">Utilisez les procédures de cet article pour activer ou désactiver le contournement de média à l’aide du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="856b2-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="856b2-105">Activer le contournement de média réseau</span><span class="sxs-lookup"><span data-stu-id="856b2-105">Enable network media bypass</span></span> 

<span data-ttu-id="856b2-106">Les paramètres de déviation du média s’appliquent globalement dans un déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="856b2-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="856b2-107">La déviation du média permet aux appels de contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="856b2-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="856b2-108">Pour plus d’informations sur l’utilisation du contournement de média, voir [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="856b2-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="856b2-109">Vous pouvez activer et configurer le contournement de média à partir du Panneau de configuration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="856b2-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="856b2-110">Pour activer et configurer le contournement de média</span><span class="sxs-lookup"><span data-stu-id="856b2-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="856b2-111">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="856b2-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="856b2-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="856b2-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="856b2-113">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="856b2-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="856b2-p102">Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.</span><span class="sxs-lookup"><span data-stu-id="856b2-p102">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="856b2-116">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="856b2-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="856b2-117">Dans la page **Modifier les paramètres globaux,** activez la case à cocher Activer le **contournement de** média.</span><span class="sxs-lookup"><span data-stu-id="856b2-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="856b2-118">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="856b2-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="856b2-119">**Toujours ignorer**   Sélectionnez cette option pour tenter le contournement de média sur tous les appels.</span><span class="sxs-lookup"><span data-stu-id="856b2-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="856b2-120">Cette option n’est pas disponible si le contrôle d’admission des appels est activé.</span><span class="sxs-lookup"><span data-stu-id="856b2-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="856b2-121">Si cac n’est pas activé, sélectionnez cette option dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="856b2-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="856b2-122">Il n’est pas nécessaire de contrôler la bande passante.</span><span class="sxs-lookup"><span data-stu-id="856b2-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="856b2-123">La configuration fine n’est pas nécessaire pour déterminer quand le contournement doit se produire.</span><span class="sxs-lookup"><span data-stu-id="856b2-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="856b2-124">Il existe une connectivité complète entre les passerelles et les clients.</span><span class="sxs-lookup"><span data-stu-id="856b2-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="856b2-125">**Utiliser la configuration des sites et des régions**   Si le cac est activé, cette option est sélectionnée par défaut et ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="856b2-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="856b2-126">Lorsque cette option est sélectionnée, les sites et régions de configuration réseau sont utilisés pour déterminer quand le contournement de média est possible.</span><span class="sxs-lookup"><span data-stu-id="856b2-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="856b2-127">Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement pour les sites qui ne sont pas mappés.</span><span class="sxs-lookup"><span data-stu-id="856b2-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="856b2-128">Cliquez sur la case à cocher Activer le contournement pour les **sites non** mappés uniquement si vous avez un ou plusieurs sites de grande taille associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central de grande taille) et si certains sites de succursale associés à la même région ont des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="856b2-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="856b2-129">Lorsque vous activez le contournement pour les sites non mappés, la configuration est simplifiée, car vous spécifiez uniquement les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites.</span><span class="sxs-lookup"><span data-stu-id="856b2-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="856b2-130">Nous vous recommandons de ne pas activer la case à cocher Activer le contournement pour les **sites non** mappés si le contrôle d’enregistrement des contrôles d’enregistrement est activé.</span><span class="sxs-lookup"><span data-stu-id="856b2-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="856b2-131">Cliquez sur **OK** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="856b2-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="856b2-132">Désactiver le contournement de média réseau</span><span class="sxs-lookup"><span data-stu-id="856b2-132">Disable network media bypass</span></span>

<span data-ttu-id="856b2-133">Les paramètres de déviation du média s’appliquent globalement dans un déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="856b2-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="856b2-134">La déviation du média permet aux appels de contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="856b2-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="856b2-135">Pour plus d’informations sur l’utilisation du contournement de média, voir [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="856b2-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="856b2-136">Vous pouvez désactiver le contournement de média à partir du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="856b2-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="856b2-137">Pour désactiver le contournement de média</span><span class="sxs-lookup"><span data-stu-id="856b2-137">To disable media bypass</span></span>

1.  <span data-ttu-id="856b2-138">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="856b2-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="856b2-139">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="856b2-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="856b2-140">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="856b2-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="856b2-p106">Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.</span><span class="sxs-lookup"><span data-stu-id="856b2-p106">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="856b2-143">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="856b2-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="856b2-144">Dans la page **Modifier la configuration globale**, décochez la case **Activer le contournement de média**.</span><span class="sxs-lookup"><span data-stu-id="856b2-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="856b2-145">Cliquez sur **OK** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="856b2-145">Click **Commit** to save your changes.</span></span>

  
