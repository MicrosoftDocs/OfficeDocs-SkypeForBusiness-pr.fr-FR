---
title: 'Lync Server 2013 : définition de votre topologie Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceba1f397493ac0ef6961099877643f802c11d93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504561"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="30255-102">Définition de votre topologie Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30255-102">Define your edge topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30255-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="30255-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="30255-104">Vous devez utiliser le générateur de topologie pour créer votre topologie et vous devez configurer au moins un pool frontal interne ou un serveur Standard Edition Server avant de déployer votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="30255-105">Utilisez la procédure suivante pour définir la topologie Edge pour un serveur Edge unique, puis utilisez les procédures de la page [publier votre topologie dans Lync server 2013](lync-server-2013-publish-your-topology.md) et [exporter votre topologie Lync Server 2013, puis copiez-la dans le support externe pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) pour publier la topologie et la mettre à la disposition de votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30255-p102">Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="30255-108">Pour réussir à publier, activer ou désactiver une topologie lorsque vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="30255-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="30255-109">Il est également possible de déléguer les droits et autorisations d’administrateur appropriés pour ajouter des rôles serveur à un compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="30255-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="30255-110">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement du serveur Standard Edition Server ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="30255-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="30255-111">Pour toutes les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.</span><span class="sxs-lookup"><span data-stu-id="30255-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="30255-112">Si vous avez défini votre topologie de serveur Edge lorsque vous avez défini et publié votre topologie interne et qu’aucune modification n’est requise pour la topologie Edge que vous avez définie précédemment, vous n’avez pas besoin de la définir et de la publier à nouveau.</span><span class="sxs-lookup"><span data-stu-id="30255-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="30255-113">Utilisez la procédure suivante uniquement si vous devez modifier votre topologie Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="30255-114">Vous devez définir la topologie précédemment définie et publiée comme étant disponible pour vos serveurs Edge, comme vous le faites à l’aide de la procédure décrite dans [Export Your Lync Server 2013 Topology et copy it to External Media for Edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="30255-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="30255-115">Vous ne pouvez pas exécuter le générateur de topologie à partir d’un serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="30255-116">Vous devez l’exécuter à partir de votre serveur frontal ou de vos serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="30255-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="30255-117">Le processus de définition de la topologie de serveur Edge s’effectuera dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="30255-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="30255-118">Les trois principaux types de topologies de serveurs Edge que vous pouvez planifier et configurer sont répertoriés ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="30255-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="30255-119">Pour définir la topologie pour un serveur Edge unique</span><span class="sxs-lookup"><span data-stu-id="30255-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="30255-120">Pour définir la topologie pour un pool de serveurs Edge à charge équilibrée</span><span class="sxs-lookup"><span data-stu-id="30255-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="30255-121">Pour définir la topologie pour un pool de serveurs Edge à charge matérielle équilibrée</span><span class="sxs-lookup"><span data-stu-id="30255-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="30255-122">Pour définir la topologie pour un serveur Edge unique</span><span class="sxs-lookup"><span data-stu-id="30255-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="30255-123">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="30255-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="30255-124">Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer un serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="30255-125">Cliquez avec le bouton droit sur **Pools**de serveurs Edge, puis cliquez sur **nouveau pool**de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="30255-126">Dans **Définir le nouveau pool Edge**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="30255-127">Dans **Définir le nom de domaine complet du pool Edge**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="30255-128">Dans **Nom de domaine complet du pool**, tapez le nom de domaine complet (FQDN) de l’interface interne pour le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="30255-129">Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="30255-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="30255-130">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, pas un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="30255-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="30255-131">Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts.</span><span class="sxs-lookup"><span data-stu-id="30255-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="30255-132">Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine.</span><span class="sxs-lookup"><span data-stu-id="30255-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="30255-133">Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools.</span><span class="sxs-lookup"><span data-stu-id="30255-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="30255-134">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="30255-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="30255-135">Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat).</span><span class="sxs-lookup"><span data-stu-id="30255-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="30255-136">Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir <A href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="30255-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="30255-137">Cliquez sur **Pool d’un seul ordinateur**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="30255-138">Dans **Sélectionner les fonctionnalités**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="30255-139">Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour le service d’accès SIP, le service de conférence Web Lync Server 2013 et les services Edge A/V, activez la case à cocher **utiliser un seul nom de domaine complet et une seule adresse IP** .</span><span class="sxs-lookup"><span data-stu-id="30255-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="30255-140">Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="30255-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-p108">Vous pouvez activer cette option, mais un seul pool de serveurs Edge ou serveur Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="30255-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="30255-145">Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**</span><span class="sxs-lookup"><span data-stu-id="30255-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="30255-146">Dans **Sélectionner les options IP**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="30255-147">**Activer IPv4 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="30255-148">**Activer IPv6 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="30255-149">**Activer IPv4 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="30255-150">**Activer IPv6 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="30255-151">Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="30255-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="30255-152">Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est traduite par NAT**.</span><span class="sxs-lookup"><span data-stu-id="30255-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="30255-153">Dans **Noms de domaine complets externes**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="30255-154">Si dans **Sélectionner les fonctionnalités** vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="30255-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-p110">Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple 443) pour les trois services.</span><span class="sxs-lookup"><span data-stu-id="30255-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="30255-157">Si dans **Sélectionner les fonctionnalités** vous n’avez pas choisi d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez les noms de domaine complets pour les services **Accès SIP**, **Conférence web** et **Audio Vidéo**, en conservant les ports par défaut.</span><span class="sxs-lookup"><span data-stu-id="30255-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="30255-158">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-158">Click **Next**.</span></span>

