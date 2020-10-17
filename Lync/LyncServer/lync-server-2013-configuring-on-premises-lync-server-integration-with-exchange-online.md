---
title: Configuration de l’intégration de Lync Server sur site avec Exchange Online
description: Configuration de l’intégration de Lync Server sur site avec Exchange Online.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c612bcdcdf4803bd6f9f2b38f1f9bb7dbad016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553934"
---
# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="2657e-103">Configuration de l’intégration de Lync Server 2013 sur site à Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2657e-103">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2657e-104">_**Dernière modification de la rubrique :** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="2657e-104">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="2657e-105">Les clients qui utilisent des déploiements Lync Server 2013 sur site peuvent configurer l’interopérabilité avec Microsoft Outlook Web App dans Microsoft Exchange Online dans un mode de déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="2657e-105">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="2657e-106">Les fonctionnalités d’interopérabilité comprennent l’ouverture de session unique et l’intégration de la messagerie instantanée et de la présence avec l’interface d’Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="2657e-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="2657e-107">Pour activer cette intégration, vous devez configurer le serveur Edge dans votre déploiement Lync Server local en effectuant les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="2657e-107">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="2657e-108">configurer un espace d’adressage SIP partagé ;</span><span class="sxs-lookup"><span data-stu-id="2657e-108">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="2657e-109">Configurer un fournisseur d’hébergement sur le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="2657e-109">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="2657e-110">Vérifier la réplication du magasin central de gestion mis à jour</span><span class="sxs-lookup"><span data-stu-id="2657e-110">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="2657e-111">Si Lync Server 2013 est intégré à Exchange Online, un utilisateur qui tente de se connecter à la messagerie instantanée depuis OWA est considéré comme un utilisateur distant ou externe.</span><span class="sxs-lookup"><span data-stu-id="2657e-111">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="2657e-112">Dans ce scénario, l’utilisateur doit avoir une stratégie d’accès externe assignée dont l’option suivante est sélectionnée :</span><span class="sxs-lookup"><span data-stu-id="2657e-112">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="2657e-113">**Autoriser les communications avec des utilisateurs distants**</span><span class="sxs-lookup"><span data-stu-id="2657e-113">**Enable communications with remote users**</span></span>

<span data-ttu-id="2657e-114">Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent à l’extérieur de votre pare-feu, tels que les télétravailleurs et les utilisateurs qui sont en déplacement, puissent se connecter à Lync Server via Internet.</span><span class="sxs-lookup"><span data-stu-id="2657e-114">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="2657e-115">Pour plus d’informations, consultez la rubrique [gestion de la stratégie d’accès externe dans Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="2657e-115">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="2657e-116">Configurer un espace d’adressage SIP partagé</span><span class="sxs-lookup"><span data-stu-id="2657e-116">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="2657e-117">Pour intégrer Lync Server 2013 sur site à Exchange Online, vous devez configurer un espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="2657e-117">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="2657e-118">Le même espace d’adressage de domaine SIP est pris en charge par Lync Server et le service Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2657e-118">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="2657e-119">À l’aide de Lync Server Management Shell, configurez le serveur Edge pour la Fédération en exécutant la cmdlet **Set-CSAccessEdgeConfiguration** à l’aide des paramètres affichés dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="2657e-119">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="2657e-120">**AllowFederatedUsers** indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="2657e-120">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="2657e-121">Cette propriété détermine également si les utilisateurs internes peuvent communiquer avec des utilisateurs dans un scénario d’espace d’adressage SIP partagé avec Lync Server et Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2657e-121">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="2657e-122">Pour plus d’informations sur l’utilisation de Lync Server Management Shell, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="2657e-122">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="2657e-123">Configurer un fournisseur d’hébergement sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="2657e-123">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="2657e-124">Utilisez Lync Server Management Shell pour configurer un fournisseur d’hébergement sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="2657e-124">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="2657e-125">Pour ce faire, exécutez la cmdlet **New-CsHostingProvider** à l’aide des paramètres de l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="2657e-125">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="2657e-126">Si vous utilisez Office 365 géré par 21Vianet en Chine, remplacez la valeur du paramètre <STRONG>ProxyFqdn</STRONG> dans cet exemple ("EXAP.um.Outlook.com") par le nom de domaine complet (FQDN) du service géré par 21ViaNet : "EXAP.um.Partner.Outlook.CN".</span><span class="sxs-lookup"><span data-stu-id="2657e-126">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="2657e-127">**Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez (par exemple, « Exchange Online »).</span><span class="sxs-lookup"><span data-stu-id="2657e-127">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="2657e-128">Les valeurs qui contiennent des espaces doivent être placées entre guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="2657e-128">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="2657e-129">**Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée.</span><span class="sxs-lookup"><span data-stu-id="2657e-129">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="2657e-130">Elle doit être définie sur **true**.</span><span class="sxs-lookup"><span data-stu-id="2657e-130">This must be set to **True**.</span></span>

  - <span data-ttu-id="2657e-131">**EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="2657e-131">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="2657e-132">Elle doit être définie sur **true**.</span><span class="sxs-lookup"><span data-stu-id="2657e-132">This must be set to **True**.</span></span>

  - <span data-ttu-id="2657e-133">**HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger Office Communications Server ou Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2657e-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="2657e-134">Il doit avoir la valeur **false**.</span><span class="sxs-lookup"><span data-stu-id="2657e-134">This must be set to **False**.</span></span>

  - <span data-ttu-id="2657e-135">**ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="2657e-135">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="2657e-136">Pour Exchange Online, le nom de domaine complet est exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2657e-136">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="2657e-137">**IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2657e-137">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="2657e-138">Il doit avoir la valeur **false**.</span><span class="sxs-lookup"><span data-stu-id="2657e-138">This must be set to **False**.</span></span>

  - <span data-ttu-id="2657e-139">**VerificationLevel** indique le niveau de vérification autorisé pour les messages échangés avec le fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="2657e-139">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="2657e-140">Spécifiez **UseSourceVerification**.</span><span class="sxs-lookup"><span data-stu-id="2657e-140">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="2657e-141">Cette option repose sur le niveau de vérification inclus dans les messages envoyés par le fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="2657e-141">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="2657e-142">Si ce niveau n’est pas spécifié, le message sera rejeté comme non vérifiable.</span><span class="sxs-lookup"><span data-stu-id="2657e-142">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="2657e-143">Vérifier la réplication du magasin central de gestion mis à jour</span><span class="sxs-lookup"><span data-stu-id="2657e-143">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="2657e-144">Les modifications que vous avez apportées à l’aide des cmdlets dans les sections précédentes sont appliquées automatiquement au serveur Edge et prennent généralement moins d’une minute pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="2657e-144">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="2657e-145">Vous pouvez vérifier l’état de la réplication et que les modifications ont été appliquées à votre serveur Edge à l’aide des applets de commande suivantes.</span><span class="sxs-lookup"><span data-stu-id="2657e-145">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="2657e-146">Pour vérifier les mises à jour de réplication sur un serveur interne dans votre déploiement Lync Server, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="2657e-146">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="2657e-147">Pour vérifier que les modifications ont été appliquées, exécutez l’applet de commande suivante sur le serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="2657e-147">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2657e-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2657e-148">See Also</span></span>


[<span data-ttu-id="2657e-149">Fourniture de la messagerie vocale des utilisateurs de Lync Server 2013 sur la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="2657e-149">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="2657e-150">Intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2657e-150">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
