---
title: Désactiver l’environnement hybride pour terminer la migration vers le Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des étapes détaillées sur la désactivation de l’environnement hybride dans le cadre de la consolidation du Cloud pour teams et Skype entreprise.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160520"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="39d3d-103">Désactiver l’environnement hybride pour terminer la migration vers le Cloud</span><span class="sxs-lookup"><span data-stu-id="39d3d-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="39d3d-104">Après avoir déplacé tous les utilisateurs de l’organisation locale vers le Cloud, vous pouvez mettre hors service le déploiement Skype entreprise sur site.</span><span class="sxs-lookup"><span data-stu-id="39d3d-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="39d3d-105">Outre la suppression d’un matériel, une étape essentielle consiste à séparer de manière logique ce déploiement sur site d’Office 365 en désactivant l’environnement hybride.</span><span class="sxs-lookup"><span data-stu-id="39d3d-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="39d3d-106">La désactivation de l’environnement hybride se compose de trois étapes:</span><span class="sxs-lookup"><span data-stu-id="39d3d-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="39d3d-107">Mettez à jour les enregistrements DNS pour qu’ils pointent vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="39d3d-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="39d3d-108">Désactivez le domaine fractionné dans le client Office 365.</span><span class="sxs-lookup"><span data-stu-id="39d3d-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="39d3d-109">Désactivez la fonctionnalité sur local pour communiquer avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="39d3d-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="39d3d-110">Ces étapes doivent être réalisées ensemble en tant qu’unité.</span><span class="sxs-lookup"><span data-stu-id="39d3d-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="39d3d-111">Vous trouverez ci-dessous des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="39d3d-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="39d3d-112">Dans de rares cas, il est possible que la Fédération avec d’autres organisations cesse de fonctionner avec le pointage local vers Office 365 pour votre organisation, jusqu’à ce que l’autre organisation ait mis à jour sa configuration de Fédération:</span><span class="sxs-lookup"><span data-stu-id="39d3d-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="39d3d-113">Toutes les organisations fédérées qui utilisent l’ancien modèle de Fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour leur organisation afin de supprimer le nom de domaine complet du proxy.</span><span class="sxs-lookup"><span data-stu-id="39d3d-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="39d3d-114">Ce modèle de Fédération hérité n’est pas basé sur les enregistrements DNS SRV, de sorte qu’une telle configuration est devenue obsolète une fois que votre organisation passe dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="39d3d-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="39d3d-115">Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed. online. Lync. <span>com doit mettre à jour sa configuration pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="39d3d-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="39d3d-116">Cette situation n’est possible que si l’organisation fédérée est purement locale et n’a jamais été fédérée avec un client hybride ou en ligne.</span><span class="sxs-lookup"><span data-stu-id="39d3d-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="39d3d-117">Dans ce cas, la Fédération avec ces organisations ne fonctionnera pas tant qu’elles n’auront pas activé leur fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="39d3d-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="39d3d-118">Si vous pensez qu’un de vos partenaires fédérés peut utiliser la Fédération directe ou avoir fédéré avec une organisation en ligne ou hybride, nous vous suggérons de lui envoyer une communication à ce sujet à mesure que vous vous préparez à effectuer votre migration vers le Cloud.</span><span class="sxs-lookup"><span data-stu-id="39d3d-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="39d3d-119">*Mettez à jour DNS pour qu’il pointe vers Office 365.*</span><span class="sxs-lookup"><span data-stu-id="39d3d-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="39d3d-120">Le DNS externe de l’Organisation pour l’organisation locale doit être mis à jour de manière à ce que les enregistrements Skype entreprise pointent vers Office 365 au lieu du déploiement local.</span><span class="sxs-lookup"><span data-stu-id="39d3d-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="39d3d-121">Notamment :</span><span class="sxs-lookup"><span data-stu-id="39d3d-121">Specifically:</span></span>

    |<span data-ttu-id="39d3d-122">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="39d3d-122">Record type</span></span>|<span data-ttu-id="39d3d-123">Nom</span><span class="sxs-lookup"><span data-stu-id="39d3d-123">Name</span></span>|<span data-ttu-id="39d3d-124">TTL (Durée de vie)</span><span class="sxs-lookup"><span data-stu-id="39d3d-124">TTL</span></span>|<span data-ttu-id="39d3d-125">Value (Valeur)</span><span class="sxs-lookup"><span data-stu-id="39d3d-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="39d3d-126">SRV</span><span class="sxs-lookup"><span data-stu-id="39d3d-126">SRV</span></span>|<span data-ttu-id="39d3d-127">_sipfederationtls. _ TCP</span><span class="sxs-lookup"><span data-stu-id="39d3d-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="39d3d-128">3600</span><span class="sxs-lookup"><span data-stu-id="39d3d-128">3600</span></span>|<span data-ttu-id="39d3d-129">100 1 5061 sipfed. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="39d3d-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="39d3d-130">SRV</span><span class="sxs-lookup"><span data-stu-id="39d3d-130">SRV</span></span>|<span data-ttu-id="39d3d-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="39d3d-131">_sip._tls</span></span>|<span data-ttu-id="39d3d-132">3600</span><span class="sxs-lookup"><span data-stu-id="39d3d-132">3600</span></span>|<span data-ttu-id="39d3d-133">100 1 443 sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="39d3d-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="39d3d-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="39d3d-134">CNAME</span></span>| <span data-ttu-id="39d3d-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="39d3d-135">lyncdiscover</span></span>|   <span data-ttu-id="39d3d-136">3600</span><span class="sxs-lookup"><span data-stu-id="39d3d-136">3600</span></span>|   <span data-ttu-id="39d3d-137">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="39d3d-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="39d3d-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="39d3d-138">CNAME</span></span>| <span data-ttu-id="39d3d-139">sip</span><span class="sxs-lookup"><span data-stu-id="39d3d-139">sip</span></span>|    <span data-ttu-id="39d3d-140">3600</span><span class="sxs-lookup"><span data-stu-id="39d3d-140">3600</span></span>|   <span data-ttu-id="39d3d-141">sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="39d3d-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="39d3d-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="39d3d-142">CNAME</span></span>| <span data-ttu-id="39d3d-143">satisfaction</span><span class="sxs-lookup"><span data-stu-id="39d3d-143">meet</span></span>|   <span data-ttu-id="39d3d-144">3600</span><span class="sxs-lookup"><span data-stu-id="39d3d-144">3600</span></span>|   <span data-ttu-id="39d3d-145">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="39d3d-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="39d3d-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="39d3d-146">CNAME</span></span>| <span data-ttu-id="39d3d-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="39d3d-147">dialin</span></span>  |<span data-ttu-id="39d3d-148">3600</span><span class="sxs-lookup"><span data-stu-id="39d3d-148">3600</span></span>|  <span data-ttu-id="39d3d-149">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="39d3d-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="39d3d-150">*Désactivez l’espace d’adressage SIP partagé dans le client Office 365.*</span><span class="sxs-lookup"><span data-stu-id="39d3d-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="39d3d-151">La commande ci-dessous doit être exécutée à partir d’une fenêtre PowerShell de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="39d3d-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="39d3d-152">*Désactivez la fonctionnalité sur local pour communiquer avec Office 365.*</span><span class="sxs-lookup"><span data-stu-id="39d3d-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="39d3d-153">La commande ci-dessous doit être exécutée à partir d’une fenêtre PowerShell locale.</span><span class="sxs-lookup"><span data-stu-id="39d3d-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="39d3d-154">Si vous avez déjà importé une session Skype entreprise Online, démarrez une nouvelle session Skype entreprise PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39d3d-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="39d3d-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39d3d-155">See also</span></span>

[<span data-ttu-id="39d3d-156">Consolidation du Cloud pour teams et Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="39d3d-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)