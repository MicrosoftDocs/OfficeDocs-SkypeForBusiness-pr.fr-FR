---
title: 'Lync Server 2013 : Définition de la topologie Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8364d2167b719e020ecebc3808c2ca850d14bc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="86edc-102">Définition de la topologie Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86edc-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86edc-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="86edc-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="86edc-104">Vous devez utiliser le générateur de topologie pour générer votre topologie et définir au moins un pool interne ou un serveur Standard Edition avant de pouvoir déployer votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="86edc-105">Utilisez la procédure suivante pour définir la topologie de bord d’un serveur Edge unique, puis utilisez les procédures décrites dans la rubriques [publier votre topologie dans Lync server 2013](lync-server-2013-publish-your-topology.md) et [exporter votre topologie Lync Server 2013 et copier celle-ci sur des éléments multimédias externes pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) . pour publier la topologie et la rendre accessible à votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86edc-106">L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge.</span><span class="sxs-lookup"><span data-stu-id="86edc-106">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="86edc-107">Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-107">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="86edc-108">Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine.</span><span class="sxs-lookup"><span data-stu-id="86edc-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="86edc-109">Vous pouvez également accorder des droits d’administrateur et des autorisations nécessaires pour ajouter des rôles de serveur à un compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="86edc-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="86edc-110">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement Standard Edition Server ou Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="86edc-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="86edc-111">Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.</span><span class="sxs-lookup"><span data-stu-id="86edc-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="86edc-112">Si vous avez défini votre topologie de bord lorsque vous avez défini et publié votre topologie interne, et qu’aucune modification n’est requise pour la topologie de bord que vous avez précédemment définie, vous n’avez pas besoin de la définir et de la republier.</span><span class="sxs-lookup"><span data-stu-id="86edc-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="86edc-113">Utilisez la procédure suivante uniquement si vous avez besoin d’apporter des modifications à votre topologie latérale.</span><span class="sxs-lookup"><span data-stu-id="86edc-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="86edc-114">Vous devez rendre la topologie précédemment définie et publiée disponible pour vos serveurs Edge, en suivant la procédure décrite dans [exporter votre topologie Lync Server 2013 et la copier vers un média externe pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="86edc-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86edc-115">Vous ne pouvez pas exécuter le générateur de topologie à partir d’un serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="86edc-116">Vous devez l’exécuter à partir de votre serveur frontal ou des serveurs Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="86edc-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="86edc-117">Le processus de définition de la topologie de votre serveur Edge est réalisé dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="86edc-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="86edc-118">Les trois principaux types de topologies de serveur Edge que vous planifiez et configurez sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="86edc-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="86edc-119">Pour définir la topologie pour un serveur Edge unique</span><span class="sxs-lookup"><span data-stu-id="86edc-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="86edc-120">Pour définir la topologie d’un pool de serveurs Edge équilibré</span><span class="sxs-lookup"><span data-stu-id="86edc-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="86edc-121">Pour définir la topologie d’un pool de périphériques équilibrés de charge matérielle</span><span class="sxs-lookup"><span data-stu-id="86edc-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="86edc-122">Pour définir la topologie pour un serveur Edge unique</span><span class="sxs-lookup"><span data-stu-id="86edc-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="86edc-123">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86edc-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="86edc-124">Dans l’arborescence de la console, développez le site dans lequel vous voulez déployer un serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="86edc-125">Cliquez avec le bouton droit sur pools de **bords**, puis cliquez sur **nouvelle réserve de périphérie**.</span><span class="sxs-lookup"><span data-stu-id="86edc-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="86edc-126">Dans **définir le nouveau pool**de bordures, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="86edc-127">Dans **définir le nom de domaine complet (FQDN) du pool Edge**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-128">Dans **nom**de domaine complet (FQDN) du pool, tapez le nom de domaine complet (FQDN) de l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="86edc-129">Le nom spécifié doit être identique au nom de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="86edc-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="86edc-130">Par défaut, le nom de l’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom court qui n’est pas un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="86edc-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="86edc-131">Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts.</span><span class="sxs-lookup"><span data-stu-id="86edc-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="86edc-132">Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine.</span><span class="sxs-lookup"><span data-stu-id="86edc-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="86edc-133">Utilisez uniquement les caractères standard (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools.</span><span class="sxs-lookup"><span data-stu-id="86edc-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="86edc-134">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="86edc-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="86edc-135">Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le FQDN doit être attribué à l’SN dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="86edc-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="86edc-136">Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir <A href="lync-server-2013-configure-dns-for-edge-support.md">configurer la prise en charge de DNS pour les bords dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="86edc-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="86edc-137">Cliquez sur **pool d’ordinateurs unique**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="86edc-138">Dans **Sélectionner les fonctionnalités**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-139">Si vous envisagez d’utiliser un nom de domaine complet et une adresse IP uniques pour le service d’accès SIP, le service de conférence Web de Lync Server 2013 et les services Edge A/V, activez la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** .</span><span class="sxs-lookup"><span data-stu-id="86edc-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="86edc-140">Si vous envisagez d’activer la Fédération, activez la case à cocher **activer la Fédération pour ce pool Edge (Port 5061)** .</span><span class="sxs-lookup"><span data-stu-id="86edc-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-141">Vous pouvez sélectionner cette option, mais un seul pool de périphériques ou serveur de périphérie de votre organisation peut être publié en externe pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="86edc-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="86edc-142">Tout accès par des utilisateurs fédérés, y compris des utilisateurs de la messagerie instantanée publique, passe par le même pool de périphérie ou serveur à périphérie unique.</span><span class="sxs-lookup"><span data-stu-id="86edc-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="86edc-143">Par exemple, si votre déploiement inclut un pool de périphérie ou un serveur Edge unique déployé à New York et un serveur déployé à Londres et que vous activez la prise en charge de la Fédération sur le pool de périphériques de la Nouvelle-York ou sur un serveur de périphérie Pool Edge ou serveur Edge unique.</span><span class="sxs-lookup"><span data-stu-id="86edc-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="86edc-144">Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="86edc-145">Si vous envisagez de prendre en charge le protocole de messagerie et de présence extensible (XMPP) pour votre déploiement, activez la case à cocher **activer la Fédération XMPP (port 5269)** .</span><span class="sxs-lookup"><span data-stu-id="86edc-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="86edc-146">Dans **Sélectionner les options IP**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-147">**Activer IPv4 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="86edc-148">**Activer IPv6 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="86edc-149">**Activer IPv4 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="86edc-150">**Activer IPv6 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="86edc-151">Vous pouvez également configurer le serveur de périphérie ou le pool Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="86edc-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="86edc-152">Pour ce faire, activez la case à cocher **l’adresse IP externe de ce pool Edge est traduite par tar**.</span><span class="sxs-lookup"><span data-stu-id="86edc-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="86edc-153">Dans les noms de **domaine complets externes**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-154">Si vous avez choisi de **Sélectionner les fonctionnalités** que vous avez choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge a/V, tapez le nom de domaine complet dans **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-155">Si vous choisissez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés: 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence Web et 443 pour service Edge A/V).</span><span class="sxs-lookup"><span data-stu-id="86edc-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="86edc-156">La sélection de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez ensuite utiliser le même numéro de port (par exemple, 443) pour les trois services.</span><span class="sxs-lookup"><span data-stu-id="86edc-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="86edc-157">Si vous n’avez pas choisi d’utiliser une adresse de domaine complet et un nom de domaine complet (FQDN) dans **Select** , tapez les noms de domaine complets externes pour l' **accès SIP**, les **conférences Web** et la **vidéo audio**, en conservant les ports par défaut.</span><span class="sxs-lookup"><span data-stu-id="86edc-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="86edc-158">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-158">Click **Next**.</span></span>