10. <span data-ttu-id="30255-p111">Dans **Définir l’adresse IP interne**, tapez l’adresse IP de votre serveur Edge dans **Adresse IPv4 interne** et **Adresse IPv6 interne** selon votre configuration. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="30255-161">Dans **Définir l’adresse IP externe**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="30255-162">Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv4 externe du serveur Edge dans **Accès SIP**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="30255-163">Si vous avez choisi d’utiliser des adresses IPv6, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="30255-164">Si vous n’avez pas choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez les adresses IPv4 externes du serveur Edge dans **Accès SIP**, **Conférence web** et **Conférence A/V**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="30255-165">Si vous avez choisi d’utiliser des adresses IPv6 et de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez les adresses IPv6 externes du serveur Edge dans **Accès SIP**, **Conférence web** et **Conférence A/V**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-166">Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="30255-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="30255-p112">Si vous avez choisi d’utiliser la traduction d’adresses réseau (NAT), une boîte de dialogue s’affiche. Dans **Adresse IPv4 publique pour le service Edge A/V**, tapez l’adresse IPv4 publique à traduire par NAT, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-169">Il doit s’agir de l’adresse IP externe du service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="30255-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="30255-p113">Si vous avez choisi d’utiliser la traduction d’adresses réseau (NAT) et des adresses IPv6, une boîte de dialogue s’affiche. Dans **Adresse IPv6 publique pour le service Edge A/V**, tapez l’adresse IPv6 publique à traduire par NAT, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-172">Il doit s’agir de l’adresse IP externe du service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="30255-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="30255-p114">Dans **Définir le tronçon suivant**, dans la zone **Pool du tronçon suivant**, sélectionnez le nom du pool interne qui peut être soit un pool frontal, soit un pool de serveurs Standard Edition. Ou, si votre déploiement inclut un directeur, sélectionnez-le, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="30255-176">Dans **Pools frontaux associés**, spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition Server, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.</span><span class="sxs-lookup"><span data-stu-id="30255-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-p115">Un seul pool de serveurs Edge avec charge équilibrée ou serveur Edge unique peut être associé à chaque pool interne pour le trafic A/V. Si vous avez déjà un pool interne associé à un pool de serveurs Edge ou à un serveur Edge unique, un avertissement apparaît vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge unique. Si vous sélectionnez un pool qui est déjà associé à un autre serveur Edge, cela modifiera l’association.</span><span class="sxs-lookup"><span data-stu-id="30255-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="30255-180">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="30255-180">Click **Finish**.</span></span>

