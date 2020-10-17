---
title: 'Lync Server 2013 : architecture d’intégration de la messagerie unifiée Exchange hébergée'
description: 'Lync Server 2013 : architecture d’intégration de la messagerie unifiée Exchange hébergée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2399fa421b59a5ea1fd83b1a86225fc12de1f2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552460"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="39512-103">Architecture d’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39512-103">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39512-104">_**Dernière modification de la rubrique :** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="39512-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="39512-105">L’application de routage ExUM de Lync Server 2013 prend en charge l’intégration à un déploiement de messagerie unifiée Exchange sur site, avec la messagerie unifiée Exchange hébergée par un fournisseur de services ou avec une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="39512-105">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="39512-106">Le diagramme suivant montre les trois possibilités.</span><span class="sxs-lookup"><span data-stu-id="39512-106">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="39512-107">**Intégration à un déploiement de messagerie unifiée Exchange sur site et à deux déploiements Exchange hébergés par des fournisseurs de service**</span><span class="sxs-lookup"><span data-stu-id="39512-107">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="39512-108">![Déploiement de la messagerie unifiée Lync Server Exchange sur site](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Déploiement de la messagerie unifiée Lync Server Exchange sur site")</span><span class="sxs-lookup"><span data-stu-id="39512-108">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="39512-109">Les modes suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="39512-109">The following modes are supported:</span></span>

  - <span data-ttu-id="39512-110">**Déploiement sur site :** Lync Server 2013 et la messagerie unifiée Exchange sont tous deux déployés sur des serveurs locaux dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="39512-110">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="39512-111">**Déploiement** intersites : Lync Server 2013 est déployé sur des serveurs locaux dans votre entreprise et la messagerie unifiée Exchange est hébergée dans une installation de fournisseur de services en ligne, telle qu’un centre de données Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="39512-111">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="39512-112">**Déploiement mixte :** Votre déploiement Lync Server 2013 comporte des boîtes aux lettres d’utilisateur hébergées sur des serveurs Exchange locaux dans votre entreprise et des boîtes aux lettres hébergées dans un centre de données de service Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="39512-112">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39512-113">Le déploiement mixte peut tenir lieu de solution de transition au cours de l’évaluation et de la migration progressive des utilisateurs vers un service de messagerie unifiée Exchange hébergé, ou de solution permanente, si vous décidez de conserver sur site les services de messagerie unifiée Exchange de certains utilisateurs après en avoir transféré d’autres.</span><span class="sxs-lookup"><span data-stu-id="39512-113">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="39512-114">Espace d’adressage SIP partagé</span><span class="sxs-lookup"><span data-stu-id="39512-114">Shared SIP Address Space</span></span>

