---
title: Configurer le service de messagerie vocale dans le nuage
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instructions relatives à la mise en œuvre la messagerie vocale en nuage pour les utilisateurs hébergement sur Skype pour Business Server.
ms.openlocfilehash: 05c486ed338e8e77ab68f12a64c3a59646a157d0
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531911"
---
# <a name="configure-cloud-voicemail-service"></a><span data-ttu-id="df38f-103">Configurer le service de messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="df38f-103">Configure Cloud Voicemail service</span></span>

## <a name="overview"></a><span data-ttu-id="df38f-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="df38f-104">Overview</span></span> 
<span data-ttu-id="df38f-105">Cet article explique comment configurer le service de messagerie vocale de Microsoft dans le nuage pour votre Skype pour les utilisateurs locaux professionnels.</span><span class="sxs-lookup"><span data-stu-id="df38f-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="df38f-106">Cet article suppose que vous avez déjà Skype pour Business Server déployé dans une topologie prise en charge, et que vous remplissez les conditions requises pour configurer la connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="df38f-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="df38f-107">Pour plus d’informations sur les avantages des considérations relatives à la planification et configuration requise pour l’implémentation de la messagerie vocale dans le nuage, voir [service de planification de la messagerie vocale dans le nuage](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="df38f-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="df38f-108">Configuration de la messagerie vocale dans le nuage implique les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="df38f-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="df38f-109">Vérifiez que vous remplissez les conditions préalables comme décrit dans le [service de planification de la messagerie vocale dans le nuage](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="df38f-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="df38f-110">Vérifiez que vous avez configuré une connectivité hybride comme décrit dans la [connectivité hybride de Plan](plan-hybrid-connectivity.md) et de [connectivité de configuration hybride](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="df38f-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="df38f-111">[Configurer la messagerie vocale dans le nuage en tant que le fournisseur d’hébergement sur le serveur Edge](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="df38f-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="df38f-112">[Configurer une stratégie de messagerie vocale hébergée](#configure-a-hosted-voicemail-policy) comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="df38f-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="df38f-113">[Attribuer une stratégie de messagerie vocale hébergée](#assign-a-hosted-voicemail-policy) comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="df38f-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="df38f-114">[Permettre à un utilisateur pour la messagerie vocale dans le nuage](#enable-a-user-for-cloud-voicemail) comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="df38f-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="df38f-115">Configurer la messagerie vocale dans le nuage en tant que le fournisseur d’hébergement sur le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="df38f-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="df38f-116">Vous configurez la messagerie vocale dans le nuage en tant que le fournisseur d’hébergement sur le serveur Edge à l’aide de l’applet de commande New-CsHostingProvider avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="df38f-116">You configure Cloud Voicemail as the hosting provider on the Edge Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="df38f-117">**Identité** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez ; par exemple, la messagerie vocale dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="df38f-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="df38f-118">\*\*Enabled \*\* indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée.</span><span class="sxs-lookup"><span data-stu-id="df38f-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="df38f-119">Ce paramètre doit être défini sur True.</span><span class="sxs-lookup"><span data-stu-id="df38f-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="df38f-120">**EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adresse SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="df38f-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="df38f-121">Ce paramètre doit être défini sur True.</span><span class="sxs-lookup"><span data-stu-id="df38f-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="df38f-122">**HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Skype pour les comptes Business Server.</span><span class="sxs-lookup"><span data-stu-id="df38f-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="df38f-123">Ce paramètre doit être défini sur False.</span><span class="sxs-lookup"><span data-stu-id="df38f-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="df38f-124">**ProxyFQDN** Spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement ; par exemple, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="df38f-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="df38f-125">Pour que ces informations, contactez votre fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="df38f-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="df38f-126">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="df38f-126">This value cannot be modified.</span></span> <span data-ttu-id="df38f-127">Si le fournisseur d’hébergement change de serveur proxy, vous devez supprimer et recréer l’entrée pour ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="df38f-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="df38f-128">**IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre Skype pour la topologie du serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="df38f-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="df38f-129">Ce paramètre doit être défini sur False.</span><span class="sxs-lookup"><span data-stu-id="df38f-129">This parameter must be set to False.</span></span>

<span data-ttu-id="df38f-130">Par exemple, dans Skype pour Business Management shell, l’applet de commande suivante permet de configurer de la messagerie vocale dans le nuage en tant que le fournisseur d’hébergement :</span><span class="sxs-lookup"><span data-stu-id="df38f-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="df38f-131">Configurer une stratégie de messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="df38f-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="df38f-132">Pour vous assurer que la messagerie vocale pour votre organisation est dirigé vers le service de messagerie vocale dans le nuage, vous devez configurer une stratégie de messagerie vocale hébergée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="df38f-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="df38f-133">Dans de nombreux cas, messagerie vocale hébergée qu’une seule stratégie est nécessaire, et vous pouvez modifier la stratégie globale pour répondre à tous vos besoins.</span><span class="sxs-lookup"><span data-stu-id="df38f-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="df38f-134">Si votre organisation a besoin de plusieurs stratégies de messagerie vocale hébergée, vous pouvez ajouter des stratégies à l’aide de l’applet de commande nouvelle-cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="df38f-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="df38f-135">Pour modifier la stratégie globale, exécutez la commande suivante dans le Skype pour Business Server shell de gestion après la mise à jour de votre organisation et l’ID client sur :</span><span class="sxs-lookup"><span data-stu-id="df38f-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="df38f-136">**Destination** Spécifie le nom de domaine complet (FQDN) du service de messagerie vocale dans le nuage hébergé.</span><span class="sxs-lookup"><span data-stu-id="df38f-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="df38f-137">Cette valeur doit être définie sur **exap.um.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="df38f-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="df38f-138">**Organisation** est le domaine par défaut affecté à votre client.</span><span class="sxs-lookup"><span data-stu-id="df38f-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="df38f-139">Vous pouvez récupérer ces informations grâce à l’administrateur du client de se connecter à office.com, cliquez sur l’application du centre d’administration, accédez à **installation** sur la gauche et cliquez sur **domaines**.</span><span class="sxs-lookup"><span data-stu-id="df38f-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="df38f-140">Par exemple : mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="df38f-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="df38f-141">Le nom de l’organisation est également le nom de domaine par défaut dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="df38f-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="df38f-142">**ID client sur** sert à identifier votre client dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="df38f-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="df38f-143">Pour plus d’informations, voir [Rechercher votre ID de client Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span><span class="sxs-lookup"><span data-stu-id="df38f-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="df38f-144">Pour vous assurer qu’une stratégie de messagerie vocale hébergée a été créée avec succès, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="df38f-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="df38f-145">Attribuer une stratégie de messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="df38f-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="df38f-146">Par défaut, Global hébergé stratégie de messagerie vocale est affectée à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="df38f-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="df38f-147">Si vous utilisez une stratégie différente, avant d’activer les utilisateurs pour la messagerie vocale hébergée, vous devez d’abord accorder aux utilisateurs la stratégie de messagerie vocale hébergée souhaité à l’aide de l’applet de commande [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="df38f-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="df38f-148">Par exemple, la commande suivante attribue une stratégie de messagerie vocale hébergée non globale à un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="df38f-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="df38f-149">Permettre à un utilisateur pour la messagerie vocale dans le nuage</span><span class="sxs-lookup"><span data-stu-id="df38f-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="df38f-150">Pour activer les appels de messagerie vocale d’un utilisateur à être acheminés vers la messagerie vocale dans le nuage, vous utilisez l’applet de commande [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) avec le paramètre HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="df38f-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="df38f-151">Par exemple, la commande suivante permet à un compte d’utilisateur pour la messagerie vocale dans le nuage :</span><span class="sxs-lookup"><span data-stu-id="df38f-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="df38f-152">L’applet de commande vérifie si une stratégie de messagerie vocale dans le nuage--au niveau global, site ou au niveau utilisateur--s’applique à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df38f-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="df38f-153">Si aucune stratégie s’applique, l’applet de commande échoue.</span><span class="sxs-lookup"><span data-stu-id="df38f-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="df38f-154">L’exemple suivant désactive un compte d’utilisateur pour la messagerie vocale dans le nuage :</span><span class="sxs-lookup"><span data-stu-id="df38f-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="df38f-155">L’applet de commande vérifie si aucune stratégie de messagerie vocale hébergée--au niveau global, site ou au niveau utilisateur--s’applique à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df38f-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="df38f-156">Si une stratégie s’applique, l’applet de commande échoue.</span><span class="sxs-lookup"><span data-stu-id="df38f-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="df38f-157">Les utilisateurs doivent être activé pour utiliser le Service de messagerie vocale du Cloud Microsoft de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="df38f-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>