17. <span data-ttu-id="30255-181">Publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="30255-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="30255-182">Pour définir la topologie pour un pool de serveurs Edge avec charge DNS équilibrée</span><span class="sxs-lookup"><span data-stu-id="30255-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="30255-183">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="30255-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="30255-184">Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="30255-185">Cliquez avec le bouton droit sur **Pools de serveurs Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="30255-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="30255-186">Dans **Définir le nouveau pool Edge**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="30255-187">Dans **Définir le nom de domaine complet du pool Edge**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="30255-188">Dans **Nom de domaine complet du pool**, tapez le nom de domaine complet (FQDN) pour la connexion interne du pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="30255-189">Le nom de pool que vous indiquez doit être identique au nom du pool Edge interne.</span><span class="sxs-lookup"><span data-stu-id="30255-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="30255-190">Il doit être défini comme nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="30255-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="30255-191">Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts.</span><span class="sxs-lookup"><span data-stu-id="30255-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="30255-192">Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools.</span><span class="sxs-lookup"><span data-stu-id="30255-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="30255-193">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="30255-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="30255-194">Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom de sujet) du certificat).</span><span class="sxs-lookup"><span data-stu-id="30255-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="30255-195">Cliquez sur **Pool de plusieurs ordinateurs**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="30255-196">Dans **Sélectionner les fonctionnalités**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="30255-197">Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence Web Lync Server 2013 et les services Edge A/V, activez la case à cocher **utiliser un seul nom de domaine complet et une seule adresse IP** .</span><span class="sxs-lookup"><span data-stu-id="30255-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="30255-p117">Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Cliquez sur **Suivant**</span><span class="sxs-lookup"><span data-stu-id="30255-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-p118">Vous pouvez activer cette option, mais un seul pool de serveurs Edge ou serveur Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="30255-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="30255-204">Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**</span><span class="sxs-lookup"><span data-stu-id="30255-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="30255-205">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-205">Click **Next**.</span></span>

8.  <span data-ttu-id="30255-206">Dans **Sélectionner les options IP**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="30255-207">**Activer IPv4 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="30255-208">**Activer IPv6 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="30255-209">**Activer IPv4 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="30255-210">**Activer IPv6 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="30255-211">Vous pouvez également configurer le serveur Edge ou le pool de serveurs Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="30255-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="30255-212">Pour ce faire, activez la case à cocher **L’adresse IP externe de ce pool Edge est traduite par NAT**.</span><span class="sxs-lookup"><span data-stu-id="30255-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="30255-213">Dans **Noms de domaine complets externes**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="30255-214">Si, dans **Sélectionner les fonctionnalités**, vous avez choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="30255-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-p120">Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple 443) pour les trois services.</span><span class="sxs-lookup"><span data-stu-id="30255-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="30255-p121">Si, dans **Sélectionner les fonctionnalités**, vous n’avez pas décidé d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Dans **Audio/Vidéo**, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Utilisez les ports par défaut.</span><span class="sxs-lookup"><span data-stu-id="30255-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="30255-221">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-221">Click **Next**.</span></span>

11. <span data-ttu-id="30255-222">Dans **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="30255-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="30255-223">Dans **FQDN et adresse IP internes**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="30255-224">Dans **Adresse IPv4 interne**, tapez l’adresse IPv4 et l’**Adresse IPv6 interne** selon les besoins du premier serveur Edge à créer dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="30255-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="30255-225">Dans **Nom de domaine complet (FQDN) interne**, tapez le nom de domaine complet du premier serveur Edge que vous souhaitez créer dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="30255-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-226">Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="30255-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="30255-227">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, non un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="30255-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="30255-228">Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts.</span><span class="sxs-lookup"><span data-stu-id="30255-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="30255-229">Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine.</span><span class="sxs-lookup"><span data-stu-id="30255-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="30255-230">Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge, pools et tableaux.</span><span class="sxs-lookup"><span data-stu-id="30255-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="30255-231">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="30255-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="30255-232">Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat).</span><span class="sxs-lookup"><span data-stu-id="30255-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="30255-233">Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir <A href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="30255-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="30255-234">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-234">Click **Next**.</span></span>

14. <span data-ttu-id="30255-235">Dans **Définir les adresses IP externes**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="30255-236">Si vous décidez d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IP externe du serveur Edge dans **Accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="30255-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="30255-p123">Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V**, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="30255-240">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-240">Click **Next**.</span></span>

