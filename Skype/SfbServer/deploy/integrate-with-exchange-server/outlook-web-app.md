---
title: Configurer l’intégration entre Skype entreprise Server local et Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Résumé : intégrez Skype entreprise Server et Outlook Web App.'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221184"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="ea64c-103">Configurer l’intégration entre Skype entreprise Server local et Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="ea64c-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="ea64c-104">**Résumé :** Intégrez Skype entreprise Server et Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ea64c-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="ea64c-105">Les clients qui utilisent des déploiements Skype entreprise Server sur site peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="ea64c-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="ea64c-106">Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique et l’intégration de la messagerie instantanée et de la présence avec l’interface d’Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ea64c-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="ea64c-107">Pour activer cette intégration, vous devez configurer le serveur Edge dans votre déploiement Skype entreprise Server sur site en effectuant les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ea64c-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="ea64c-108">configurer un espace d’adressage SIP partagé ;</span><span class="sxs-lookup"><span data-stu-id="ea64c-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="ea64c-109">Configurer un fournisseur d’hébergement sur le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="ea64c-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="ea64c-110">Vérifier la réplication du magasin central de gestion mis à jour</span><span class="sxs-lookup"><span data-stu-id="ea64c-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="ea64c-111">Configurer un espace d’adressage SIP partagé</span><span class="sxs-lookup"><span data-stu-id="ea64c-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="ea64c-112">Pour intégrer Skype entreprise Server sur site à Exchange Online, vous devez configurer un espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="ea64c-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="ea64c-113">Le même espace d’adressage de domaine SIP est pris en charge par Skype entreprise Server et le service Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea64c-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="ea64c-114">À l’aide de Skype entreprise Server Management Shell, configurez le serveur Edge pour la Fédération en exécutant la cmdlet **Set-CSAccessEdgeConfiguration** à l’aide des paramètres affichés dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="ea64c-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="ea64c-115">Le paramètre **AllowFederatedUsers** indique si les utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="ea64c-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="ea64c-116">Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adressage SIP partagé avec Skype entreprise Server et Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea64c-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="ea64c-117">Pour plus d’informations sur l’utilisation de Skype entreprise Server Management Shell, voir [Skype for Business Server Management Shell](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ea64c-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ea64c-118">Configurer un fournisseur d’hébergement sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="ea64c-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="ea64c-119">À l’aide de Skype entreprise Server Management Shell, configurez un fournisseur d’hébergement sur le serveur Edge en exécutant la cmdlet **New-CsHostingProvider** à l’aide des paramètres de l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="ea64c-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="ea64c-120">Si vous utilisez Microsoft 365 ou Office 365 géré par 21Vianet en Chine, remplacez la valeur du paramètre ProxyFqdn dans cet exemple ("exap.um.outlook.com") par le nom de domaine complet (FQDN) du service géré par 21Vianet : "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="ea64c-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="ea64c-121">Si vous utilisez Microsoft 365 ou Office 365 GCC High, remplacez la valeur du paramètre ProxyFqdn dans cet exemple ("exap.um.outlook.com") par le nom de domaine complet (FQDN) de GCC High : "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="ea64c-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="ea64c-122">**Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »).</span><span class="sxs-lookup"><span data-stu-id="ea64c-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="ea64c-123">Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="ea64c-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="ea64c-124">**Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée.</span><span class="sxs-lookup"><span data-stu-id="ea64c-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ea64c-125">Ce paramètre doit avoir la valeur True.</span><span class="sxs-lookup"><span data-stu-id="ea64c-125">This must be set to True.</span></span>

- <span data-ttu-id="ea64c-126">**EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="ea64c-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ea64c-127">Ce paramètre doit avoir la valeur True.</span><span class="sxs-lookup"><span data-stu-id="ea64c-127">This must be set to True.</span></span>

- <span data-ttu-id="ea64c-128">**HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Office Communications Server ou Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ea64c-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="ea64c-129">Ce paramètre doit avoir la valeur False.</span><span class="sxs-lookup"><span data-stu-id="ea64c-129">This must be set to False.</span></span>

- <span data-ttu-id="ea64c-130">**ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="ea64c-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="ea64c-131">Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ea64c-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="ea64c-132">**IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ea64c-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="ea64c-133">Ce paramètre doit avoir la valeur False.</span><span class="sxs-lookup"><span data-stu-id="ea64c-133">This must be set to False.</span></span>

- <span data-ttu-id="ea64c-134">**VerificationLevel** Indique le niveau de vérification autorisé pour les messages échangés avec le fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="ea64c-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="ea64c-135">Spécifiez **UseSourceVerification**, qui s’appuie sur le niveau de vérification inclus dans les messages envoyés par le fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="ea64c-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="ea64c-136">Si ce niveau n’est pas spécifié, le message sera rejeté comme non vérifiable.</span><span class="sxs-lookup"><span data-stu-id="ea64c-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="ea64c-137">Vérifier la réplication du magasin central de gestion mis à jour</span><span class="sxs-lookup"><span data-stu-id="ea64c-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="ea64c-138">Les modifications que vous avez apportées à l’aide des applets de commande dans les sections précédentes sont appliquées automatiquement au serveur Edge et prennent généralement moins d’une minute à répliquer.</span><span class="sxs-lookup"><span data-stu-id="ea64c-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="ea64c-139">Vous pouvez valider l’état de la réplication, puis confirmer que les modifications ont été appliquées à votre serveur Edge à l’aide des applets de commande suivantes.</span><span class="sxs-lookup"><span data-stu-id="ea64c-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="ea64c-140">Pour vérifier les mises à jour de réplication, sur un serveur interne dans votre déploiement de Skype entreprise Server, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ea64c-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="ea64c-141">Vérifiez si la valeur UpToDate indique TRUE pour tous les réplicas.</span><span class="sxs-lookup"><span data-stu-id="ea64c-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="ea64c-142">Pour confirmer que les modifications ont été appliquées, sur le serveur Edge, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ea64c-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="ea64c-143">Double vérifier si les informations indiquées correspondent aux modifications validées lors des étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="ea64c-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea64c-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea64c-144">See also</span></span>

[<span data-ttu-id="ea64c-145">Fourniture de la messagerie vocale des utilisateurs de Skype entreprise Server sur la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="ea64c-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="ea64c-146">Intégration de la messagerie unifiée Exchange hébergée dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ea64c-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
