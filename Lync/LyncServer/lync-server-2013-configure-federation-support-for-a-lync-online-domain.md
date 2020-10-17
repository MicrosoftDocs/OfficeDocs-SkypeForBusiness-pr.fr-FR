---
title: 'Lync Server 2013 : configuration de la prise en charge de la Fédération pour un domaine Lync Online'
description: 'Lync Server 2013 : configuration de la prise en charge de la Fédération pour un domaine Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553300"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="f5dae-103">Configurer la prise en charge de la Fédération pour un domaine Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5dae-103">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5dae-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f5dae-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f5dae-105">La Fédération avec un client Microsoft Lync Online 2010 nécessite d’effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f5dae-105">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="f5dae-106">Configurez la prise en charge du domaine du client Lync Online 2010 (par exemple, contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="f5dae-106">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="f5dae-107">Comme indiqué dans la section [conditions préalables à la Fédération avec un client Lync Online dans Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) de cette documentation, vous devriez déjà avoir activé la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f5dae-107">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="f5dae-108">L’activation de la Fédération nécessite de spécifier la méthode à utiliser pour contrôler l’accès par les domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="f5dae-108">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="f5dae-109">Si vous avez configuré votre organisation pour utiliser la découverte, l’ajout du domaine à la liste autorisée de votre organisation est facultatif.</span><span class="sxs-lookup"><span data-stu-id="f5dae-109">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="f5dae-110">Si vous n’avez pas activé la découverte de domaine, vous devez ajouter le nom de domaine du client Lync Online à votre liste de domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="f5dae-110">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="f5dae-111">Vous pouvez ajouter un nom de domaine à l’aide du panneau de configuration Lync Server ou en exécutant la cmdlet **New-CSAllowedDomain** .</span><span class="sxs-lookup"><span data-stu-id="f5dae-111">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="f5dae-112">Pour plus d’informations sur l’utilisation du panneau de configuration Lync Server, notamment sur l’activation de la découverte de domaines, voir [Manage SIP Federated Providers for Your Organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f5dae-112">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="f5dae-113">Pour plus d’informations sur l’utilisation de la cmdlet **New-CSAllowedDomain** pour ajouter un domaine, voir [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f5dae-113">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5dae-114">Un client Lync Online peut avoir plusieurs domaines.</span><span class="sxs-lookup"><span data-stu-id="f5dae-114">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="f5dae-115">Si vous souhaitez fédérer avec plusieurs domaines, vous devez configurer la prise en charge pour chaque domaine individuel avec lequel vous souhaitez prendre en charge la Fédération, et l’administrateur du client Lync Online doit activer la Fédération pour chacun des domaines à fédéré.</span><span class="sxs-lookup"><span data-stu-id="f5dae-115">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="f5dae-116">Configurez la prise en charge du fournisseur d’hébergement du domaine Lync Online 2010 client avec lequel vous souhaitez fédérer.</span><span class="sxs-lookup"><span data-stu-id="f5dae-116">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="f5dae-117">Utilisez la procédure décrite dans cette section pour configurer la prise en charge du fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="f5dae-117">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5dae-118">Cette étape est requise uniquement pour la Fédération avec un domaine d’un client Lync Online, pas pour la Fédération avec un domaine déployé sur site sur un emplacement de partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="f5dae-118">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="f5dae-119">Pour configurer la prise en charge d’un fournisseur d’hébergement</span><span class="sxs-lookup"><span data-stu-id="f5dae-119">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="f5dae-120">À partir d’un serveur frontal, démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f5dae-120">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f5dae-121">Exécutez la cmdlet **New-CsHostingProvider** pour créer et configurer le fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="f5dae-121">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="f5dae-122">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f5dae-122">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="f5dae-123">L’exemple qui précède définit les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f5dae-123">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="f5dae-124">**Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez.</span><span class="sxs-lookup"><span data-stu-id="f5dae-124">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="f5dae-125">Notez que la commande échoue si un fournisseur existant a déjà été configuré avec cette identité.</span><span class="sxs-lookup"><span data-stu-id="f5dae-125">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="f5dae-126">**ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="f5dae-126">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="f5dae-127">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="f5dae-127">This value cannot be modified.</span></span> <span data-ttu-id="f5dae-128">Si le fournisseur d’hébergement modifie son serveur proxy, vous devrez supprimer, puis recréer l’entrée pour ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f5dae-128">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="f5dae-129">**VerificationLevel** spécifie comment (ou si) les messages envoyés à partir d’un fournisseur d’hébergement sont vérifiés pour s’assurer qu’ils ont été envoyés à partir de ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f5dae-129">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="f5dae-130">**Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée.</span><span class="sxs-lookup"><span data-stu-id="f5dae-130">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="f5dae-131">Les messages ne peuvent pas être échangés entre les deux organisations tant que cette valeur n’est pas définie sur **true**.</span><span class="sxs-lookup"><span data-stu-id="f5dae-131">Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="f5dae-132">**EnabledSharedAddressSpace** indique si le fournisseur d’hébergement est utilisé dans un scénario d’espace d’adressage SIP partagé (domaine fractionné).</span><span class="sxs-lookup"><span data-stu-id="f5dae-132">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="f5dae-133">**HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5dae-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="f5dae-134">Si la **valeur est false**, le fournisseur héberge d’autres types de comptes, tels que les comptes Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="f5dae-134">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="f5dae-135">**IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5dae-135">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="f5dae-136">Pour plus d’informations sur l’utilisation de cette cmdlet, voir [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f5dae-136">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