16. <span data-ttu-id="30255-241">Si vous avez activé l’utilisation des adresses IPv6, dans **Définir l’adresse IP externe**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="30255-242">Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="30255-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="30255-p124">Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V**, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-246">Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="30255-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="30255-247">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="30255-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-248">Le premier serveur Edge créé dans votre pool apparaît maintenant dans la boîte de dialogue <STRONG>Définissez les ordinateurs inclus dans ce pool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="30255-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="30255-249">Dans **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Ajouter**, puis répétez les étapes 11 à 14 pour le deuxième serveur Edge à ajouter à votre pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="30255-250">Après avoir exécuté les étapes 11 à 14, cliquez sur **Suivant** dans **Définissez les ordinateurs inclus dans ce pool**.</span><span class="sxs-lookup"><span data-stu-id="30255-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-251">À ce stade, les deux serveurs Edge sont visibles dans le pool.</span><span class="sxs-lookup"><span data-stu-id="30255-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="30255-p125">Si vous avez choisi d’utiliser la traduction d’adresses réseau (NAT), une boîte de dialogue s’affiche. Dans **Adresse IP publique**, tapez les adresses IPv4 et IPv6 (le cas échéant) publiques à traduire par NAT, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-254">Il doit s’agir de l’adresse IP externe du service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="30255-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="30255-p126">Dans **Définir le tronçon suivant**, dans la liste **Pool du tronçon suivant**, sélectionnez le nom du pool interne qui peut être soit un pool de serveurs frontaux, soit un pool de serveurs Standard Edition Server. Ou, si votre déploiement inclut un directeur, sélectionnez son nom. Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="30255-258">Dans **Pools frontaux associés**, spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition Server, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.</span><span class="sxs-lookup"><span data-stu-id="30255-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-p127">Un seul pool de serveurs Edge avec charge équilibrée ou serveur Edge unique peut être associé à chaque pool interne pour le trafic A/V. Si vous avez déjà un pool interne associé à un pool de serveurs Edge ou à un serveur Edge unique, un avertissement apparaît vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge unique. Si vous sélectionnez un pool qui est déjà associé à un autre serveur Edge, cela modifiera l’association.</span><span class="sxs-lookup"><span data-stu-id="30255-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="30255-262">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="30255-262">Click **Finish**.</span></span>

24. <span data-ttu-id="30255-263">Publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="30255-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="30255-264">Pour définir la topologie pour un pool de serveurs Edge à charge matérielle équilibrée</span><span class="sxs-lookup"><span data-stu-id="30255-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="30255-265">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="30255-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="30255-266">Dans l’arborescence de la console, développez le site dans lequel vous souhaitez déployer les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="30255-267">Cliquez avec le bouton droit sur **Pools**de serveurs Edge, puis sélectionnez **nouveau pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="30255-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="30255-268">Dans **Définir le nouveau pool Edge**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="30255-269">Dans **Définir le nom de domaine complet du pool Edge**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="30255-270">Dans **Nom de domaine complet**, tapez le nom de domaine complet (FQDN) de l’interface interne pour le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="30255-271">Le nom de pool que vous indiquez doit être identique au nom du pool Edge interne.</span><span class="sxs-lookup"><span data-stu-id="30255-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="30255-272">Il doit être défini comme nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="30255-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="30255-273">Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts.</span><span class="sxs-lookup"><span data-stu-id="30255-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="30255-274">Utilisez uniquement des caractères standard (A à Z, a à z, 0 à 9 et tirets) lorsque vous affectez des noms de domaine complets à vos serveurs Lync, serveurs Edge et pools.</span><span class="sxs-lookup"><span data-stu-id="30255-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="30255-275">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="30255-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="30255-276">Les caractères non standard dans les noms de domaine complets ne sont souvent pas pris en charge par les DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté à l’élément SN (nom du sujet) du certificat).</span><span class="sxs-lookup"><span data-stu-id="30255-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="30255-277">Cliquez sur **pool de plusieurs ordinateurs**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="30255-278">Dans **Sélectionner les fonctionnalités**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="30255-279">Si vous envisagez d’utiliser un seul nom de domaine complet et une seule adresse IP pour le service d’accès SIP, le service de conférence Web Lync Server et le service Edge A/V, activez la case à cocher **utiliser un seul nom de domaine complet & adresse IP** .</span><span class="sxs-lookup"><span data-stu-id="30255-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="30255-280">Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="30255-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-p129">Vous pouvez activer cette option, mais un seul pool Edge ou serveur Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York, et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="30255-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="30255-285">Si vous envisagez de prendre en charge le protocole XMPP (Extensible Messaging and Presence Protocol) pour votre déploiement, activez la case à cocher **Activer la fédération XMPP (port 5269)**</span><span class="sxs-lookup"><span data-stu-id="30255-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="30255-286">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-286">Click **Next**.</span></span>

