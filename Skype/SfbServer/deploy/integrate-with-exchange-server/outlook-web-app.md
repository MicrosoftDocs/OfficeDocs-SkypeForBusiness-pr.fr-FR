---
title: Configurer l’intégration entre locale Skype pour Business Server et Outlook Web App
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Résumé : Intégrer Skype pour Business Server et Outlook Web App.'
ms.openlocfilehash: 3bd5131fcdba3d3253021c711910b18f46e93ce4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216647"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="f04ec-103">Configurer l’intégration entre locale Skype pour Business Server et Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="f04ec-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="f04ec-104">**Résumé :** Intégrer Skype pour Business Server et Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="f04ec-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="f04ec-105">Les clients qui utilisent des locaux Skype pour les déploiements de serveur d’entreprise peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="f04ec-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="f04ec-106">Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique, l’intégration de la messagerie instantanée et de la présence dans l’interface d’Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="f04ec-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="f04ec-107">Pour activer cette intégration, vous devez configurer le serveur de périphérie dans votre Skype sur site pour le déploiement de serveur d’entreprise en effectuant les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="f04ec-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="f04ec-108">configurer un espace d’adressage SIP partagé ;</span><span class="sxs-lookup"><span data-stu-id="f04ec-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="f04ec-109">Configurer un fournisseur d’hébergement sur le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="f04ec-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="f04ec-110">Vérifier la réplication du magasin Central de gestion mis à jour</span><span class="sxs-lookup"><span data-stu-id="f04ec-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="f04ec-111">Configurer un espace d’adressage SIP partagé</span><span class="sxs-lookup"><span data-stu-id="f04ec-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="f04ec-112">Pour intégrer locale Skype pour Business Server avec Exchange Online, vous devez configurer un espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="f04ec-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="f04ec-113">Le même espace d’adresse de domaine SIP est pris en charge par Skype pour Business Server et le service Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f04ec-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="f04ec-114">À l’aide de la Skype pour Business Server Management Shell, configurez le serveur de périphérie pour la fédération en exécutant l’applet de commande **Set-CSAccessEdgeConfiguration** avec les paramètres affichés dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="f04ec-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="f04ec-115">Le paramètre **AllowFederatedUsers** indique si les utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="f04ec-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="f04ec-116">Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adresse SIP partagé avec Skype pour Business Server et Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f04ec-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="f04ec-117">Pour plus d’informations sur l’utilisation de la Skype pour Business Server Management Shell, voir [Skype pour Business Server Management Shell](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="f04ec-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="f04ec-118">Configurer un fournisseur d’hébergement sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="f04ec-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="f04ec-119">À l’aide de la Skype pour Business Server Management Shell, configurez un fournisseur d’hébergement sur le serveur Edge en exécutant l’applet de commande **New-CsHostingProvider** avec les paramètres de l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="f04ec-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="f04ec-120">Si vous utilisez Office 365 activé par 21Vianet en Chine, remplacez dans cet exemple la valeur du paramètre ProxyFqdn (« exap.um.outlook.com ») par le FQDN du service activé par 21Vianet: « exap.um.partner.outlook.cn ».</span><span class="sxs-lookup"><span data-stu-id="f04ec-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="f04ec-121">Si vous utilisez Office 365 GCC haute, remplacez la valeur du paramètre ProxyFqdn dans cet exemple (« exap.um.outlook.com ») avec le nom de domaine complet GCC High : « exap.um.office365.us ».</span><span class="sxs-lookup"><span data-stu-id="f04ec-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="f04ec-122">**Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »).</span><span class="sxs-lookup"><span data-stu-id="f04ec-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="f04ec-123">Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="f04ec-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="f04ec-124">\*\*Enabled \*\* indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée.</span><span class="sxs-lookup"><span data-stu-id="f04ec-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="f04ec-125">Ce paramètre doit avoir la valeur True.</span><span class="sxs-lookup"><span data-stu-id="f04ec-125">This must be set to True.</span></span>

- <span data-ttu-id="f04ec-126">**EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="f04ec-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="f04ec-127">Ce paramètre doit avoir la valeur True.</span><span class="sxs-lookup"><span data-stu-id="f04ec-127">This must be set to True.</span></span>

- <span data-ttu-id="f04ec-128">**HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Office Communications Server ou Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f04ec-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="f04ec-129">Ce paramètre doit avoir la valeur False.</span><span class="sxs-lookup"><span data-stu-id="f04ec-129">This must be set to False.</span></span>

- <span data-ttu-id="f04ec-130">**ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="f04ec-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="f04ec-131">Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f04ec-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="f04ec-132">**IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre Skype pour la topologie du serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f04ec-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="f04ec-133">Ce paramètre doit avoir la valeur False.</span><span class="sxs-lookup"><span data-stu-id="f04ec-133">This must be set to False.</span></span>

- <span data-ttu-id="f04ec-134">**VerificationLevel** Indique le niveau de vérification autorisé pour les messages qui sont envoyés vers ou à partir du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="f04ec-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="f04ec-135">Spécifiez **UseSourceVerification**, qui repose sur le niveau de vérification inclus dans les messages en provenance du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="f04ec-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="f04ec-136">Si ce niveau n’est pas spécifié, le message sera rejeté comme étant non vérifiables.</span><span class="sxs-lookup"><span data-stu-id="f04ec-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="f04ec-137">Vérifier la réplication du magasin central de gestion mis à jour</span><span class="sxs-lookup"><span data-stu-id="f04ec-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="f04ec-138">Les modifications apportées à l’aide des applets de commande dans les sections précédentes sont automatiquement appliquées au serveur de périphérie et prennent généralement moins d’une minute à répliquer.</span><span class="sxs-lookup"><span data-stu-id="f04ec-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="f04ec-139">Vous pouvez valider l’état de la réplication et confirmer que les modifications ont été appliquées à votre serveur Edge à l’aide des applets de commande suivantes.</span><span class="sxs-lookup"><span data-stu-id="f04ec-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="f04ec-140">Pour vérifier les mises à jour de réplication, sur un serveur interne dans votre Skype pour le déploiement de Business Server, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f04ec-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="f04ec-141">Vérifiez si UpToDate valeur affiche la valeur TRUE pour tous les réplicas.</span><span class="sxs-lookup"><span data-stu-id="f04ec-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="f04ec-142">Pour confirmer que les modifications ont été appliquées, sur le serveur Edge, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f04ec-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="f04ec-143">Vérifiez si les informations affichées établit une correspondance avec les modifications validées lors des étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="f04ec-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="f04ec-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f04ec-144">See also</span></span>

[<span data-ttu-id="f04ec-145">Fourniture Skype pour Business Server utilisateurs la messagerie vocale sur hébergé la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="f04ec-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="f04ec-146">Hébergée intégration de messagerie unifiée Exchange dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f04ec-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
