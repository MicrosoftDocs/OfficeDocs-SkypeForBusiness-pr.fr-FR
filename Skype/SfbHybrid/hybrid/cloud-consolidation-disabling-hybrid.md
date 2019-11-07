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
ms.openlocfilehash: 7bd0b4c606a84dea08fb568d42fe403f624c522d
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010577"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="465f2-103">Désactiver l’environnement hybride pour terminer la migration vers le Cloud</span><span class="sxs-lookup"><span data-stu-id="465f2-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="465f2-104">Après avoir déplacé tous les utilisateurs de l’organisation locale vers le Cloud, vous pouvez mettre hors service le déploiement Skype entreprise sur site.</span><span class="sxs-lookup"><span data-stu-id="465f2-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="465f2-105">Outre la suppression d’un matériel, une étape essentielle consiste à séparer de manière logique ce déploiement sur site d’Office 365 en désactivant l’environnement hybride.</span><span class="sxs-lookup"><span data-stu-id="465f2-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="465f2-106">La désactivation de l’environnement hybride se compose de trois étapes :</span><span class="sxs-lookup"><span data-stu-id="465f2-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="465f2-107">Mettez à jour les enregistrements DNS pour qu’ils pointent vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="465f2-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="465f2-108">Désactivez le domaine fractionné dans le client Office 365.</span><span class="sxs-lookup"><span data-stu-id="465f2-108">Disable split domain in the Office 365 tenant.</span></span>

3. <span data-ttu-id="465f2-109">Désactivez la fonctionnalité en local pour communiquer avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="465f2-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="465f2-110">Ces étapes doivent être réalisées ensemble en tant qu’unité.</span><span class="sxs-lookup"><span data-stu-id="465f2-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="465f2-111">Vous trouverez ci-dessous des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="465f2-111">Details are provided below.</span></span> <span data-ttu-id="465f2-112">En outre, des recommandations sont fournies pour la gestion des numéros de téléphone des utilisateurs migrés une fois que le déploiement local est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="465f2-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="465f2-113">Dans de rares cas, il est possible que la Fédération avec d’autres organisations cesse de fonctionner avec le pointage local vers Office 365 pour votre organisation, jusqu’à ce que l’autre organisation ait mis à jour sa configuration de Fédération :</span><span class="sxs-lookup"><span data-stu-id="465f2-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="465f2-114">Toutes les organisations fédérées qui utilisent l’ancien modèle de Fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour leur organisation afin de supprimer le nom de domaine complet du proxy.</span><span class="sxs-lookup"><span data-stu-id="465f2-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="465f2-115">Ce modèle de Fédération hérité n’est pas basé sur les enregistrements DNS SRV, de sorte qu’une telle configuration est devenue obsolète une fois que votre organisation passe dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="465f2-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="465f2-116">Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed. online. Lync. <span>com doit mettre à jour sa configuration pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="465f2-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="465f2-117">Cette situation n’est possible que si l’organisation fédérée est purement locale et n’a jamais été fédérée avec un client hybride ou en ligne.</span><span class="sxs-lookup"><span data-stu-id="465f2-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="465f2-118">Dans ce cas, la Fédération avec ces organisations ne fonctionnera pas tant qu’elles n’auront pas activé leur fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="465f2-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="465f2-119">Si vous pensez qu’un de vos partenaires fédérés peut utiliser la Fédération directe ou avoir fédéré avec une organisation en ligne ou hybride, nous vous suggérons de lui envoyer une communication à ce sujet à mesure que vous vous préparez à effectuer votre migration vers le Cloud.</span><span class="sxs-lookup"><span data-stu-id="465f2-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="465f2-120">*Mettez à jour DNS pour qu’il pointe vers Office 365.*</span><span class="sxs-lookup"><span data-stu-id="465f2-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="465f2-121">Le DNS externe de l’Organisation pour l’organisation locale doit être mis à jour de manière à ce que les enregistrements Skype entreprise pointent vers Office 365 au lieu du déploiement local.</span><span class="sxs-lookup"><span data-stu-id="465f2-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="465f2-122">Notamment :</span><span class="sxs-lookup"><span data-stu-id="465f2-122">Specifically:</span></span>

    |<span data-ttu-id="465f2-123">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="465f2-123">Record type</span></span>|<span data-ttu-id="465f2-124">Nom</span><span class="sxs-lookup"><span data-stu-id="465f2-124">Name</span></span>|<span data-ttu-id="465f2-125">TTL (Durée de vie)</span><span class="sxs-lookup"><span data-stu-id="465f2-125">TTL</span></span>|<span data-ttu-id="465f2-126">Value (Valeur)</span><span class="sxs-lookup"><span data-stu-id="465f2-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="465f2-127">SRV</span><span class="sxs-lookup"><span data-stu-id="465f2-127">SRV</span></span>|<span data-ttu-id="465f2-128">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="465f2-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="465f2-129">3600</span><span class="sxs-lookup"><span data-stu-id="465f2-129">3600</span></span>|<span data-ttu-id="465f2-130">100 1 5061 sipfed. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="465f2-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="465f2-131">SRV</span><span class="sxs-lookup"><span data-stu-id="465f2-131">SRV</span></span>|<span data-ttu-id="465f2-132">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="465f2-132">_sip._tls</span></span>|<span data-ttu-id="465f2-133">3600</span><span class="sxs-lookup"><span data-stu-id="465f2-133">3600</span></span>|<span data-ttu-id="465f2-134">100 1 443 sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="465f2-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="465f2-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="465f2-135">CNAME</span></span>| <span data-ttu-id="465f2-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="465f2-136">lyncdiscover</span></span>|   <span data-ttu-id="465f2-137">3600</span><span class="sxs-lookup"><span data-stu-id="465f2-137">3600</span></span>|   <span data-ttu-id="465f2-138">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="465f2-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="465f2-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="465f2-139">CNAME</span></span>| <span data-ttu-id="465f2-140">sip</span><span class="sxs-lookup"><span data-stu-id="465f2-140">sip</span></span>|    <span data-ttu-id="465f2-141">3600</span><span class="sxs-lookup"><span data-stu-id="465f2-141">3600</span></span>|   <span data-ttu-id="465f2-142">sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="465f2-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="465f2-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="465f2-143">CNAME</span></span>| <span data-ttu-id="465f2-144">satisfaction</span><span class="sxs-lookup"><span data-stu-id="465f2-144">meet</span></span>|   <span data-ttu-id="465f2-145">3600</span><span class="sxs-lookup"><span data-stu-id="465f2-145">3600</span></span>|   <span data-ttu-id="465f2-146">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="465f2-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="465f2-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="465f2-147">CNAME</span></span>| <span data-ttu-id="465f2-148">Dialin</span><span class="sxs-lookup"><span data-stu-id="465f2-148">dialin</span></span>  |<span data-ttu-id="465f2-149">3600</span><span class="sxs-lookup"><span data-stu-id="465f2-149">3600</span></span>|  <span data-ttu-id="465f2-150">webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="465f2-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="465f2-151">*Désactivez l’espace d’adressage SIP partagé dans le client Office 365.*</span><span class="sxs-lookup"><span data-stu-id="465f2-151">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="465f2-152">La commande ci-dessous doit être exécutée à partir d’une fenêtre PowerShell de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="465f2-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="465f2-153">*Désactivez la fonctionnalité locale pour communiquer avec Office 365.*</span><span class="sxs-lookup"><span data-stu-id="465f2-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="465f2-154">La commande ci-dessous doit être exécutée à partir d’une fenêtre PowerShell locale :</span><span class="sxs-lookup"><span data-stu-id="465f2-154">The command below needs to be done from an on-premises PowerShell window:</span></span>
