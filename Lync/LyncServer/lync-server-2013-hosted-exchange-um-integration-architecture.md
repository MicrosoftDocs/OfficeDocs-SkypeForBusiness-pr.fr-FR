---
title: 'Lync Server 2013 : Architecture d’intégration de messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="41a78-102">Architecture d’intégration de messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41a78-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41a78-103">_**Dernière modification de la rubrique:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="41a78-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="41a78-104">L’application de routage de ExUM Lync Server 2013 prend en charge l’intégration avec un déploiement de messagerie unifiée Exchange local (MU), avec la messagerie unifiée hébergée par un fournisseur de service ou avec une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="41a78-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="41a78-105">Le diagramme suivant présente les trois possibilités.</span><span class="sxs-lookup"><span data-stu-id="41a78-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="41a78-106">**Intégration avec un déploiement Exchange UM local et deux fournisseurs Exchange hébergés**</span><span class="sxs-lookup"><span data-stu-id="41a78-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="41a78-107">![Déploiement de la messagerie unifiée Exchange Server en local] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Déploiement de la messagerie unifiée Exchange Server en local")</span><span class="sxs-lookup"><span data-stu-id="41a78-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="41a78-108">Les modes suivants sont pris en charge:</span><span class="sxs-lookup"><span data-stu-id="41a78-108">The following modes are supported:</span></span>

  - <span data-ttu-id="41a78-109">**Déploiement local:** Lync Server 2013 et la messagerie unifiée Exchange sont tous deux déployés sur des serveurs locaux au sein de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="41a78-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="41a78-110">**Déploiement sur site:** Lync Server 2013 est déployé sur des serveurs locaux au sein de votre entreprise et la messagerie unifiée Exchange est hébergée dans une installation de prestataire de services en ligne, telle qu’un centre de données Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41a78-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="41a78-111">**Déploiement mixte:** Votre déploiement de Lync Server 2013 dispose de certaines boîtes aux lettres d’utilisateurs hébergées sur des serveurs Exchange locaux au sein de votre entreprise, et de certaines boîtes aux lettres dans un centre de données de service Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="41a78-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41a78-112">Le déploiement mixte peut être utilisé en tant que solution de transition lors de l’évaluation et de la migration par phases des utilisateurs vers la messagerie unifiée Exchange hébergée, ou d’une solution permanente si vous choisissez de limiter les services de messagerie unifiée d’échange des utilisateurs en local après le transfert d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="41a78-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="41a78-113">Espace d’adressage SIP partagé</span><span class="sxs-lookup"><span data-stu-id="41a78-113">Shared SIP Address Space</span></span>

