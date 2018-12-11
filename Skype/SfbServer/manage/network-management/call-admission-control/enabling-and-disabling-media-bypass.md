---
title: Activation et désactivation du contournement de média
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Utilisez les procédures décrites dans cet article pour activer ou désactiver le contournement de média à l’aide de la Skype pour le panneau de configuration serveur Business.
ms.openlocfilehash: f595ab5380575f34c0a470cb58c82459841ee4d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222757"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="7f80e-103">Activation et désactivation des médias de contournement dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="7f80e-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="7f80e-104">Utilisez les procédures décrites dans cet article pour activer ou désactiver le contournement de média à l’aide de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="7f80e-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="7f80e-105">Activer le contournement de média réseau</span><span class="sxs-lookup"><span data-stu-id="7f80e-105">Enable network media bypass</span></span> 

<span data-ttu-id="7f80e-106">Paramètres de déviation du trafic multimédia s’appliquent globalement un Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7f80e-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="7f80e-107">Le contournement de média autorise les appels à ignorer le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="7f80e-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="7f80e-108">Pour plus d’informations sur l’utilisation de Media contournement de média, voir [Plan pour le média de contournement](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="7f80e-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="7f80e-109">Vous pouvez activer et configurer le contournement de média à partir de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="7f80e-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="7f80e-110">Pour activer et configurer le contournement de média</span><span class="sxs-lookup"><span data-stu-id="7f80e-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="7f80e-111">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="7f80e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7f80e-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="7f80e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7f80e-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="7f80e-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="7f80e-114">Dans la page **globale** , cliquez sur la configuration **globale** .</span><span class="sxs-lookup"><span data-stu-id="7f80e-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="7f80e-115">Il y a toujours qu’une seule configuration, et il est toujours nommé Global.</span><span class="sxs-lookup"><span data-stu-id="7f80e-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="7f80e-116">Dans le menu **Edition** , cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="7f80e-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="7f80e-117">Dans la page **Modifier la configuration globale** , cliquez sur la case à cocher **Activer le contournement de média** .</span><span class="sxs-lookup"><span data-stu-id="7f80e-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="7f80e-118">Sélectionnez une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f80e-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="7f80e-119">**Toujours contourner**   Sélectionnez cette option pour essayer de médias contournement de média sur tous les appels.</span><span class="sxs-lookup"><span data-stu-id="7f80e-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="7f80e-120">Cette option n’est pas disponible si le contrôle d’admission des appels (CAC) est activé.</span><span class="sxs-lookup"><span data-stu-id="7f80e-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="7f80e-121">Si CAC n’est pas activé, sélectionnez cette option dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f80e-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="7f80e-122">Il n’est pas nécessaire de contrôler la bande passante.</span><span class="sxs-lookup"><span data-stu-id="7f80e-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="7f80e-123">Il n’est pas nécessaire d’affiner la configuration déterminer si la déviation doit avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="7f80e-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="7f80e-124">Connectivité est complète entre passerelles et clients.</span><span class="sxs-lookup"><span data-stu-id="7f80e-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="7f80e-125">**Utiliser les sites et la configuration de la zone**   si CAC est activé, cette option est sélectionnée par défaut et ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="7f80e-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="7f80e-126">Lorsque cette option est sélectionnée, sites de configuration réseau et les régions seront utilisées pour déterminer quand le contournement de média est possible.</span><span class="sxs-lookup"><span data-stu-id="7f80e-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="7f80e-127">Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement de média pour les sites qui ne sont pas associés.</span><span class="sxs-lookup"><span data-stu-id="7f80e-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="7f80e-128">Cliquez sur la case à cocher **Activer le contournement de média pour les sites non mappés** uniquement si vous avez un ou plusieurs sites de grande taille associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central volumineux) et vous avez également certains sites de succursale associés à la zone qui ont des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="7f80e-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="7f80e-129">Lorsque vous activez le contournement de média pour les sites non mappés, configuration est simple puisque vous spécifiez uniquement les sous-réseaux associés avec les sites de succursale, plutôt que d’avoir à spécifier tous les sous-réseaux associés à tous les sites.</span><span class="sxs-lookup"><span data-stu-id="7f80e-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="7f80e-130">Il est recommandé que vous ne sélectionnez pas la case à cocher **Activer le contournement de média pour les sites non mappés** si CAC est activé.</span><span class="sxs-lookup"><span data-stu-id="7f80e-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="7f80e-131">Cliquez sur **Valider** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="7f80e-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="7f80e-132">Désactiver le contournement de média réseau</span><span class="sxs-lookup"><span data-stu-id="7f80e-132">Disable network media bypass</span></span>

<span data-ttu-id="7f80e-133">Paramètres de déviation du trafic multimédia s’appliquent globalement un Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7f80e-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="7f80e-134">Le contournement de média autorise les appels à ignorer le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="7f80e-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="7f80e-135">Pour plus d’informations sur l’utilisation de Media contournement de média, voir [Plan pour le média de contournement](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="7f80e-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="7f80e-136">Vous pouvez désactiver le contournement de média à partir de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="7f80e-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="7f80e-137">Pour désactiver le contournement de média</span><span class="sxs-lookup"><span data-stu-id="7f80e-137">To disable media bypass</span></span>

1.  <span data-ttu-id="7f80e-138">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="7f80e-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7f80e-139">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="7f80e-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7f80e-140">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="7f80e-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="7f80e-141">Dans la page **globale** , cliquez sur la configuration **globale** .</span><span class="sxs-lookup"><span data-stu-id="7f80e-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="7f80e-142">Il y a toujours qu’une seule configuration, et il est toujours nommé Global.</span><span class="sxs-lookup"><span data-stu-id="7f80e-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="7f80e-143">Dans le menu **Edition** , cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="7f80e-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="7f80e-144">Dans la page **Modifier la configuration globale** , désactivez la case à cocher **Activer le contournement de média** .</span><span class="sxs-lookup"><span data-stu-id="7f80e-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="7f80e-145">Cliquez sur **Valider** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="7f80e-145">Click **Commit** to save your changes.</span></span>

  