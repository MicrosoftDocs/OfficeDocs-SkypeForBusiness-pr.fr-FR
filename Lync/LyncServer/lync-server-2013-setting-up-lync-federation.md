---
title: 'Lync Server 2013 : Configuration de la fédération Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6dc0a2aeb39c86db54d21a2c4be5ff6c5be599
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="eaf83-102">Configuration de la fédération Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaf83-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaf83-103">_**Dernière modification de la rubrique:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="eaf83-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="eaf83-104">Si vous avez déjà déployé votre serveur ou serveur Edge, l’ajout de fonctionnalités de scénarios fédérés est une avancée directe.</span><span class="sxs-lookup"><span data-stu-id="eaf83-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="eaf83-105">Si vous n’avez pas configuré Edge Servers, vous devez commencer par cela.</span><span class="sxs-lookup"><span data-stu-id="eaf83-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="eaf83-106">Pour plus d’informations, reportez-vous à la section [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et [au déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="eaf83-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eaf83-107">Si vous envisagez de configurer n’importe quelle combinaison de la Fédération XMPP, de la Fédération Lync ou de la connectivité de messagerie instantanée publique, vous pouvez les déployer en même temps.</span><span class="sxs-lookup"><span data-stu-id="eaf83-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="eaf83-108">Si vous configurez les options à l’aide du générateur de topologie et de Lync Server Management Shell, puis exécutez l’Assistant Déploiement sur le serveur Edge après avoir configuré les options pour un, deux ou trois types de Fédération, vous pouvez réduire le nombre d’étapes requises.</span><span class="sxs-lookup"><span data-stu-id="eaf83-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="eaf83-109">Configuration de la Fédération Lync dans le générateur de topologie et de l’Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="eaf83-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="eaf83-110">Sur un serveur frontal, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="eaf83-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="eaf83-111">Développez pools de bords, puis cliquez avec le bouton droit sur votre serveur Edge ou sur le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="eaf83-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="eaf83-112">Sélectionnez modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="eaf83-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="eaf83-113">Dans modifier les propriétés sous général, sélectionnez Activer la Fédération pour ce pool Edge (port 5061).</span><span class="sxs-lookup"><span data-stu-id="eaf83-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="eaf83-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="eaf83-114">Click OK.</span></span>

3.  <span data-ttu-id="eaf83-115">Cliquez sur action, sélectionnez topologie, puis publier.</span><span class="sxs-lookup"><span data-stu-id="eaf83-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="eaf83-116">Lorsque le système vous le demande, cliquez sur suivant.</span><span class="sxs-lookup"><span data-stu-id="eaf83-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="eaf83-117">Lorsque la publication est terminée, cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="eaf83-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="eaf83-118">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eaf83-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="eaf83-119">Cliquez sur installer ou mettre à jour le système serveur Lync, puis cliquez sur Configurer ou supprimer les composants Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eaf83-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="eaf83-120">Cliquez de nouveau sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="eaf83-120">Click Run Again.</span></span>

5.  <span data-ttu-id="eaf83-121">Dans configurer les composants serveur Lync, cliquez sur suivant.</span><span class="sxs-lookup"><span data-stu-id="eaf83-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="eaf83-122">L’écran de synthèse indique les actions à mesure qu’elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="eaf83-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="eaf83-123">Lorsque le déploiement est effectué, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="eaf83-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="eaf83-124">Cliquez sur Terminer pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="eaf83-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eaf83-125">Vous pouvez sélectionner cette option, mais un seul pool de périphériques ou serveur de périphérie de votre organisation peut être publié en externe pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="eaf83-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="eaf83-126">Tout accès par des utilisateurs fédérés, y compris des utilisateurs de la messagerie instantanée publique, passe par le même pool de périphérie ou serveur à périphérie unique.</span><span class="sxs-lookup"><span data-stu-id="eaf83-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="eaf83-127">Par exemple, si votre déploiement inclut un pool de périphérie ou un serveur Edge unique déployé à New York et un serveur déployé à Londres et que vous activez la prise en charge de la Fédération sur le pool de périphériques de la Nouvelle-York ou sur un serveur de périphérie Pool Edge ou serveur Edge unique.</span><span class="sxs-lookup"><span data-stu-id="eaf83-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="eaf83-128">Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="eaf83-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="eaf83-129">Configuration de la Fédération avec des partenaires</span><span class="sxs-lookup"><span data-stu-id="eaf83-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="eaf83-130">Pour configurer une Fédération réussie avec un autre Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 ou Office Communicator 2007, sélectionnez le type de Fédération dans le tableau suivant et définissez les enregistrements DNS SRV, l’hôte DNS (A ou AAAA pour IPv6) et configurez les stratégies applicables au type de Fédération:</span><span class="sxs-lookup"><span data-stu-id="eaf83-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="eaf83-131">Type de Fédération</span><span class="sxs-lookup"><span data-stu-id="eaf83-131">Federation type</span></span></th>
    <th><span data-ttu-id="eaf83-132">Enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="eaf83-132">DNS Records</span></span></th>
    <th><span data-ttu-id="eaf83-133">Définition de la stratégie</span><span class="sxs-lookup"><span data-stu-id="eaf83-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="eaf83-134">Notes</span><span class="sxs-lookup"><span data-stu-id="eaf83-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="eaf83-135">Domaine partenaire détecté</span><span class="sxs-lookup"><span data-stu-id="eaf83-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="eaf83-136">Configurez l’enregistrement SRV du format _sipfederationtls. _ TCP. &lt;nom&gt;de domaine externe où la valeur de port pour l’enregistrement SRV est TCP 5061 et l' <strong>hôte proposant ce service</strong> est défini en tant que SIP.</span><span class="sxs-lookup"><span data-stu-id="eaf83-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="eaf83-137">&lt;nom de domaine&gt; externe: nom de domaine complet (FQDN) du service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="eaf83-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="eaf83-138">Pour plus d’informations sur la création de l’enregistrement SRV <a href="lync-server-2013-configure-dns-for-edge-support.md">, voir Configurer la prise en charge de DNS pour Edge dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="eaf83-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="eaf83-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="eaf83-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="eaf83-141">Versions précédentes auxquelles il est fait référence à ce type de Fédération en tant qu’ouverture de la <strong>Fédération avancée</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf83-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="eaf83-142">La création de l’enregistrement SRV est requise pour ce type de Fédération et permet à d’autres partenaires de détecter votre Fédération.</span><span class="sxs-lookup"><span data-stu-id="eaf83-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eaf83-143">Domaine partenaire autorisé</span><span class="sxs-lookup"><span data-stu-id="eaf83-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="eaf83-144">Configurez l’enregistrement SRV du format _sipfederationtls. _ TCP. &lt;nom&gt;de domaine externe où la valeur de port pour l’enregistrement SRV est TCP 5061 et l' <strong>hôte proposant ce service</strong> est défini en tant que SIP.</span><span class="sxs-lookup"><span data-stu-id="eaf83-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="eaf83-145">&lt;nom de domaine&gt; externe: nom de domaine complet (FQDN) du service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="eaf83-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="eaf83-146">Pour plus d’informations sur la création de l’enregistrement SRV <a href="lync-server-2013-configure-dns-for-edge-support.md">, voir Configurer la prise en charge de DNS pour Edge dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="eaf83-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="eaf83-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="eaf83-148">Versions précédentes auxquelles il est fait référence à ce type de Fédération comme <strong>Fédération améliorée</strong>.</span><span class="sxs-lookup"><span data-stu-id="eaf83-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="eaf83-149">La création de l’enregistrement SRV peut être facultative pour ce type de Fédération et permettre à d’autres partenaires de détecter votre Fédération.</span><span class="sxs-lookup"><span data-stu-id="eaf83-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="eaf83-150">Bien entendu, il s’agit d’une <strong>fédération étendue ouverte</strong>ou d’un <strong>domaine partenaire découvert</strong> .</span><span class="sxs-lookup"><span data-stu-id="eaf83-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="eaf83-151">Serveur partenaire autorisé</span><span class="sxs-lookup"><span data-stu-id="eaf83-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="eaf83-152">Configurer le nom de domaine SIP et le FQDN du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="eaf83-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="eaf83-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="eaf83-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="eaf83-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configuration de la prise en charge pour les domaines externes bloqués dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="eaf83-156">Ce type de Fédération est la définition d’une relation un-à-un qui ne permet pas la découverte d’autres partenaires de la Fédération.</span><span class="sxs-lookup"><span data-stu-id="eaf83-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="eaf83-157">Chaque partenaire de Fédération est configuré explicitement.</span><span class="sxs-lookup"><span data-stu-id="eaf83-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="eaf83-158">Dans les versions précédentes, il s’agit de la <strong>Fédération directe</strong></span><span class="sxs-lookup"><span data-stu-id="eaf83-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="eaf83-159">Fournisseur d’hébergement et fournisseur de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="eaf83-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="eaf83-160">Aucune configuration DNS spécifique n’est définie pour ce type de Fédération</span><span class="sxs-lookup"><span data-stu-id="eaf83-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="eaf83-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="eaf83-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="eaf83-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Création ou modification des fournisseurs fédérés SIP hébergés dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="eaf83-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="eaf83-164">Ce type de Fédération définit les services et fournisseurs d’hébergement que vous voulez configurer pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="eaf83-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="eaf83-165">Les utilisations typiques incluent la configuration pour les fournisseurs de messagerie instantanée publique tels que Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="eaf83-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="eaf83-166">et AOL, ainsi que des fournisseurs d’hébergement tels que Lync Online et Office 365</span><span class="sxs-lookup"><span data-stu-id="eaf83-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="eaf83-167">À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="eaf83-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="eaf83-168">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="eaf83-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="eaf83-169">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="eaf83-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="eaf83-170">Date de fin de vie du 2014 juin pour AOL et Yahoo!</span><span class="sxs-lookup"><span data-stu-id="eaf83-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="eaf83-171">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="eaf83-171">has been announced.</span></span> <span data-ttu-id="eaf83-172">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eaf83-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eaf83-173">La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="eaf83-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="eaf83-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="eaf83-174">Messenger.</span></span> <span data-ttu-id="eaf83-175">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</span><span class="sxs-lookup"><span data-stu-id="eaf83-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eaf83-176">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="eaf83-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="eaf83-177">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="eaf83-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="eaf83-178">Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</span><span class="sxs-lookup"><span data-stu-id="eaf83-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="eaf83-179">Définissez et configurez tout hôte DNS requis (A ou AAAA pour IPv6) et enregistrements SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="eaf83-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="eaf83-180">Définissez et configurez toutes les stratégies à l’aide du panneau de configuration de Lync Server ou en utilisant Lync Server Management Shell et les applets de commande appropriées.</span><span class="sxs-lookup"><span data-stu-id="eaf83-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="eaf83-181">Pour en savoir plus sur les applets de cmdlet Lync Server Management Shell, voir [Fédération et applets de connexion Access externes dans Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="eaf83-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eaf83-182">Le système de salle Lync (LRS) ne montre pas le bouton de participation pour les réunions envoyées par des organisateurs dans les partenaires Lync fédérés.</span><span class="sxs-lookup"><span data-stu-id="eaf83-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="eaf83-183">Pour qu’un lien de participation à une réunion apparaisse sur LRS, l’organisation d’expédition doit activer TNEF en utilisant l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="eaf83-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="eaf83-184">Notez que cela n’est pas spécifique à LRS.</span><span class="sxs-lookup"><span data-stu-id="eaf83-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="eaf83-185">Dans le cas contraire, Outlook et Lync n’affichent pas de liens de jointure dans le cas où les propriétés MAPI ne sont pas transportées, mais dans le cas d’Outlook, l’utilisateur peut ouvrir l’invitation à la réunion et cliquer sur l’URL de la réunion.</span><span class="sxs-lookup"><span data-stu-id="eaf83-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="eaf83-186">Lorsque TNEFEnabled est défini sur true Exchange 2013 ne Strip pas les propriétés MAPI, y compris OnlineMeetingExternalLink et le bouton Join s’affichera sur le rappel.</span><span class="sxs-lookup"><span data-stu-id="eaf83-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eaf83-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eaf83-187">See Also</span></span>


[<span data-ttu-id="eaf83-188">Planification de la Fédération SIP, de XMPP et de la messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaf83-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="eaf83-189">Gestion de la fédération et de l’accès externe à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaf83-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