<span data-ttu-id="41a78-114">Pour intégrer Lync Server 2013 à un déploiement Exchange UM local, vous accordez l’autorisation Lync Server 2013 aux objets services de domaine Active Directory UM.</span><span class="sxs-lookup"><span data-stu-id="41a78-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="41a78-115">Toutefois, cette approche ne fonctionne pas pour l’intégration à la messagerie unifiée Exchange hébergée, car Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts distinctes sans approbation.</span><span class="sxs-lookup"><span data-stu-id="41a78-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="41a78-116">Pour intégrer Lync Server 2013 et la messagerie unifiée Exchange hébergée, vous devez configurer un *espace d’adressage SIP partagé*.</span><span class="sxs-lookup"><span data-stu-id="41a78-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="41a78-117">Dans cette configuration, le même espace d’adressage de domaine SIP est disponible pour Lync Server 2013 et le fournisseur de service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="41a78-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41a78-118">L’utilisation de l’espace d’adressage SIP partagé est semblable à celle utilisée dans un environnement Lync Server 2013 multiplateforme, dans lequel certains utilisateurs sont hébergés dans le déploiement local, et certains sont hébergés dans un déploiement hébergé (par exemple, Lync Online).</span><span class="sxs-lookup"><span data-stu-id="41a78-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="41a78-119">Le domaine SIP est fractionné entre eux.</span><span class="sxs-lookup"><span data-stu-id="41a78-119">The SIP domain is split between them.</span></span> <span data-ttu-id="41a78-120">Lorsque vous intégrez Lync Server 2013 à une messagerie unifiée Exchange hébergée, veillez à inclure le fournisseur de service de messagerie unifiée Exchange dans l’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="41a78-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="41a78-121">Pour configurer l’espace d’adressage SIP partagé à des fins d’intégration à un fournisseur de service de messagerie unifiée Exchange, vous devez configurer votre serveur Edge comme suit:</span><span class="sxs-lookup"><span data-stu-id="41a78-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="41a78-122">Configurez le serveur Edge pour la Fédération en exécutant l’applet de commande **Set-CsAccessEdgeConfiguration** pour définir les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="41a78-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="41a78-123">\*\*UseDnsSrvRouting \*\* indique que les serveurs Edge doivent reposer sur les enregistrements DNS SRV lors de l’envoi et la réception des demandes de fédération.</span><span class="sxs-lookup"><span data-stu-id="41a78-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="41a78-p105">\*\*AllowFederatedUsers \*\* indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si des utilisateurs internes peuvent communiquer avec des utilisateurs de domaines fractionnés.</span><span class="sxs-lookup"><span data-stu-id="41a78-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="41a78-126">**EnablePartnerDiscovery** spécifie si Lync Server 2013 utilisera les enregistrements DNS pour essayer de détecter des domaines de partenariat qui ne sont pas répertoriés dans la liste des domaines autorisés Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41a78-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="41a78-127">Si faux, Lync Server 2013 se fédérera uniquement avec les domaines qui se trouvent sur la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="41a78-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="41a78-128">Ce paramètre est requis si vous utilisez le routage de service DNS.</span><span class="sxs-lookup"><span data-stu-id="41a78-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="41a78-129">Dans la plupart des déploiements, la valeur est définie sur False pour empêcher l’ouverture de la fédération à tous les partenaires.</span><span class="sxs-lookup"><span data-stu-id="41a78-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="41a78-130">Répliquez le magasin de gestion central sur le serveur Edge et vérifiez la réplication.</span><span class="sxs-lookup"><span data-stu-id="41a78-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="41a78-131">Pour plus d’informations, reportez-vous [à exporter votre topologie Lync Server 2013 et à la copier sur média externe pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="41a78-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="41a78-132">Configurez un *fournisseur d’hébergement* sur le serveur Edge en exécutant l’applet de commande **New-CsHostingProvider** pour définir les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="41a78-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="41a78-133">**Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez, par exemple, la **messagerie unifiée Exchange hébergée**.</span><span class="sxs-lookup"><span data-stu-id="41a78-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="41a78-134">\*\*Enabled \*\* indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée.</span><span class="sxs-lookup"><span data-stu-id="41a78-134">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="41a78-135">Doit avoir la valeur **true**.</span><span class="sxs-lookup"><span data-stu-id="41a78-135">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="41a78-136">**EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="41a78-136">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="41a78-137">Doit avoir la valeur **true**.</span><span class="sxs-lookup"><span data-stu-id="41a78-137">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="41a78-138">**HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger des comptes Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41a78-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="41a78-139">Doit être défini sur **false**.</span><span class="sxs-lookup"><span data-stu-id="41a78-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="41a78-140">**ProxyFQDN** spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur d’hébergement (par exemple, **ProxyServer.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="41a78-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="41a78-141">Pour obtenir ces informations, contactez votre fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="41a78-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="41a78-142">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="41a78-142">This value cannot be modified.</span></span> <span data-ttu-id="41a78-143">Si le fournisseur d’hébergement a modifié son serveur proxy, vous devez supprimer, puis recréer l’entrée pour ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="41a78-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="41a78-144">**IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41a78-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="41a78-145">Doit être défini sur **false**.</span><span class="sxs-lookup"><span data-stu-id="41a78-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

