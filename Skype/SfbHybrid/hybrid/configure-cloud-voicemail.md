---
title: Configurer le service de messagerie vocale cloud pour les utilisateurs locaux
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions d’implémentation de la messagerie vocale en nuage pour les utilisateurs sur Skype Entreprise Server.
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118983"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="da271-103">Configurer le service de messagerie vocale cloud pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="da271-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="da271-104">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="da271-104">Overview</span></span> 
<span data-ttu-id="da271-105">Cet article explique comment configurer le service de messagerie vocale Microsoft Cloud pour vos utilisateurs locaux de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="da271-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="da271-106">Cet article suppose que Skype Entreprise Server est déjà déployé dans une topologie prise en charge et que vous avez satisfait aux conditions préalables à la configuration de la connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="da271-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="da271-107">Pour plus d’informations sur les avantages, les considérations relatives à la planification et les conditions requises pour l’implémentation de la messagerie vocale cloud, voir [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="da271-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="da271-108">La configuration de la messagerie vocale cloud implique les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="da271-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="da271-109">Assurez-vous que vous avez satisfait aux conditions préalables décrites dans planifier le [service de messagerie vocale cloud.](plan-cloud-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="da271-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="da271-110">Assurez-vous que vous avez configuré la connectivité hybride comme décrit dans [Planifier](plan-hybrid-connectivity.md) la connectivité hybride et [configurer la connectivité hybride.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="da271-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="da271-111">[Configurez la messagerie vocale cloud](#configure-cloud-voicemail-as-the-hosting-provider) en tant que fournisseur d’hébergement sur le serveur frontal, comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="da271-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="da271-112">[Configurez une stratégie de messagerie vocale hébergée](#configure-a-hosted-voicemail-policy) comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="da271-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="da271-113">[Affectez une stratégie de messagerie vocale hébergée](#assign-a-hosted-voicemail-policy) comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="da271-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="da271-114">[Activez un utilisateur pour la messagerie vocale cloud,](#enable-a-user-for-cloud-voicemail) comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="da271-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="da271-115">Configurer la messagerie vocale cloud en tant que fournisseur d’hébergement</span><span class="sxs-lookup"><span data-stu-id="da271-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="da271-116">Vous configurez la messagerie vocale cloud en tant que fournisseur d’hébergement sur un serveur frontal en utilisant la cmdlet New-CsHostingProvider avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="da271-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="da271-117">**Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez ; par exemple, messagerie vocale cloud.</span><span class="sxs-lookup"><span data-stu-id="da271-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="da271-118">**Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée.</span><span class="sxs-lookup"><span data-stu-id="da271-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="da271-119">Ce paramètre doit avoir la valeur True.</span><span class="sxs-lookup"><span data-stu-id="da271-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="da271-120">**EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="da271-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="da271-121">Ce paramètre doit avoir la valeur True.</span><span class="sxs-lookup"><span data-stu-id="da271-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="da271-122">**HostsOCSUsers indique** si le fournisseur d’hébergement est utilisé pour héberger des comptes Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="da271-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="da271-123">Ce paramètre doit avoir la valeur False.</span><span class="sxs-lookup"><span data-stu-id="da271-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="da271-124">**ProxyFQDN** spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement ; par exemple, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="da271-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="da271-125">Demandez cette information au fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="da271-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="da271-126">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="da271-126">This value cannot be modified.</span></span> <span data-ttu-id="da271-127">Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer, puis re-créer l’entrée pour ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="da271-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="da271-128">**IsLocal indique** si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="da271-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="da271-129">Ce paramètre doit avoir la valeur False.</span><span class="sxs-lookup"><span data-stu-id="da271-129">This parameter must be set to False.</span></span>

<span data-ttu-id="da271-130">Par exemple, dans Skype Entreprise Management Shell, l’cmdlet suivante configure la messagerie vocale cloud en tant que fournisseur d’hébergement :</span><span class="sxs-lookup"><span data-stu-id="da271-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="da271-131">Configurer une stratégie de messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="da271-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="da271-132">Pour vous assurer que la messagerie vocale de votre organisation est acheminée vers le service de messagerie vocale cloud, vous devez configurer une stratégie de messagerie vocale hébergée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="da271-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="da271-133">Dans de nombreux cas, une seule stratégie de messagerie vocale hébergée est requise et vous pouvez modifier la stratégie globale pour répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="da271-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="da271-134">Si votre organisation nécessite plusieurs stratégies de messagerie vocale hébergée, vous pouvez ajouter des stratégies à l’aide de la cmdlet new-cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="da271-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="da271-135">Pour modifier la stratégie globale, exécutez la commande suivante dans l’environnement de ligne de commande Skype Entreprise Server après avoir mis à jour votre Organisation et tenantID :</span><span class="sxs-lookup"><span data-stu-id="da271-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="da271-136">**La destination** spécifie le nom de domaine complet (FQDN) du service de messagerie vocale cloud hébergé.</span><span class="sxs-lookup"><span data-stu-id="da271-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="da271-137">Cette valeur doit être définie sur **exap.um.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="da271-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="da271-138">**L’organisation** est le domaine par défaut affecté à votre client.</span><span class="sxs-lookup"><span data-stu-id="da271-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="da271-139">Vous pouvez récupérer ces informations en ayant l’administrateur client se connecter à office.com, cliquer sur l’application Centre d’administration, accéder au programme d’installation sur la gauche, puis cliquer sur **Domaines**. </span><span class="sxs-lookup"><span data-stu-id="da271-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="da271-140">Par exemple : mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="da271-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="da271-141">Le nom de l’organisation est également le nom de domaine par défaut dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="da271-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="da271-142">Pour vous assurer qu’une stratégie de messagerie vocale hébergée a été correctement créée, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="da271-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="da271-143">Attribuer une stratégie de messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="da271-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="da271-144">Par défaut, la stratégie de messagerie vocale hébergée globale est affectée à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="da271-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="da271-145">Si vous utilisez une stratégie différente, avant d’activer les utilisateurs pour la messagerie vocale hébergée, vous devez d’abord accorder aux utilisateurs la stratégie de messagerie vocale hébergée souhaitée à l’aide de l’cmdlet [Grant-CSHostedVoicemailPolicy.](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="da271-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="da271-146">Par exemple, la commande suivante affecte une stratégie de messagerie vocale hébergée non globale à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="da271-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="da271-147">Activer un utilisateur pour la messagerie vocale cloud</span><span class="sxs-lookup"><span data-stu-id="da271-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="da271-148">Pour router les appels de messagerie vocale d’un utilisateur vers la messagerie vocale cloud, utilisez l’cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) avec le paramètre HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="da271-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="da271-149">Par exemple, la commande suivante active un compte d’utilisateur pour la messagerie vocale cloud :</span><span class="sxs-lookup"><span data-stu-id="da271-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="da271-150">La cmdlet vérifie qu’une stratégie de messagerie vocale cloud (au niveau global, du site ou de l’utilisateur) s’applique à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="da271-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="da271-151">Si aucune stratégie ne s’applique, la cmdlet échoue.</span><span class="sxs-lookup"><span data-stu-id="da271-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="da271-152">L’exemple suivant désactive un compte d’utilisateur pour la messagerie vocale cloud :</span><span class="sxs-lookup"><span data-stu-id="da271-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="da271-153">La cmdlet vérifie qu’aucune stratégie de messagerie vocale hébergée (au niveau global, du site ou de l’utilisateur) ne s’applique à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="da271-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="da271-154">Si une stratégie s’applique, la cmdlet échoue.</span><span class="sxs-lookup"><span data-stu-id="da271-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="da271-155">Les utilisateurs doivent être activés pour la voix entreprise pour utiliser le service de messagerie vocale Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="da271-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>