```
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="465f2-155">Gérer les numéros de téléphone pour les utilisateurs qui ont été migrés à partir de l’installation locale</span><span class="sxs-lookup"><span data-stu-id="465f2-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="465f2-156">Les administrateurs peuvent gérer les utilisateurs qui ont été précédemment déplacés d’un serveur Skype entreprise local vers le Cloud, même après la désactivation du déploiement local.</span><span class="sxs-lookup"><span data-stu-id="465f2-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="465f2-157">Il existe deux possibilités :</span><span class="sxs-lookup"><span data-stu-id="465f2-157">There are two different possibilities:</span></span>

- <span data-ttu-id="465f2-158">L’utilisateur n’a pas de valeur pour LineURI en local avant le déplacement.</span><span class="sxs-lookup"><span data-stu-id="465f2-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="465f2-159">Dans ce cas, vous pouvez modifier le LineURI à l’aide des paramètres-onpremLineUri de la [cmdlet Set-Csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) dans le module Skype entreprise Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="465f2-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="465f2-160">L’utilisateur avait une LineURI locale avant le déplacement (vraisemblablement parce que l’utilisateur a été activé pour voix entreprise).</span><span class="sxs-lookup"><span data-stu-id="465f2-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="465f2-161">Si vous souhaitez modifier le LineURI, vous devez le faire dans l’annuaire Active Directory local et laisser la valeur circuler dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="465f2-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="465f2-162">Il n’est pas nécessaire d’utiliser Skype entreprise Server sur site.</span><span class="sxs-lookup"><span data-stu-id="465f2-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="465f2-163">Au lieu de cela, cet attribut, msRTCSIP-Line, peut être modifié directement dans l’annuaire Active Directory local, à l’aide du composant logiciel enfichable MMC utilisateurs et ordinateurs Active Directory, ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="465f2-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="465f2-164">Si vous utilisez le composant logiciel enfichable MMC, ouvrez la page Propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs, puis recherchez msRTCSIP-Line.</span><span class="sxs-lookup"><span data-stu-id="465f2-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Outil utilisateurs et ordinateurs Active Directory](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="465f2-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="465f2-166">See also</span></span>

[<span data-ttu-id="465f2-167">Consolidation du Cloud pour teams et Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="465f2-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
