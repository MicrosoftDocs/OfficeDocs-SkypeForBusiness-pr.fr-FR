---
title: 'Lync Server 2013 : configuration de DNS pour la prise en charge du serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e22228ec089f5632f30d4eabc2e8c32d87b5e2d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="f5926-102">Configuration de DNS pour la prise en charge du serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5926-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5926-103">_**Dernière modification de la rubrique :** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="f5926-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="f5926-104">Vous devez configurer des enregistrements DNS pour les interfaces Edge internes et externes, notamment pour les interfaces des serveurs Edge et proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="f5926-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="f5926-105">Par défaut, les serveurs Edge ne sont pas joints à un domaine et n’ont pas de nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="f5926-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="f5926-106">Il est fait référence au serveur Edge par un nom court (ordinateur) et non un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="f5926-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="f5926-107">Toutefois, le générateur de topologies utilise des noms de domaine complets, pas des noms courts.</span><span class="sxs-lookup"><span data-stu-id="f5926-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="f5926-108">Le nom du serveur Edge doit correspondre au nom de domaine complet utilisé par le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f5926-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="f5926-109">Pour ce faire, vous définissez un suffixe DNS qui, quand il est associé au nom de l’ordinateur, correspond au nom de domaine complet attendu.</span><span class="sxs-lookup"><span data-stu-id="f5926-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="f5926-110">Utilisez la procédure suivante de « Pour ajouter le suffixe DNS au nom d’ordinateur du serveur Edge qui n’est pas joint à un domaine » pour ajouter le suffixe DNS au nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f5926-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5926-111">Par défaut, DNS utilise un algorithme de répétition alternée pour faire pivoter l’ordre des données des enregistrements de ressource renvoyées dans les réponses aux requêtes où existent plusieurs enregistrements de ressources du même type pour un nom de domaine DNS interrogé.</span><span class="sxs-lookup"><span data-stu-id="f5926-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="f5926-112">L’équilibrage de charge DNS de Lync Server 2013, dépend de la répétition alternée DNS dans le cadre du mécanisme d’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="f5926-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="f5926-113">Vérifiez que le paramètre Round-Robin n’a pas été désactivé.</span><span class="sxs-lookup"><span data-stu-id="f5926-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="f5926-114">Si vous utilisez un serveur DNS qui n’exécute pas de système d’exploitation Windows, vérifiez que la commande d’enregistrement de ressource à répétition alternée est activée.</span><span class="sxs-lookup"><span data-stu-id="f5926-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="f5926-115">Utilisez les procédures suivantes de « **Pour créer un enregistrement DNS SRV** » pour créer et vérifier chaque enregistrement DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="f5926-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="f5926-116">Utilisez la procédure de « **Pour créer un enregistrement DNS A** » pour définir les enregistrements DNS A requis pour l’accès utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="f5926-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="f5926-117">Pour confirmer que les enregistrements sont configurés et fonctionnent correctement, voir « **Pour vérifier un enregistrement DNS** » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f5926-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="f5926-118">Pour plus d’informations sur chaque enregistrement requis pour prendre en charge l’accès des utilisateurs externes, voir [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5926-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="f5926-119">Pour ajouter le suffixe DNS au nom de l’ordinateur sur un serveur Edge qui n’est pas joint à un domaine</span><span class="sxs-lookup"><span data-stu-id="f5926-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="f5926-120">Sur l’ordinateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Ordinateur**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f5926-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="f5926-121">Sous **Paramètres de nom d’ordinateur, de domaine et de groupe de travail**, cliquez sur **Modifier les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="f5926-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="f5926-122">Sous l’onglet **Nom de l’ordinateur**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f5926-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="f5926-123">Dans **Modification du nom ou du domaine de l’ordinateur**, cliquez sur **Plus**.</span><span class="sxs-lookup"><span data-stu-id="f5926-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="f5926-124">Dans **Nom d’ordinateur NetBIOS et suffixe DNS**, dans **Suffixe DNS principal de cet ordinateur**, tapez le nom de votre domaine interne (par exemple, corp.contoso.com), puis cliquez trois fois sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5926-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="f5926-125">Redémarrez l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f5926-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="f5926-126">Pour créer un enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="f5926-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="f5926-127">Sur le serveur DNS approprié, cliquez sur **Démarrer**, sur **Panneau de configuration**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f5926-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f5926-128">Vous devez configurer DNS de sorte qu’il y ait : 1) entrées DNS externes pour les recherches DNS externes par les utilisateurs distants et les partenaires fédérés ; 2) entrées pour les recherches DNS utilisées par les serveurs Edge dans le réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré), y compris les enregistrements A pour les serveurs internes exécutant Lync Server 2013 ; et 3) entrées DNS internes pour les recherches par les clients et serveurs internes exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5926-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="f5926-129">Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine où Lync Server 2013 est installé.</span><span class="sxs-lookup"><span data-stu-id="f5926-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="f5926-130">Cliquez sur **Nouveaux enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="f5926-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="f5926-131">Dans **Choisissez un type d’enregistrement de ressource**, tapez **Emplacement du service (SRV)**, puis cliquez sur **Créer un enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="f5926-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="f5926-132">Fournissez toutes les informations requises pour l’enregistrement DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="f5926-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="f5926-133">Pour créer un enregistrement DNS A</span><span class="sxs-lookup"><span data-stu-id="f5926-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="f5926-134">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Panneau de configuration**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f5926-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f5926-135">Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 est installé.</span><span class="sxs-lookup"><span data-stu-id="f5926-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="f5926-136">Cliquez sur **Nouvel hôte (A)**.</span><span class="sxs-lookup"><span data-stu-id="f5926-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="f5926-137">Fournissez toutes les informations requises pour l’enregistrement DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="f5926-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="f5926-138">Pour vérifier un enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="f5926-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="f5926-139">Ouvrez une session sur un ordinateur client du domaine.</span><span class="sxs-lookup"><span data-stu-id="f5926-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="f5926-140">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f5926-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f5926-141">À l’invite de commandes, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f5926-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="f5926-142">Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="f5926-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5926-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5926-143">See Also</span></span>


[<span data-ttu-id="f5926-144">Créer un enregistrement SRV DNS pour l’intégration à la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="f5926-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="f5926-145">Déterminer les exigences DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5926-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

