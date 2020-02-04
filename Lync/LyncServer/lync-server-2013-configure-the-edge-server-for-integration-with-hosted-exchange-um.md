---
title: Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a801ba4bf5f67eeda2eb760b3f639bac4cd13b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="57175-102">Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="57175-102">Configure the Edge Server for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57175-103">_**Dernière modification de la rubrique :** 2015-01-23_</span><span class="sxs-lookup"><span data-stu-id="57175-103">_**Topic Last Modified:** 2015-01-23_</span></span>

<span data-ttu-id="57175-104">Pour fournir aux utilisateurs de Lync Server 2013 des fonctionnalités de messagerie vocale sur la messagerie unifiée Exchange hébergée (MU), vous devez effectuer les tâches de configuration suivantes sur le serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="57175-104">To provide your Lync Server 2013 users with voice mail capabilities on hosted Exchange Unified Messaging (UM), you must perform the following configuration tasks on the Edge Server:</span></span>

  - <span data-ttu-id="57175-105">Configurez le serveur Edge pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="57175-105">Configure the Edge Server for federation.</span></span>

  - <span data-ttu-id="57175-106">Répliquez les données du magasin central de gestion sur le serveur Edge et vérifiez la réplication.</span><span class="sxs-lookup"><span data-stu-id="57175-106">Replicate Central Management store data to the Edge Server and verify the replication.</span></span>

  - <span data-ttu-id="57175-107">Créez un fournisseur d’hébergement sur le serveur de périphérie.</span><span class="sxs-lookup"><span data-stu-id="57175-107">Create a hosting provider on the Edge Server.</span></span>

<span data-ttu-id="57175-108">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="57175-108">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="57175-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57175-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="57175-110">[Nouveau-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57175-110">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="57175-111">Avant d’effectuer ces étapes, vous devez créer un enregistrement SRV DNS pour le service Exchange d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="57175-111">You must create an external DNS SRV record for the hosting Exchange service before you perform these steps.</span></span> <span data-ttu-id="57175-112">Pour plus d’informations, consultez <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">créer un enregistrement SRV DNS pour l’intégration à la messagerie unifiée Exchange hébergée</A>.</span><span class="sxs-lookup"><span data-stu-id="57175-112">For details, see <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Create a DNS SRV record for integration with hosted Exchange UM</A>.</span></span>



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a><span data-ttu-id="57175-113">Pour configurer le serveur de périphérique pour la fédération</span><span class="sxs-lookup"><span data-stu-id="57175-113">To configure the Edge Server for federation</span></span>