10. <span data-ttu-id="86edc-159">Dans **définir l’adresse IP interne**, tapez l’adresse IP de votre serveur Edge dans **adresse IPv4 interne** et **adresse IPv6 interne** , en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="86edc-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="86edc-160">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-160">Click **Next**.</span></span>

11. <span data-ttu-id="86edc-161">Dans **définir l’adresse IP externe**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-162">Si vous choisissez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IPv4 externe du serveur Edge dans **accès SIP**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="86edc-163">Si vous avez choisi d’utiliser les adresses IPv6, tapez l’adresse IPv6 externe du serveur Edge dans **accès SIP**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="86edc-164">Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez les adresses IPv4 externes du serveur Edge dans **accès SIP**, **conférences Web**et **conférences a/v**, puis Cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="86edc-165">Si vous avez choisi d’utiliser les adresses IPv6 et que vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez les adresses IPv6 externes du serveur Edge dans **accès SIP**, **conférences Web**et **a/ V Conferencing**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-166">Si vous n’avez pas choisi d’activer et d’affecter l’adressage IPv6, cette boîte de dialogue ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="86edc-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="86edc-167">Si vous choisissez d’utiliser la traduction d’adresses réseau (NAT), une boîte de dialogue s’affiche.</span><span class="sxs-lookup"><span data-stu-id="86edc-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="86edc-168">Dans **adresse IPv4 publique pour le service Edge A/V**, tapez l’adresse IPv4 publique à traduire par tar, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-169">Il doit s’agir de l’adresse IP externe du service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="86edc-170">Si vous choisissez d’utiliser des adresses NAT et IPv6, une boîte de dialogue s’affiche.</span><span class="sxs-lookup"><span data-stu-id="86edc-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="86edc-171">Dans **adresse IPv6 publique pour le service Edge A/V**, tapez l’adresse IPv6 publique à traduire par tar, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-172">Il doit s’agir de l’adresse IP externe du service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="86edc-173">Dans **définir le saut suivant**, dans le **pool de sauts suivant**, sélectionnez le nom du pool interne, qui peut être un pool frontal ou un pool Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="86edc-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="86edc-174">Si votre déploiement inclut un directeur, sélectionnez le réalisateur.</span><span class="sxs-lookup"><span data-stu-id="86edc-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="86edc-175">Ensuite, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="86edc-176">Dans la zone associer des regroupements **front-end**, spécifiez un ou plusieurs pools internes, qui peuvent inclure des pools frontaux et des serveurs Standard Edition, à associer à ce serveur Edge, en sélectionnant les noms des pools internes pour lesquels utiliser ce serveur Edge. communication avec des utilisateurs externes pris en charge.</span><span class="sxs-lookup"><span data-stu-id="86edc-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-177">Il n’est possible d’associer qu’un seul pool Edge équilibré ou un seul serveur Edge à chaque pool interne pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="86edc-178">Si vous disposez déjà d’un pool interne associé à un serveur Edge ou à un pool de bords, un message d’avertissement s’affiche, indiquant que le pool interne est déjà associé à un serveur Edge ou à un serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="86edc-179">Si vous sélectionnez un pool déjà associé à un autre serveur Edge, l’Association est modifiée.</span><span class="sxs-lookup"><span data-stu-id="86edc-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="86edc-180">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="86edc-180">Click **Finish**.</span></span>