<span data-ttu-id="39512-115">Pour intégrer Lync Server 2013 avec un déploiement de messagerie unifiée Exchange local, vous devez accorder à Lync Server 2013 l’autorisation de lire les objets des services de domaine Active Directory de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="39512-115">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="39512-116">Cette approche ne fonctionne pas pour l’intégration avec la messagerie unifiée Exchange hébergée, car Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts distinctes sans approbation.</span><span class="sxs-lookup"><span data-stu-id="39512-116">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="39512-117">Pour intégrer Lync Server 2013 à la messagerie unifiée Exchange hébergée, vous devez configurer un *espace d’adressage SIP partagé*.</span><span class="sxs-lookup"><span data-stu-id="39512-117">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="39512-118">Dans cette configuration, le même espace d’adressage de domaine SIP est disponible pour Lync Server 2013 et pour le fournisseur de services de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="39512-118">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39512-119">L’utilisation de l’espace d’adressage SIP partagé est semblable à l’approche utilisée dans un environnement Lync Server 2013 intersites, dans lequel certains utilisateurs sont hébergés dans le déploiement local et d’autres sont hébergés dans un déploiement hébergé (par exemple, Lync Online).</span><span class="sxs-lookup"><span data-stu-id="39512-119">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="39512-120">Le domaine SIP est fractionné entre les deux déploiements.</span><span class="sxs-lookup"><span data-stu-id="39512-120">The SIP domain is split between them.</span></span> <span data-ttu-id="39512-121">Lorsque vous intégrez Lync Server 2013 avec la messagerie unifiée Exchange hébergée, vérifiez que vous incluez le fournisseur de services de messagerie unifiée Exchange dans l’espace d’adressage SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="39512-121">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="39512-122">Pour configurer l’espace d’adressage SIP partagé en vue de l’intégration de Lync Server à un service de messagerie unifiée Exchange hébergé, vous devez configurer le serveur Edge comme suit :</span><span class="sxs-lookup"><span data-stu-id="39512-122">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="39512-123">Configurez le serveur Edge pour la fédération en exécutant l’applet de commande **Set-CsAccessEdgeConfiguration** qui permet de définir les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="39512-123">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="39512-124">**UseDnsSrvRouting** indique que les serveurs Edge doivent reposer sur les enregistrements DNS SRV lors de l’envoi et la réception des demandes de fédération.</span><span class="sxs-lookup"><span data-stu-id="39512-124">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="39512-p105">**AllowFederatedUsers** indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si des utilisateurs internes peuvent communiquer avec des utilisateurs de domaines fractionnés.</span><span class="sxs-lookup"><span data-stu-id="39512-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="39512-127">**EnablePartnerDiscovery** spécifie si Lync Server 2013 utilise des enregistrements DNS pour essayer de découvrir des domaines partenaires qui ne sont pas répertoriés dans la liste des domaines autorisés Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39512-127">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="39512-128">Si la valeur est false, Lync Server 2013 se fédérera uniquement avec les domaines qui se trouvent dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="39512-128">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="39512-129">Ce paramètre est requis si vous utilisez le routage de service DNS.</span><span class="sxs-lookup"><span data-stu-id="39512-129">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="39512-130">Dans la plupart des déploiements, la valeur est définie sur False pour empêcher l’ouverture de la fédération à tous les partenaires.</span><span class="sxs-lookup"><span data-stu-id="39512-130">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="39512-131">Répliquer le magasin central de gestion sur le serveur Edge et vérifier la réplication.</span><span class="sxs-lookup"><span data-stu-id="39512-131">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="39512-132">Pour plus d’informations, reportez-vous à la rubrique [Export Your Lync Server 2013 Topology and copy it to External Media for Edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="39512-132">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="39512-133">Configurez un *fournisseur d’hébergement* sur le serveur Edge en exécutant l’applet de commande **New-CsHostingProvider** qui permet de définir les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="39512-133">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="39512-134">**Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez, par exemple, **Messagerie unifiée Exchange hébergée**.</span><span class="sxs-lookup"><span data-stu-id="39512-134">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="39512-p108">**Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. La valeur doit être définie sur **True**.</span><span class="sxs-lookup"><span data-stu-id="39512-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="39512-p109">**EnabledSharedAddressSpace** indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adressage SIP partagé. La valeur doit être définie sur **True**.</span><span class="sxs-lookup"><span data-stu-id="39512-p109">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="39512-139">**HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39512-139">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="39512-140">La valeur doit être définie sur **False**.</span><span class="sxs-lookup"><span data-stu-id="39512-140">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="39512-141">**ProxyFQDN** indique le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement, par exemple, **proxyserver.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="39512-141">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="39512-142">Demandez cette information au fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="39512-142">Contact your hosting provider for this information.</span></span> <span data-ttu-id="39512-143">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="39512-143">This value cannot be modified.</span></span> <span data-ttu-id="39512-144">Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer et recréer l’entrée pour ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="39512-144">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="39512-145">**IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39512-145">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="39512-146">La valeur doit être définie sur **False**.</span><span class="sxs-lookup"><span data-stu-id="39512-146">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

