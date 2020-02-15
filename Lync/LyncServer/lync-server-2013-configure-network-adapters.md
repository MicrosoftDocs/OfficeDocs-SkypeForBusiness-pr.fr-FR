---
title: 'Lync Server 2013 : configuration des cartes réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c114766bffb665e2c7da2850fefc6113365e4c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="f685a-102">Configurer les cartes réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f685a-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f685a-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f685a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f685a-104">Vous devez affecter une ou plusieurs adresses IP à la carte réseau externe et au moins une adresse IP à la carte réseau interne.</span><span class="sxs-lookup"><span data-stu-id="f685a-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="f685a-105">Dans les procédures suivantes, le serveur exécutant soit le service Forefront Threat Management Gateway (TMG) 2010, soit le routage des demandes d’application Internet Information Server a deux cartes réseau :</span><span class="sxs-lookup"><span data-stu-id="f685a-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="f685a-106">une carte réseau publique ou externe pour les clients qui tentent de se connecter à votre site web (habituellement par le biais d’Internet) ;</span><span class="sxs-lookup"><span data-stu-id="f685a-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="f685a-107">Une interface réseau privée, ou interne, pour les serveurs internes exécutant Lync Server qui hébergent des services Web.</span><span class="sxs-lookup"><span data-stu-id="f685a-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f685a-108">De la même manière que pour les serveurs Edge, vous devez définir la passerelle par défaut sur la carte réseau externe uniquement.</span><span class="sxs-lookup"><span data-stu-id="f685a-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="f685a-109">La passerelle par défaut est l’adresse IP du routeur ou du pare-feu côté externe qui dirige le trafic vers Internet.</span><span class="sxs-lookup"><span data-stu-id="f685a-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="f685a-110">Pour le trafic destiné à la carte réseau côté interne face à partir du proxy inverse, vous devez utiliser des itinéraires statiques permanents (notamment la commande route dans Windows Server) pour tous les sous-réseaux contenant des serveurs référencés par les règles de publication web.</span><span class="sxs-lookup"><span data-stu-id="f685a-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="f685a-111">La définition d’un itinéraire permanent n’entraîne pas l’ordinateur à devenir un routeur.</span><span class="sxs-lookup"><span data-stu-id="f685a-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="f685a-112">Si le transfert IP n’est pas activé, l’ordinateur agit uniquement pour diriger le trafic spécifique destiné à un autre réseau vers l’interface appropriée.</span><span class="sxs-lookup"><span data-stu-id="f685a-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="f685a-113">Il s’agit essentiellement de définir deux passerelles, une comme valeur par défaut pointant vers les réseaux externes, une pour le trafic destiné à l’interface interne et sur un routeur ou un autre réseau.</span><span class="sxs-lookup"><span data-stu-id="f685a-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="f685a-p102">Toutefois, la création d’itinéraires permanents pour tous les sous-réseaux peut ne pas être nécessaire si les routeurs de votre réseau sont configurés de manière à résumer les itinéraires. Créez un itinéraire permanent au réseau où le routeur est défini et utilisez le routeur comme passerelle par défaut. Si vous n’êtes pas sûr du mode de configuration de votre réseau et que vous avez besoin d’aide concernant les itinéraires permanents à créer, contactez les ingénieurs réseau de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="f685a-p102">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes. Create a persistent route to the network where the router is defined and use the router as the default gateway. If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="f685a-117">Le proxy inverse doit être en mesure de résoudre les enregistrements d’hôte DNS (A) pour le serveur frontal ou le serveur frontal et les noms de domaine complets (FQDN) du pool du tronçon suivant utilisés dans les règles de publication Web.</span><span class="sxs-lookup"><span data-stu-id="f685a-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="f685a-118">Comme pour les serveurs Edge, pour des raisons de sécurité, nous vous recommandons de ne pas configurer un proxy inverse pour utiliser un serveur DNS situé sur le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="f685a-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="f685a-119">Cela signifie que vous devez utiliser soit des serveurs DNS dans le périmètre, soit des entrées de fichier HOSTS sur le proxy inverse qui résout chacun de ces noms de domaine complets en adresse IP interne des serveurs.</span><span class="sxs-lookup"><span data-stu-id="f685a-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="f685a-120">Pour configurer les cartes réseau sur l’ordinateur de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="f685a-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="f685a-121">Sur le serveur Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 s’exécutant en tant que proxy inverse, ouvrez **modifier les paramètres** de la carte en cliquant sur **Démarrer**, en pointant sur panneau de **configuration**, en cliquant sur **Centre réseau et partage**, puis en cliquant sur **modifier les paramètres**de la carte.</span><span class="sxs-lookup"><span data-stu-id="f685a-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="f685a-122">Cliquez avec le bouton droit sur la connexion réseau externe que vous souhaitez utiliser pour l’interface externe, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f685a-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="f685a-123">Dans la page **Propriétés**, cliquez sur l’onglet **Réseau**, cliquez sur **Protocole Internet version 4 (TCP/IPv4)** dans la liste **Cette connexion utilise les éléments suivants**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f685a-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="f685a-124">Dans la page **Propriétés du protocole Internet (TCP/IP)**, configurez les adresses IP comme il convient pour le sous-réseau auquel la carte réseau est associée.</span><span class="sxs-lookup"><span data-stu-id="f685a-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f685a-125">Si le proxy inverse est déjà utilisé par d’autres applications qui utilisent le protocole HTTPs/TCP/443, par exemple, pour la publication d’Outlook Web Access, vous devez ajouter une autre adresse IP afin de pouvoir publier les services Web Lync Server 2013 sur HTTPs/TCP/443 sans interférer avec les règles et les écouteurs Web existants, ou vous devez remplacer le certificat existant par un certificat qui ajoute les nouveaux noms de noms de domaine complets externes à l’autre nom de l’objet.</span><span class="sxs-lookup"><span data-stu-id="f685a-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="f685a-126">Cliquez sur **OK**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f685a-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="f685a-127">Dans **Connexions réseau**, cliquez avec le bouton droit sur la connexion réseau interne que vous souhaitez utiliser pour l’interface interne, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f685a-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="f685a-128">Répétez les étapes 3 à 5 pour configurer la connexion au réseau interne.</span><span class="sxs-lookup"><span data-stu-id="f685a-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