17. <span data-ttu-id="86edc-181">Publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="86edc-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="86edc-182">Pour définir la topologie d’un pool de serveurs Edge équilibré de charge DNS</span><span class="sxs-lookup"><span data-stu-id="86edc-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="86edc-183">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86edc-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="86edc-184">Dans l’arborescence de la console, développez le site dans lequel vous voulez déployer des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="86edc-185">Cliquez avec le bouton droit sur pools de **bords**, puis cliquez sur **nouvelle réserve de périphérie**.</span><span class="sxs-lookup"><span data-stu-id="86edc-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="86edc-186">Dans **définir le nouveau pool**de bordures, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="86edc-187">Dans **définir le nom de domaine complet (FQDN) du pool Edge**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-188">Dans **nom**de domaine complet (FQDN) du pool, tapez le nom de domaine complet (FQDN) de votre connexion interne.</span><span class="sxs-lookup"><span data-stu-id="86edc-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="86edc-189">Le nom que vous spécifiez pour le pool doit correspondre au nom du pool de bords internes.</span><span class="sxs-lookup"><span data-stu-id="86edc-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="86edc-190">Cette opération doit être définie en tant que nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="86edc-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="86edc-191">Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts.</span><span class="sxs-lookup"><span data-stu-id="86edc-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="86edc-192">Utilisez uniquement les caractères standard (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools.</span><span class="sxs-lookup"><span data-stu-id="86edc-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="86edc-193">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="86edc-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="86edc-194">Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le FQDN doit être attribué à l’SN dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="86edc-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="86edc-195">Cliquez sur **plusieurs pools d’ordinateurs**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="86edc-196">Dans **Sélectionner les fonctionnalités**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-197">Si vous envisagez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web Lync Server 2013 et les services Edge A/V, activez la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** .</span><span class="sxs-lookup"><span data-stu-id="86edc-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="86edc-198">Si vous envisagez d’activer la Fédération, activez la case à cocher **activer la Fédération pour ce pool Edge (Port 5061)** .</span><span class="sxs-lookup"><span data-stu-id="86edc-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="86edc-199">Cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="86edc-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-200">Vous pouvez sélectionner cette option, mais un seul pool de périphériques ou serveur de périphérie de votre organisation peut être publié en externe pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="86edc-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="86edc-201">Tout accès par des utilisateurs fédérés, y compris des utilisateurs de la messagerie instantanée publique, passe par le même pool de périphérie ou serveur à périphérie unique.</span><span class="sxs-lookup"><span data-stu-id="86edc-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="86edc-202">Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou sur le serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou par le serveur Edge unique de New York.</span><span class="sxs-lookup"><span data-stu-id="86edc-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="86edc-203">Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="86edc-204">Si vous envisagez de prendre en charge le protocole de messagerie et de présence extensible (XMPP) pour votre déploiement, activez la case à cocher **activer la Fédération XMPP (port 5269)** .</span><span class="sxs-lookup"><span data-stu-id="86edc-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="86edc-205">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-205">Click **Next**.</span></span>

8.  <span data-ttu-id="86edc-206">Dans **Sélectionner les options IP**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-207">**Activer IPv4 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="86edc-208">**Activer IPv6 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="86edc-209">**Activer IPv4 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="86edc-210">**Activer IPv6 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="86edc-211">Vous pouvez également configurer le serveur de périphérie ou le pool Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes.</span><span class="sxs-lookup"><span data-stu-id="86edc-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="86edc-212">Pour ce faire, activez la case à cocher **l’adresse IP externe de ce pool Edge est traduite par tar**.</span><span class="sxs-lookup"><span data-stu-id="86edc-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="86edc-213">Dans les noms de **domaine complets externes**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-214">Si vous avez choisi de **Sélectionner les fonctionnalités** que vous avez choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge a/V, tapez le nom de domaine complet dans **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-215">Si vous choisissez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés: 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence Web et 443 pour service Edge A/V).</span><span class="sxs-lookup"><span data-stu-id="86edc-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="86edc-216">En sélectionnant cette option, vous pouvez éviter les problèmes de connectivité potentiels et simplifier la configuration, car vous pouvez ensuite utiliser le même numéro de port (par exemple, 443) pour les trois services.</span><span class="sxs-lookup"><span data-stu-id="86edc-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="86edc-217">Si vous n’avez pas choisi d’utiliser une adresse de domaine complet et un nom de domaine complet (FQDN) dans **Sélectionner les fonctionnalités** , tapez le nom de domaine complet (FQDN) du pool pour l' **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="86edc-218">Dans **conférences Web**, tapez le nom de domaine complet que vous avez choisi pour le côté public du pool de périphérie.</span><span class="sxs-lookup"><span data-stu-id="86edc-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="86edc-219">Dans **audio/vidéo**, tapez le nom de domaine complet (FQDN) que vous avez choisi pour le côté public du pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="86edc-220">Utiliser les ports par défaut.</span><span class="sxs-lookup"><span data-stu-id="86edc-220">Use the default ports.</span></span>

10. <span data-ttu-id="86edc-221">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-221">Click **Next**.</span></span>

11. <span data-ttu-id="86edc-222">Dans **définir les ordinateurs dans ce pool**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="86edc-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="86edc-223">Dans **FQDN et adresse IP internes**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-224">Dans **adresse IPv4 interne**, tapez l’adresse IPv4 et l' **adresse IPv6 interne** , en fonction de vos besoins pour le premier serveur de périmètre que vous voulez créer dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="86edc-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="86edc-225">Dans **nom de domaine complet (FQDN) interne**, tapez le nom de domaine complet (FQDN) du premier serveur Edge que vous voulez créer dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="86edc-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-226">Le nom de domaine complet spécifié doit être identique au nom de l’ordinateur configuré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="86edc-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="86edc-227">Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="86edc-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="86edc-228">Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts.</span><span class="sxs-lookup"><span data-stu-id="86edc-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="86edc-229">Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine.</span><span class="sxs-lookup"><span data-stu-id="86edc-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="86edc-230">Utilisez uniquement les caractères standard (y compris A – Z, a-z, 0 à 9 et les traits d’Union) lorsque vous attribuez des noms de domaine complets de vos serveurs Lync, serveurs de périphérie, groupes et matrices.</span><span class="sxs-lookup"><span data-stu-id="86edc-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="86edc-231">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="86edc-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="86edc-232">Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le FQDN doit être attribué à l’SN dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="86edc-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="86edc-233">Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir <A href="lync-server-2013-configure-dns-for-edge-support.md">configurer la prise en charge de DNS pour les bords dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="86edc-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="86edc-234">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-234">Click **Next**.</span></span>

14. <span data-ttu-id="86edc-235">Dans **définir les adresses IP externes**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-236">Si vous choisissez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IP externe du serveur Edge dans **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="86edc-237">Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour les services d’accès SIP, de service de conférence Web et de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge pour l' **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="86edc-238">Dans **conférence Web**, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="86edc-239">Dans le cadre de **conférences A/V**, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="86edc-240">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-240">Click **Next**.</span></span>

16. <span data-ttu-id="86edc-241">Si vous choisissez d’activer les adresses IPv6, dans **définir les adresses IP externes**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-242">Si vous choisissez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans l' **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="86edc-243">Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour les services d’accès SIP, de service de conférence Web et de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge pour l' **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="86edc-244">Dans **conférence Web**, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="86edc-245">Dans le cadre de **conférences A/V**, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-246">Si vous n’avez pas choisi d’activer et d’affecter l’adressage IPv6, cette boîte de dialogue ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="86edc-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="86edc-247">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="86edc-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-248">Le premier serveur Edge que vous avez créé dans votre pool apparaît désormais dans la boîte de dialogue <STRONG>définir les ordinateurs dans ce pool</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="86edc-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="86edc-249">Dans **définir les ordinateurs dans ce pool**, cliquez sur **Ajouter**, puis répétez les étapes 11 à 14 pour le deuxième serveur de périmètre que vous voulez ajouter à votre liste de serveurs de bord.</span><span class="sxs-lookup"><span data-stu-id="86edc-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="86edc-250">Après avoir répété les étapes 11 à 14, cliquez sur **suivant** dans **définir les ordinateurs dans ce pool**.</span><span class="sxs-lookup"><span data-stu-id="86edc-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-251">À ce stade, vous pouvez voir les deux serveurs de périphérie de votre liste.</span><span class="sxs-lookup"><span data-stu-id="86edc-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="86edc-252">Si vous choisissez d’utiliser la traduction d’adresses réseau (NAT), une boîte de dialogue s’affiche.</span><span class="sxs-lookup"><span data-stu-id="86edc-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="86edc-253">Dans **adresse IP publique**, tapez les adresses publiques IPv4 et IPv6 (le cas échéant) à traduire par tar, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-254">Il doit s’agir de l’adresse IP externe du bord A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="86edc-255">Dans **définir le tronçon suivant**, dans la liste **pool de sauts suivants** , sélectionnez le nom du pool interne, qui peut être un pool frontal ou un pool Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="86edc-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="86edc-256">Si votre déploiement inclut un réalisateur, sélectionnez le nom du réalisateur.</span><span class="sxs-lookup"><span data-stu-id="86edc-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="86edc-257">Ensuite, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="86edc-258">Dans la liste de serveurs **Associate**, spécifiez un ou plusieurs pools internes, qui peuvent inclure des pools frontaux et des serveurs Standard Edition, à associer à ce serveur Edge, en sélectionnant les noms du ou des pools d’édition standard pour lesquels utiliser ce serveur Edge pour communication avec des utilisateurs externes pris en charge.</span><span class="sxs-lookup"><span data-stu-id="86edc-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-259">Il n’est possible d’associer qu’un seul pool Edge équilibré ou un seul serveur Edge à chaque pool interne pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="86edc-260">Si vous disposez déjà d’un pool interne associé à un serveur Edge ou à un pool de bords, un message d’avertissement s’affiche, indiquant que le pool interne est déjà associé à un serveur Edge ou à un serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="86edc-261">Si vous sélectionnez un pool déjà associé à un autre serveur Edge, l’Association est modifiée.</span><span class="sxs-lookup"><span data-stu-id="86edc-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="86edc-262">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="86edc-262">Click **Finish**.</span></span>

24. <span data-ttu-id="86edc-263">Publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="86edc-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="86edc-264">Pour définir la topologie d’un pool de serveurs Edge équilibré en charge matérielle</span><span class="sxs-lookup"><span data-stu-id="86edc-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="86edc-265">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86edc-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="86edc-266">Dans l’arborescence de la console, développez le site dans lequel vous voulez déployer des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="86edc-267">Cliquez avec le bouton droit sur pools de **bords**, puis sélectionnez **nouvelle liste de bord**.</span><span class="sxs-lookup"><span data-stu-id="86edc-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="86edc-268">Dans **définir le nouveau pool**de bordures, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="86edc-269">Dans **définir le nom de domaine complet (FQDN) du pool Edge**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-270">Dans **FQDN**, tapez le nom de domaine complet (FQDN) que vous avez choisi pour le côté interne du pool de périphérie.</span><span class="sxs-lookup"><span data-stu-id="86edc-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="86edc-271">Le nom que vous spécifiez pour le pool doit correspondre au nom du pool de bords internes.</span><span class="sxs-lookup"><span data-stu-id="86edc-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="86edc-272">Cette opération doit être définie en tant que nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="86edc-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="86edc-273">Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts.</span><span class="sxs-lookup"><span data-stu-id="86edc-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="86edc-274">Utilisez uniquement les caractères standard (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools.</span><span class="sxs-lookup"><span data-stu-id="86edc-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="86edc-275">N’utilisez ni caractère Unicode ni trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="86edc-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="86edc-276">Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le FQDN doit être attribué à l’SN dans le certificat).</span><span class="sxs-lookup"><span data-stu-id="86edc-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="86edc-277">Cliquez sur **plusieurs pools d’ordinateurs**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="86edc-278">Dans **Sélectionner les fonctionnalités** , effectuez les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="86edc-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="86edc-279">Si vous envisagez d’utiliser un nom de domaine complet et une adresse IP uniques pour le service d’accès SIP, le service de conférence Web Lync Server et le service Edge A/V, activez la case à cocher **utiliser un nom de domaine complet & adresse IP** .</span><span class="sxs-lookup"><span data-stu-id="86edc-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="86edc-280">Si vous envisagez d’activer la Fédération, activez la case à cocher **activer la Fédération pour ce pool Edge (Port 5061)** .</span><span class="sxs-lookup"><span data-stu-id="86edc-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-281">Vous pouvez sélectionner cette option, mais il se peut que vous n’ayez publié qu’une seule grappe de périphériques ou qu’un serveur Edge au sein de votre organisation pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="86edc-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="86edc-282">Tout accès par des utilisateurs fédérés, y compris des utilisateurs de la messagerie instantanée publique, passe par le même pool de périphérie ou serveur à périphérie unique.</span><span class="sxs-lookup"><span data-stu-id="86edc-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="86edc-283">Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou sur le serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou par le serveur Edge unique de New York.</span><span class="sxs-lookup"><span data-stu-id="86edc-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="86edc-284">Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="86edc-285">Si vous envisagez de prendre en charge le protocole de messagerie et de présence extensible (XMPP) pour votre déploiement, activez la case à cocher **activer la Fédération XMPP (port 5269)** .</span><span class="sxs-lookup"><span data-stu-id="86edc-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="86edc-286">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-286">Click **Next**.</span></span>

8.  <span data-ttu-id="86edc-287">Dans **Sélectionner les options IP**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-288">**Activer IPv4 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="86edc-289">**Activer IPv6 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="86edc-290">**Activer IPv4 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="86edc-291">**Activer IPv6 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de périphériques</span><span class="sxs-lookup"><span data-stu-id="86edc-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="86edc-292"><STRONG>Ne cochez pas</STRONG> la case <STRONG>l’adresse IP externe de la liste des bords est traduite par tar</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="86edc-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="86edc-293">La traduction d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="86edc-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="86edc-294">Dans les noms de **domaine complets externes**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-295">Si vous avez choisi de **Sélectionner les fonctionnalités** que vous avez choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge a/V, tapez le nom de domaine complet dans **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-296">Si vous choisissez d’activer cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés: 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence Web et 443 pour service Edge A/V).</span><span class="sxs-lookup"><span data-stu-id="86edc-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="86edc-297">En sélectionnant cette option, vous pouvez éviter les problèmes de connectivité potentiels et simplifier la configuration, car vous pouvez ensuite utiliser le même numéro de port (par exemple, 443) pour les trois services.</span><span class="sxs-lookup"><span data-stu-id="86edc-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="86edc-298">Si vous n’avez pas choisi d’utiliser une adresse de domaine complet et un nom de domaine complet (FQDN) dans **Sélectionner les fonctionnalités** , tapez le nom de domaine complet (FQDN) du pool pour l' **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="86edc-299">Dans **conférences Web**, tapez le nom de domaine complet que vous avez choisi pour le côté public du pool de périphérie.</span><span class="sxs-lookup"><span data-stu-id="86edc-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="86edc-300">Dans **audio/vidéo**, tapez le nom de domaine complet (FQDN) que vous avez choisi pour le côté public du pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="86edc-301">Utiliser les ports par défaut.</span><span class="sxs-lookup"><span data-stu-id="86edc-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="86edc-302">Il s’agira des noms de domaine complets de l’adresse IP virtuelle pour le pool.</span><span class="sxs-lookup"><span data-stu-id="86edc-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="86edc-303">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-303">Click **Next**.</span></span>

