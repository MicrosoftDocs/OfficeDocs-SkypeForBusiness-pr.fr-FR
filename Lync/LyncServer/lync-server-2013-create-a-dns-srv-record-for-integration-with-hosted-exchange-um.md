---
title: Création d’un enregistrement SRV DNS pour l’intégrer à la messagerie unifiée Exchange hébergée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f96b8873e7d83b7025b43b111312185b8e5d5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="ec974-102">Création d’un enregistrement SRV DNS pour l’intégrer à la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="ec974-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec974-103">_**Dernière modification de la rubrique:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ec974-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ec974-104">Cette rubrique décrit comment configurer l’enregistrement SRV DNS (Domain Name System) requis pour un serveur Edge Lync Server 2013 pour le routage vers un service Exchange hébergé tel que Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ec974-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="ec974-105">Pour créer un enregistrement SRV DNS externe pour le service Exchange hébergé</span><span class="sxs-lookup"><span data-stu-id="ec974-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="ec974-106">Connectez-vous au serveur DNS externe en tant que membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="ec974-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="ec974-107">Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="ec974-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="ec974-108">Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, puis sélectionnez le domaine SIP dans lequel Lync Server 2013 sera installé.</span><span class="sxs-lookup"><span data-stu-id="ec974-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="ec974-109">Vous devez créer l’enregistrement SRV DNS dans le domaine SIP sur lequel Lync Server est ou sera installé.</span><span class="sxs-lookup"><span data-stu-id="ec974-109">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed.</span></span> <span data-ttu-id="ec974-110">Lorsque vous créez l’enregistrement SRV, le nom de domaine complet (FQDN) utilisé pour le champ Host qui offre ce service doit être le nom de domaine complet (FQDN) externe du pool Edge.</span><span class="sxs-lookup"><span data-stu-id="ec974-110">When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool.</span></span> <span data-ttu-id="ec974-111">Par exemple, si le nom de domaine complet externe de votre pool Edge est edge01.contoso.net, entrez cette valeur.</span><span class="sxs-lookup"><span data-stu-id="ec974-111">For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value.</span></span> <span data-ttu-id="ec974-112">Cela doit également se trouver dans le même domaine que l’enregistrement DNS hosts (A).</span><span class="sxs-lookup"><span data-stu-id="ec974-112">This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="ec974-113">Cliquez avec le bouton droit sur le domaine sélectionné, puis cliquez sur **nouveaux enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="ec974-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="ec974-114">Dans **type d’enregistrement de ressource**, cliquez sur **emplacement du service (SRV)**, puis cliquez sur **créer un enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="ec974-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="ec974-115">Dans **nouvel enregistrement de ressource**, cliquez sur **service**, puis tapez \*\* \_sipfederationtls\*\*.</span><span class="sxs-lookup"><span data-stu-id="ec974-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="ec974-116">Cliquez sur **protocole**, puis tapez \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="ec974-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="ec974-117">Cliquez sur **Numéro de port**, puis saisissez **5061**.</span><span class="sxs-lookup"><span data-stu-id="ec974-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="ec974-118">Cliquez sur **hôte proposant ce service**, puis tapez le nom de domaine complet (FQDN) du pool de périphériques lync Server 2013 qui permet d’accéder à votre système lync Server 2013 pour les clients externes approuvés.</span><span class="sxs-lookup"><span data-stu-id="ec974-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ec974-119">Le domaine doit également être configuré en tant que domaine forcé et accepté dans vos paramètres Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ec974-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="ec974-120">Pour plus d’informations, consultez créer des <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>domaines approuvés sur.</span><span class="sxs-lookup"><span data-stu-id="ec974-120">For details, see Create Accepted Domains at <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="ec974-121">Cliquez sur **OK**, puis sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="ec974-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="ec974-122">Pour vérifier que l’enregistrement SRV DNS a été correctement créé</span><span class="sxs-lookup"><span data-stu-id="ec974-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="ec974-123">Connectez-vous à un ordinateur client dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="ec974-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="ec974-124">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="ec974-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="ec974-125">À l’invite de commandes, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="ec974-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="ec974-126">Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="ec974-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ec974-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ec974-127">See Also</span></span>


[<span data-ttu-id="ec974-128">Création des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec974-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

