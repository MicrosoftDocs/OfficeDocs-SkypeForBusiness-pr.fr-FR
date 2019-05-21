---
title: Activation et désactivation de la contournement du contenu multimédia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Suivez les procédures décrites dans cet article pour activer ou désactiver la contournement du contenu multimédia à l’aide du panneau de configuration Skype entreprise Server.
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279584"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="34cc6-103">Activation et désactivation du contournement de média dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="34cc6-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="34cc6-104">Suivez les procédures décrites dans cet article pour activer ou désactiver la contournement du contenu multimédia à l’aide du panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34cc6-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="34cc6-105">Activer la dérivation de média réseau</span><span class="sxs-lookup"><span data-stu-id="34cc6-105">Enable network media bypass</span></span> 

<span data-ttu-id="34cc6-106">Les paramètres de contournement de média s’appliquent à un déploiement global de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34cc6-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="34cc6-107">Bypass Media accepte les appels pour ignorer le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="34cc6-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="34cc6-108">Pour plus d’informations sur l’utilisation du contournement du contenu multimédia, voir [planifier la dérivation de médias](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="34cc6-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="34cc6-109">Vous pouvez activer et configurer le contournement multimédia dans le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34cc6-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="34cc6-110">Pour activer et configurer le contournement multimédia</span><span class="sxs-lookup"><span data-stu-id="34cc6-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="34cc6-111">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="34cc6-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="34cc6-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34cc6-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="34cc6-113">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="34cc6-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="34cc6-114">Dans la page **Global** , cliquez sur configuration **globale** .</span><span class="sxs-lookup"><span data-stu-id="34cc6-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="34cc6-115">Il n’y a toujours qu’une seule configuration et elle est toujours nommée global.</span><span class="sxs-lookup"><span data-stu-id="34cc6-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="34cc6-116">Dans le menu **édition** , cliquez sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="34cc6-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="34cc6-117">Dans la page **modifier le paramètre global** , activez la case à cocher **activer le contournement du contenu multimédia** .</span><span class="sxs-lookup"><span data-stu-id="34cc6-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="34cc6-118">Sélectionnez l’une des options suivantes:</span><span class="sxs-lookup"><span data-stu-id="34cc6-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="34cc6-119">**Toujours ignorer**   sélectionnez cette option pour essayer la dérivation multimédia sur tous les appels.</span><span class="sxs-lookup"><span data-stu-id="34cc6-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="34cc6-120">Cette option n’est pas disponible si le contrôle d’admission des appels (CAC) est activé.</span><span class="sxs-lookup"><span data-stu-id="34cc6-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="34cc6-121">Si le CAC n’est pas activé, sélectionnez cette option dans les situations suivantes:</span><span class="sxs-lookup"><span data-stu-id="34cc6-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="34cc6-122">Le contrôle de la bande passante n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="34cc6-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="34cc6-123">Il n’est pas nécessaire de disposer d’une configuration précise pour déterminer le moment où un contournement se produit.</span><span class="sxs-lookup"><span data-stu-id="34cc6-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="34cc6-124">Il existe une connectivité complète entre les passerelles et les clients.</span><span class="sxs-lookup"><span data-stu-id="34cc6-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="34cc6-125">**Utiliser la configuration**   des sites et des régions si le CAC est activé, cette option est activée par défaut et ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="34cc6-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="34cc6-126">Lorsque cette option est sélectionnée, les sites et les régions de configuration réseau sont utilisés pour déterminer à quel moment une dérivation de média est possible.</span><span class="sxs-lookup"><span data-stu-id="34cc6-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="34cc6-127">Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement pour les sites qui ne sont pas mappés.</span><span class="sxs-lookup"><span data-stu-id="34cc6-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="34cc6-128">Activez la case à cocher **activer le contournement pour les sites non mappés** uniquement si vous avez un ou plusieurs sites de grande taille associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central de grande taille) et si des sites de succursales sont également associés au même région qui comporte des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="34cc6-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="34cc6-129">Lorsque vous activez le contournement pour les sites non mappés, la configuration est simplifiée, car vous spécifiez uniquement les sous-réseaux associés aux sites de succursale plutôt que d’indiquer tous les sous-réseaux associés à tous les sites.</span><span class="sxs-lookup"><span data-stu-id="34cc6-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="34cc6-130">Nous vous recommandons de ne pas activer la case à cocher **activer le contournement pour les sites non mappés** si le CAC est activé.</span><span class="sxs-lookup"><span data-stu-id="34cc6-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="34cc6-131">Cliquez sur **valider** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="34cc6-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="34cc6-132">Désactiver le contournement de média réseau</span><span class="sxs-lookup"><span data-stu-id="34cc6-132">Disable network media bypass</span></span>

<span data-ttu-id="34cc6-133">Les paramètres de contournement de média s’appliquent à un déploiement global de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34cc6-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="34cc6-134">Bypass Media accepte les appels pour ignorer le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="34cc6-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="34cc6-135">Pour plus d’informations sur l’utilisation du contournement du contenu multimédia, voir [planifier la dérivation de médias](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="34cc6-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="34cc6-136">Vous pouvez désactiver la dérivation multimédia du panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34cc6-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="34cc6-137">Pour désactiver la dérivation multimédia</span><span class="sxs-lookup"><span data-stu-id="34cc6-137">To disable media bypass</span></span>

1.  <span data-ttu-id="34cc6-138">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="34cc6-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="34cc6-139">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="34cc6-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="34cc6-140">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="34cc6-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="34cc6-141">Dans la page **Global** , cliquez sur configuration **globale** .</span><span class="sxs-lookup"><span data-stu-id="34cc6-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="34cc6-142">Il n’y a toujours qu’une seule configuration et elle est toujours nommée global.</span><span class="sxs-lookup"><span data-stu-id="34cc6-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="34cc6-143">Dans le menu **édition** , cliquez sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="34cc6-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="34cc6-144">Dans la page **modifier le paramètre global** , décochez la case **activer le contournement multimédia** .</span><span class="sxs-lookup"><span data-stu-id="34cc6-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="34cc6-145">Cliquez sur **valider** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="34cc6-145">Click **Commit** to save your changes.</span></span>

  