8.  <span data-ttu-id="30255-287">Dans **Sélectionner les options IP**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="30255-288">**Activer IPv4 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="30255-289">**Activer IPv6 sur l’interface interne**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="30255-290">**Activer IPv4 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="30255-291">**Activer IPv6 sur l’interface externe**: activez cette case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="30255-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="30255-p130"><STRONG>N’activez pas</STRONG> la case à cocher <STRONG>L’adresse IP externe de ce pool de serveurs Edge est traduite par NAT</STRONG>. La traduction d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="30255-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="30255-294">Dans **Noms de domaine complets externes**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="30255-295">Si, dans **Sélectionner les fonctionnalités**, vous avez choisi d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez le nom de domaine complet externe dans **Accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="30255-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-p131">Si vous décidez d’activer cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés : 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence web et 443 pour le service Edge A/V). L’activation de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez alors utiliser le même numéro de port (par exemple 443) pour les trois services.</span><span class="sxs-lookup"><span data-stu-id="30255-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="30255-p132">Si, dans **Sélectionner les fonctionnalités**, vous n’avez pas décidé d’utiliser un seul nom de domaine complet et une seule adresse IP, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Dans **Audio/Vidéo**, tapez le nom de domaine complet que vous avez choisi pour le côté accessible au public du pool de serveurs Edge. Utilisez les ports par défaut.</span><span class="sxs-lookup"><span data-stu-id="30255-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30255-302">Il serviront de noms de domaine complets des adresses IP virtuelles (VIP) accessibles au public.</span><span class="sxs-lookup"><span data-stu-id="30255-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="30255-303">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-303">Click **Next**.</span></span>

11. <span data-ttu-id="30255-304">Dans **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="30255-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="30255-305">Dans **Définir les adresses IP externes**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="30255-306">Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv4 externe du serveur Edge dans **Accès\*\*\*\*SIP**.</span><span class="sxs-lookup"><span data-stu-id="30255-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="30255-p133">Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V**, tapez l’adresse IP que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="30255-310">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-310">Click **Next**.</span></span>

14. <span data-ttu-id="30255-311">Si vous avez activé l’utilisation des adresses IPv6, dans **Définir l’adresse IP externe**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30255-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="30255-312">Si vous avez décidé d’utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans **Accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="30255-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="30255-p134">Si vous avez décidé de ne pas utiliser un seul nom de domaine complet et une seule adresse IP pour l’accès SIP, le service de conférence web et le service de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge dans **Accès SIP**. Dans **Conférence web**, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge. Dans **Conférence A/V**, tapez l’adresse IPv6 que vous avez choisie pour le côté accessible au public de ce serveur du pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-316">Si vous n’avez pas activé l’utilisation d’adresses IPv6, cette boîte de dialogue ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="30255-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="30255-317">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="30255-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-318">Le premier serveur Edge créé dans votre pool apparaît maintenant dans la boîte de dialogue <STRONG>Définissez les ordinateurs inclus dans ce pool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="30255-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="30255-319">Dans **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Ajouter**, puis répétez les étapes 11 à 14 pour le deuxième serveur Edge que vous souhaitez ajouter à votre pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="30255-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="30255-320">Après avoir exécuté les étapes 11 à 14, cliquez sur **Suivant** dans **Définissez les ordinateurs inclus dans ce pool**.</span><span class="sxs-lookup"><span data-stu-id="30255-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-321">À ce stade, les deux serveurs Edge sont visibles dans le pool.</span><span class="sxs-lookup"><span data-stu-id="30255-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="30255-p135">Dans **Définir le tronçon suivant**, dans la liste **Pool du tronçon suivant**, sélectionnez le nom du pool interne qui peut être soit un pool de serveurs frontaux, soit un pool de serveurs Standard Edition Server. Ou, si votre déploiement inclut un directeur, sélectionnez son nom. Cliquez ensuite sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="30255-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="30255-325">Dans **Pools frontaux associés**, spécifiez un ou plusieurs pools internes à associer à ce serveur Edge, notamment des pools frontaux et des serveurs Standard Edition Server, en sélectionnant les noms des pools internes qui utiliseront ce serveur Edge pour communiquer avec les utilisateurs externes pris en charge.</span><span class="sxs-lookup"><span data-stu-id="30255-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30255-p136">Un seul pool de serveurs Edge avec charge équilibrée ou serveur Edge unique peut être associé à chaque pool interne pour le trafic A/V. Si vous avez déjà un pool interne associé à un pool de serveurs Edge ou à un serveur Edge unique, un avertissement apparaît vous indiquant que le pool interne est déjà associé à un pool de serveurs Edge ou à un serveur Edge unique. Si vous sélectionnez un pool qui est déjà associé à un autre serveur Edge, cela modifiera l’association.</span><span class="sxs-lookup"><span data-stu-id="30255-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="30255-329">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="30255-329">Click **Finish**.</span></span>

21. <span data-ttu-id="30255-330">Publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="30255-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

