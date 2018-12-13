---
title: Désactiver hybride pour effectuer la migration vers le nuage
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des procédures détaillées permettant de désactiver hybride dans le cadre de la consolidation de cloud pour les équipes et Skype pour les entreprises.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247646"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="fed7a-103">Désactiver hybride pour effectuer la migration vers le nuage</span><span class="sxs-lookup"><span data-stu-id="fed7a-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="fed7a-104">Après avoir déplacé tous les utilisateurs sur site vers le nuage, vous pouvez retirer la Skype sur site pour le déploiement d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="fed7a-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="fed7a-105">Outre la suppression de n’importe quel matériel, une étape importante consiste à séparer logiquement ce déploiement sur site à partir d’Office 365 en désactivant hybride.</span><span class="sxs-lookup"><span data-stu-id="fed7a-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="fed7a-106">Désactivation hybride se compose des 3 étapes :</span><span class="sxs-lookup"><span data-stu-id="fed7a-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="fed7a-107">Mettre à jour les enregistrements DNS pour pointer vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="fed7a-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="fed7a-108">Désactiver le domaine fractionné dans le client Office 365.</span><span class="sxs-lookup"><span data-stu-id="fed7a-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="fed7a-109">Désactiver la possibilité de communiquer avec Office 365 dans sur prem.</span><span class="sxs-lookup"><span data-stu-id="fed7a-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="fed7a-110">Ces étapes doivent être effectuées ensemble en tant qu’unité.</span><span class="sxs-lookup"><span data-stu-id="fed7a-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="fed7a-111">Plus d’informations sont fournies ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="fed7a-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="fed7a-112">Rarement, modification DNS de pointage dans les locaux vers Office 365 pour votre organisation peut entraîner la fédération avec d’autres organisations arrêt avant que d’autres organisations mises à jour leur configuration de fédération :</span><span class="sxs-lookup"><span data-stu-id="fed7a-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="fed7a-113">Les organisations fédérées qui utilisent l’ancien modèle de fédération directe (également appelé serveur partenaire autorisé) vous devrez mettre à jour les entrées de domaines autorisés pour leur organisation permet de supprimer le nom de domaine complet du proxy.</span><span class="sxs-lookup"><span data-stu-id="fed7a-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="fed7a-114">Ce modèle de fédération héritée n’est pas basé sur les enregistrements SRV DNS, afin que cette configuration système plus à jour une fois que votre organisation se déplace vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="fed7a-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="fed7a-115">Toute organisation fédérée qui ne dispose pas d’un fournisseur d’hébergement activé pour sipfed.online.lync. <span>com vous devrez mettre à jour leur configuration afin d’activer qui.</span><span class="sxs-lookup"><span data-stu-id="fed7a-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="fed7a-116">Cela est possible uniquement si l’organisation fédérée est purement localement et n’a jamais fédérée avec n’importe quel hybride ou le locataire en ligne.</span><span class="sxs-lookup"><span data-stu-id="fed7a-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="fed7a-117">Dans ce cas, la fédération avec ces organisations ne fonctionnera pas jusqu'à ce qu’ils permettent à leur fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="fed7a-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="fed7a-118">Si vous pensez qu’un de vos partenaires fédérés peuvent utiliser la fédération directe ont fédéré avec n’importe quel en ligne ou organisation hybride, nous vous recommandons de que les envoyer une communication sur ce que vous vous préparez à terminer votre migration vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="fed7a-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="fed7a-119">*Mettre à jour DNS pour pointer vers Office 365.*</span><span class="sxs-lookup"><span data-stu-id="fed7a-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="fed7a-120">DNS externe de l’organisation de l’organisation locale doit être mis à jour afin que Skype pour les enregistrements d’entreprise pointent vers Office 365 au lieu du déploiement local.</span><span class="sxs-lookup"><span data-stu-id="fed7a-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="fed7a-121">Plus particulièrement :</span><span class="sxs-lookup"><span data-stu-id="fed7a-121">Specifically:</span></span>

    |<span data-ttu-id="fed7a-122">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="fed7a-122">Record type</span></span>|<span data-ttu-id="fed7a-123">Nom</span><span class="sxs-lookup"><span data-stu-id="fed7a-123">Name</span></span>|<span data-ttu-id="fed7a-124">DURÉE DE VIE</span><span class="sxs-lookup"><span data-stu-id="fed7a-124">TTL</span></span>|<span data-ttu-id="fed7a-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="fed7a-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="fed7a-126">SRV</span><span class="sxs-lookup"><span data-stu-id="fed7a-126">SRV</span></span>|<span data-ttu-id="fed7a-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="fed7a-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="fed7a-128">3600</span><span class="sxs-lookup"><span data-stu-id="fed7a-128">3600</span></span>|<span data-ttu-id="fed7a-129">100 1 5061 sipfed.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="fed7a-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="fed7a-130">SRV</span><span class="sxs-lookup"><span data-stu-id="fed7a-130">SRV</span></span>|<span data-ttu-id="fed7a-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="fed7a-131">_sip._tls</span></span>|<span data-ttu-id="fed7a-132">3600</span><span class="sxs-lookup"><span data-stu-id="fed7a-132">3600</span></span>|<span data-ttu-id="fed7a-133">100 1 443 sipdir.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="fed7a-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="fed7a-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="fed7a-134">CNAME</span></span>| <span data-ttu-id="fed7a-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="fed7a-135">lyncdiscover</span></span>|   <span data-ttu-id="fed7a-136">3600</span><span class="sxs-lookup"><span data-stu-id="fed7a-136">3600</span></span>|   <span data-ttu-id="fed7a-137">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="fed7a-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="fed7a-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="fed7a-138">CNAME</span></span>| <span data-ttu-id="fed7a-139">SIP</span><span class="sxs-lookup"><span data-stu-id="fed7a-139">sip</span></span>|    <span data-ttu-id="fed7a-140">3600</span><span class="sxs-lookup"><span data-stu-id="fed7a-140">3600</span></span>|   <span data-ttu-id="fed7a-141">sipdir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="fed7a-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="fed7a-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="fed7a-142">CNAME</span></span>| <span data-ttu-id="fed7a-143">répondre à</span><span class="sxs-lookup"><span data-stu-id="fed7a-143">meet</span></span>|   <span data-ttu-id="fed7a-144">3600</span><span class="sxs-lookup"><span data-stu-id="fed7a-144">3600</span></span>|   <span data-ttu-id="fed7a-145">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="fed7a-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="fed7a-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="fed7a-146">CNAME</span></span>| <span data-ttu-id="fed7a-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="fed7a-147">dialin</span></span>  |<span data-ttu-id="fed7a-148">3600</span><span class="sxs-lookup"><span data-stu-id="fed7a-148">3600</span></span>|  <span data-ttu-id="fed7a-149">WebDir.Online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="fed7a-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="fed7a-150">*Désactiver l’espace d’adressage SIP partagé dans le client Office 365.*</span><span class="sxs-lookup"><span data-stu-id="fed7a-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="fed7a-151">La commande suivante doit être effectuée à partir d’un Skype pour fenêtre Business Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fed7a-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="fed7a-152">*Désactiver la possibilité de communiquer avec Office 365 dans sur prem.*</span><span class="sxs-lookup"><span data-stu-id="fed7a-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="fed7a-153">La commande suivante doit être effectuée à partir d’une fenêtre de PowerShell locale.</span><span class="sxs-lookup"><span data-stu-id="fed7a-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="fed7a-154">Si vous avez précédemment importé un Skype pour la session Business en ligne, démarrez un nouveau Skype pour la session PowerShell Business.</span><span class="sxs-lookup"><span data-stu-id="fed7a-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="fed7a-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fed7a-155">See also</span></span>

[<span data-ttu-id="fed7a-156">Consolidation de cloud pour les équipes et Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="fed7a-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)