11. <span data-ttu-id="86edc-304">Dans **définir les ordinateurs dans ce pool**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="86edc-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="86edc-305">Dans **définir les adresses IP externes**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-306">Si vous avez choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse \*\*\*\* IPv4 externe du serveur Edge dans accès SIP. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="86edc-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="86edc-307">Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour les services d’accès SIP, de service de conférence Web et de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge pour l' **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="86edc-308">Dans **conférence Web**, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="86edc-309">Dans le cadre de **conférences A/V**, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="86edc-310">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-310">Click **Next**.</span></span>

14. <span data-ttu-id="86edc-311">Si vous choisissez d’activer les adresses IPv6, dans **définir les adresses IP externes**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="86edc-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="86edc-312">Si vous choisissez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans l' **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="86edc-313">Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour les services d’accès SIP, de service de conférence Web et de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge pour l' **accès SIP**.</span><span class="sxs-lookup"><span data-stu-id="86edc-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="86edc-314">Dans **conférence Web**, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="86edc-315">Dans le cadre de **conférences A/V**, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-316">Si vous n’avez pas choisi d’activer et d’affecter l’adressage IPv6, cette boîte de dialogue ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="86edc-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="86edc-317">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="86edc-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-318">Le premier serveur Edge que vous avez créé dans votre pool apparaît désormais dans la boîte de dialogue <STRONG>définir les ordinateurs dans ce pool</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="86edc-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="86edc-319">Dans **définir les ordinateurs dans ce pool**, cliquez sur **Ajouter**, puis répétez les étapes 11 à 14 pour le deuxième serveur de périmètre que vous voulez ajouter à votre pool de périphériques.</span><span class="sxs-lookup"><span data-stu-id="86edc-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="86edc-320">Après avoir répété les étapes 11 à 14, cliquez sur **suivant** dans **définir les ordinateurs dans ce pool**.</span><span class="sxs-lookup"><span data-stu-id="86edc-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-321">À ce stade, vous pouvez voir les deux serveurs de périphérie de votre liste.</span><span class="sxs-lookup"><span data-stu-id="86edc-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="86edc-322">Dans **définir le tronçon suivant**, dans la liste **pool de sauts suivants** , sélectionnez le nom du pool interne, qui peut être un pool frontal ou un pool Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="86edc-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="86edc-323">Si votre déploiement inclut un réalisateur, sélectionnez le nom du réalisateur.</span><span class="sxs-lookup"><span data-stu-id="86edc-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="86edc-324">Ensuite, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="86edc-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="86edc-325">Dans la liste de serveurs **Associate**, spécifiez un ou plusieurs pools internes, qui peuvent inclure des pools frontaux et des serveurs Standard Edition, à associer à ce serveur Edge, en sélectionnant les noms du ou des pools d’édition standard pour lesquels utiliser ce serveur Edge pour communication avec des utilisateurs externes pris en charge.</span><span class="sxs-lookup"><span data-stu-id="86edc-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86edc-326">Il n’est possible d’associer qu’un seul pool Edge équilibré ou un seul serveur Edge à chaque pool interne pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="86edc-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="86edc-327">Si vous disposez déjà d’un pool interne associé à un serveur Edge ou à un pool de bords, un message d’avertissement s’affiche, indiquant que le pool interne est déjà associé à un serveur Edge ou à un serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86edc-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="86edc-328">Si vous sélectionnez un pool déjà associé à un autre serveur Edge, l’Association est modifiée.</span><span class="sxs-lookup"><span data-stu-id="86edc-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="86edc-329">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="86edc-329">Click **Finish**.</span></span>

21. <span data-ttu-id="86edc-330">Publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="86edc-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

