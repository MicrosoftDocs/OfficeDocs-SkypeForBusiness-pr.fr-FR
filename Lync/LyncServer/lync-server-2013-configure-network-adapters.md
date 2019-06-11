---
title: 'Lync Server 2013 : Configuration des cartes réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3469e9d5fa3f7aeb45bc8f35ff692d97d09b8481
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="f11ae-102">Configuration des cartes réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f11ae-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f11ae-103">_**Dernière modification de la rubrique:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f11ae-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f11ae-104">Vous devez assigner une ou plusieurs adresses IP à la carte réseau externe et au moins une adresse IP à la carte réseau interne.</span><span class="sxs-lookup"><span data-stu-id="f11ae-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="f11ae-105">Dans les procédures suivantes, le serveur qui exécute le routage de demandes d’applications de la passerelle de gestion des menaces (TMG) 2010 ou de l’application Internet Information Server est doté de deux cartes réseau:</span><span class="sxs-lookup"><span data-stu-id="f11ae-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="f11ae-106">Une carte réseau publique ou externe, qui permet aux clients qui essaient de se connecter à votre site Web (généralement sur Internet).</span><span class="sxs-lookup"><span data-stu-id="f11ae-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="f11ae-107">Une interface réseau privée, ou interne, pour les serveurs internes exécutant Lync Server hébergeant des services Web.</span><span class="sxs-lookup"><span data-stu-id="f11ae-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f11ae-108">Comme pour les serveurs Edge, vous définissez la passerelle par défaut sur la carte réseau externe uniquement.</span><span class="sxs-lookup"><span data-stu-id="f11ae-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="f11ae-109">La passerelle par défaut est l’adresse IP du routeur ou du pare-feu externe qui dirige le trafic vers Internet.</span><span class="sxs-lookup"><span data-stu-id="f11ae-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="f11ae-110">Pour le trafic qui provient du proxy inverse vers la carte réseau interne, vous devez utiliser des itinéraires statiques persistants (tels que la commande itinéraire dans Windows Server) pour tous les sous-réseaux contenant des serveurs référencés par les règles de publication Web.</span><span class="sxs-lookup"><span data-stu-id="f11ae-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="f11ae-111">La définition d’un itinéraire permanent n’entraîne pas la mise en route de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f11ae-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="f11ae-112">Si la fonction de transfert IP n’est pas activée, l’ordinateur ne peut agir que pour diriger le trafic spécifique destiné à un autre réseau vers l’interface appropriée.</span><span class="sxs-lookup"><span data-stu-id="f11ae-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="f11ae-113">Il s’agit essentiellement de définir deux passerelles, une comme la connexion par défaut aux réseaux externes, une pour le trafic destiné à l’interface interne et sur un routeur ou un autre réseau.</span><span class="sxs-lookup"><span data-stu-id="f11ae-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="f11ae-114">Toutefois, la création d’itinéraires permanents pour tous les sous-réseaux peut ne pas être nécessaire si les routeurs de votre réseau sont configurés pour résumer les itinéraires.</span><span class="sxs-lookup"><span data-stu-id="f11ae-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="f11ae-115">Créez un itinéraire permanent vers le réseau où le routeur est défini, puis utilisez le routeur comme passerelle par défaut.</span><span class="sxs-lookup"><span data-stu-id="f11ae-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="f11ae-116">Si vous n’êtes pas sûr de la configuration de votre réseau et que vous avez besoin d’aide pour savoir quels itinéraires persistants doivent être créés, contactez les ingénieurs réseau de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="f11ae-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="f11ae-117">Le proxy inverse doit être en mesure de résoudre les enregistrements d’hôte DNS (A) pour le directeur interne, le serveur frontal, et le FQDN du pool de sauts suivants utilisés dans les règles de publication Web.</span><span class="sxs-lookup"><span data-stu-id="f11ae-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="f11ae-118">Comme pour des raisons de sécurité, il est recommandé de ne pas configurer un proxy inverse pour utiliser un serveur DNS situé dans le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="f11ae-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="f11ae-119">Cela signifie que vous avez besoin de serveurs DNS dans le périmètre ou que vous avez besoin d’entrées de fichier HOSTs sur le proxy inverse qui résout chacun de ces noms de domaine complets à l’adresse IP interne des serveurs.</span><span class="sxs-lookup"><span data-stu-id="f11ae-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="f11ae-120">Pour configurer les cartes réseau sur l’ordinateur proxy inverse</span><span class="sxs-lookup"><span data-stu-id="f11ae-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="f11ae-121">Sur Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 Server en tant que proxy inverse, ouvrez modifier les **paramètres** de la carte en cliquant sur **Démarrer**, pointez sur **panneau**de configuration, cliquez sur **réseau. et le centre de partage**, puis en cliquant sur **modifier les paramètres**de la carte.</span><span class="sxs-lookup"><span data-stu-id="f11ae-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="f11ae-122">Cliquez avec le bouton droit sur la connexion réseau externe que vous souhaitez utiliser pour l’interface externe, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f11ae-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="f11ae-123">Dans la page **Propriétés** , cliquez sur l’onglet **mise en réseau** , cliquez sur **protocole Internet version 4 (TCP/IPv4)** dans la liste **cette connexion utilise les éléments suivants** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f11ae-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="f11ae-124">Dans la page de **Propriétés du protocole Internet (TCP/IP)** , configurez les adresses IP en fonction du réseau de sous-réseau auquel la carte réseau est attachée.</span><span class="sxs-lookup"><span data-stu-id="f11ae-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f11ae-125">Si le proxy inverse est déjà utilisé par d’autres applications qui utilisent HTTPs/TCP/443 (par exemple, pour la publication d’Outlook Web Access), vous devez ajouter une autre adresse IP pour pouvoir publier les services Web 2013 Lync Server sur HTTPs/TCP/443 sans interférer à l’aide des règles et des écouteurs Web existants, ou si vous avez besoin de remplacer le certificat existant par un certificat qui ajoute les nouveaux noms de domaine complets sur le nom de l’autre objet.</span><span class="sxs-lookup"><span data-stu-id="f11ae-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="f11ae-126">Cliquez sur **OK**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f11ae-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="f11ae-127">Dans **connexions réseau**, cliquez avec le bouton droit sur la connexion réseau interne que vous souhaitez utiliser pour l’interface interne, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f11ae-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="f11ae-128">Répétez les étapes 3 à 5 pour configurer la connexion réseau interne.</span><span class="sxs-lookup"><span data-stu-id="f11ae-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