1.  <span data-ttu-id="57175-114">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="57175-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="57175-p102">Exécutez l’applet de commande Set-CsAccessEdgeConfiguration pour configurer le serveur pour la fédération. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="57175-p102">Run the Set-CsAccessEdgeConfiguration cmdlet to configure the server for federation. For example, run:</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    <span data-ttu-id="57175-117">L’exemple qui précède définit les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="57175-117">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="57175-118">\*\*UseDnsSrvRouting \*\* indique que les serveurs Edge doivent reposer sur les enregistrements DNS SRV lors de l’envoi et la réception des demandes de fédération.</span><span class="sxs-lookup"><span data-stu-id="57175-118">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="57175-p103">\*\*AllowFederatedUsers \*\* indique si des utilisateurs internes sont autorisés à communiquer avec des utilisateurs de domaines fédérés. Cette propriété détermine également si des utilisateurs internes peuvent communiquer avec des utilisateurs de domaines fractionnés.</span><span class="sxs-lookup"><span data-stu-id="57175-p103">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="57175-121">**EnablePartnerDiscovery** indique si Lync Server utilisera les enregistrements DNS pour essayer de découvrir les domaines de partenariat qui ne sont pas répertoriés dans la liste des domaines autorisés Active Directory.</span><span class="sxs-lookup"><span data-stu-id="57175-121">**EnablePartnerDiscovery** specifies whether Lync Server will use DNS records to try to discover partner domains not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="57175-122">Si faux, Lync Server 2013 ne se fédérera que par les domaines figurant dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="57175-122">If False, Lync Server 2013 will only federate with domains found on the allowed domains list.</span></span> <span data-ttu-id="57175-123">Ce paramètre est requis si vous utilisez le routage de service DNS.</span><span class="sxs-lookup"><span data-stu-id="57175-123">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="57175-124">Dans la plupart des déploiements, la valeur est définie sur False pour empêcher l’ouverture de la fédération à tous les partenaires.</span><span class="sxs-lookup"><span data-stu-id="57175-124">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a><span data-ttu-id="57175-125">Pour répliquer des données sur le serveur de périphérie et vérifier que la réplication s’est correctement effectuée</span><span class="sxs-lookup"><span data-stu-id="57175-125">To replicate data to the Edge Server and verify the replication</span></span>

  - <span data-ttu-id="57175-126">Vérifiez que la réplication du serveur de périphérie est complète.</span><span class="sxs-lookup"><span data-stu-id="57175-126">Verify that the replication to the Edge Server is complete.</span></span> <span data-ttu-id="57175-127">Pour la procédure, voir [Vérifier la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="57175-127">For the procedure, see [Verify connectivity between internal servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span></span>

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="57175-128">Pour créer un fournisseur d’hébergement sur le serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="57175-128">To create a hosting provider on the Edge Server</span></span>

1.  <span data-ttu-id="57175-129">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="57175-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="57175-130">Exécutez l’applet de commande **New-CsHostingProvider** pour configurer le fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="57175-130">Run the **New-CsHostingProvider** cmdlet to configure the hosting provider.</span></span> <span data-ttu-id="57175-131">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="57175-131">For example, run:</span></span>
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="57175-132">L’exemple qui précède définit les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="57175-132">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="57175-p107">\*\*Identity \*\* spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez, par exemple, \*\*Fabrikam.com \*\*. Notez que la commande échouera si un fournisseur existant a déjà été configuré avec ce paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="57175-p107">**Identity** specifies a unique string value identifier for the hosting provider you are creating, in this example, **Fabrikam.com**. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="57175-p108">\*\*Enabled \*\* indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux entreprises tant que cette valeur n’est pas définie sur \*\*True \*\*.</span><span class="sxs-lookup"><span data-stu-id="57175-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="57175-137">\*\*EnabledSharedAddressSpace \*\* indique si le fournisseur d’hébergement sera utilisé dans un scénario d’espace d’adresse SIP partagé (domaine fractionné).</span><span class="sxs-lookup"><span data-stu-id="57175-137">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="57175-138">Avant d’avoir <CODE>EnableSharedAddressSpace</CODE> défini sur true, essayez de résoudre l’enregistrement SRV de Fédération en interne.</span><span class="sxs-lookup"><span data-stu-id="57175-138">Before you set <CODE>EnableSharedAddressSpace</CODE> to True, try to resolve the Federation SRV record internally.</span></span> <span data-ttu-id="57175-139">Si cet enregistrement ne peut pas être résolu en interne, vous devez créer les enregistrements, _sipfederationtls. _tcp. &lt;domain&gt; et _sip. _tls. &lt;Domain&gt; dans le DNS interne.</span><span class="sxs-lookup"><span data-stu-id="57175-139">If this record cannot be resolved internally, then you need to create the records, _sipfederationtls._tcp.&lt;domain&gt; and _sip._tls.&lt;domain&gt; in the internal DNS.</span></span> <span data-ttu-id="57175-140">Ces enregistrements doivent pointer vers l’adresse IP externe de l’interface d’accès du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="57175-140">These records should point to the external IP address of the Access Interface of the Edge Server.</span></span>

        
        </div>
    
      - <span data-ttu-id="57175-141">**HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger des comptes Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57175-141">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="57175-142">Si la valeur est \*\*False \*\*, le fournisseur héberge d’autres types de comptes, comme des comptes Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="57175-142">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="57175-p111">\*\*ProxyFQDN \*\* spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement, dans cet exemple, \*\*proxyserver.fabrikam.com \*\*. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement change de serveur proxy, vous devrez supprimer puis recréer l’entrée pour ce fournisseur.</span><span class="sxs-lookup"><span data-stu-id="57175-p111">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, in this example, **proxyserver.fabrikam.com**. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="57175-146">**IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57175-146">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span>
    
      - <span data-ttu-id="57175-147">\*\*VerificationLevel \*\* indique le niveau de vérification autorisé pour les messages à destination et en provenance du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="57175-147">**VerficationLevel** indicates the allowed verification level for messages sent to and from the hosted provider.</span></span> <span data-ttu-id="57175-148">Spécifiez **UseSourceVerification**, qui repose sur le niveau de vérification inclus dans les messages en provenance du fournisseur hébergé.</span><span class="sxs-lookup"><span data-stu-id="57175-148">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="57175-149">Si ce niveau n’est pas spécifié, le message sera rejeté comme message non vérifiable.</span><span class="sxs-lookup"><span data-stu-id="57175-149">If this level is not specified, then the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57175-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57175-150">See Also</span></span>


[<span data-ttu-id="57175-151">Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge</span><span class="sxs-lookup"><span data-stu-id="57175-151">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[<span data-ttu-id="57175-152">Vérification de la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57175-152">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


<span data-ttu-id="57175-153">[Nouveau-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="57175-153">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

