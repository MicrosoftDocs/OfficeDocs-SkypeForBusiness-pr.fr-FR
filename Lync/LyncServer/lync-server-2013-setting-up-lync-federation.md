---
title: 'Lync Server 2013 : configuration de la Fédération Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b955def7b7648f274125353673d6973afb59b7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="7cab9-102">Configuration de la Fédération Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cab9-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cab9-103">_**Dernière modification de la rubrique :** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="7cab9-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="7cab9-104">Si vous avez déjà déployé votre ou vos serveurs Edge, l’ajout des fonctionnalités de scénarios fédérés est très rapide.</span><span class="sxs-lookup"><span data-stu-id="7cab9-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="7cab9-105">Dans le cas contraire, vous devez commencer par le déploiement des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="7cab9-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="7cab9-106">Pour plus d’informations, reportez-vous à la rubrique : [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et [déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="7cab9-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cab9-p102">Si vous avez l’intention de configurer une combinaison de fédération XMPP, fédération Lync ou connectivité PIC, vous pouvez les déployer simultanément ou l’une après l’autre. Si vous configurez les options à l’aide du Générateur de topologie et de Lync Server Management shell, exécutez l’Assistant Déploiement sur le serveur Edge après avoir configuré les options d’un, de deux ou des trois types de fédération, vous pouvez ainsi réduire le nombre d’étapes nécessaires.</span><span class="sxs-lookup"><span data-stu-id="7cab9-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="7cab9-109">Configuration d’une fédération Lync dans le Générateur de topologie et l’Assistant Déploiement</span><span class="sxs-lookup"><span data-stu-id="7cab9-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="7cab9-p103">Sur le serveur frontal, ouvrez le Générateur de topologie. Développez les pools de serveurs Edge, puis cliquez avec le bouton droit sur votre serveur Edge ou votre pool de serveurs Edge. Sélectionnez Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="7cab9-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="7cab9-p104">Dans Modifier les propriétés sous Général, sélectionnez Activer la fédération pour ce pool Edge (port 5061). Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7cab9-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="7cab9-p105">Cliquez sur Action, sélectionnez Topologie, puis Publier. Dans la page Publier la topologie, cliquez sur Suivant. Quand la publication est terminée, cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="7cab9-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="7cab9-p106">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.</span><span class="sxs-lookup"><span data-stu-id="7cab9-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="7cab9-p107">Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="7cab9-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7cab9-p108">Vous pouvez activer cette option, mais un seul serveur Edge ou pool de serveurs Edge dans votre organisation peut être publié en externe pour la fédération. Tout accès par des utilisateurs fédérés, notamment les utilisateurs de messagerie instantanée publique, passe par le même serveur Edge unique ou pool de serveurs Edge. Par exemple, si votre déploiement inclut un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un déployé à Londres et que vous activez la prise en charge de la fédération sur le pool de serveurs Edge ou le serveur Edge unique de New York, le trafic de signalisation des utilisateurs fédérés passera par le pool de serveurs Edge ou le serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le serveur Edge ou le pool de serveurs de Londres pour le trafic A/V.</span><span class="sxs-lookup"><span data-stu-id="7cab9-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="7cab9-129">Configuration d’une fédération avec des partenaires</span><span class="sxs-lookup"><span data-stu-id="7cab9-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="7cab9-130">Pour configurer une Fédération réussie avec un autre Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 ou Office Communicator 2007, sélectionnez le type de Fédération dans le tableau suivant et définissez les enregistrements DNS SRV, l’hôte DNS (A ou AAAA pour IPv6) et configurez les stratégies applicables au type de Fédération :</span><span class="sxs-lookup"><span data-stu-id="7cab9-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="7cab9-131">Type de fédération</span><span class="sxs-lookup"><span data-stu-id="7cab9-131">Federation type</span></span></th>
    <th><span data-ttu-id="7cab9-132">Enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="7cab9-132">DNS Records</span></span></th>
    <th><span data-ttu-id="7cab9-133">Définition de la stratégie</span><span class="sxs-lookup"><span data-stu-id="7cab9-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="7cab9-134">Notes</span><span class="sxs-lookup"><span data-stu-id="7cab9-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="7cab9-135">Domaine partenaire découvert</span><span class="sxs-lookup"><span data-stu-id="7cab9-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="7cab9-136">Configurez un enregistrement SRV au format _sipfederationtls. _tcp. &lt; nom de domaine externe &gt; où la valeur de port pour l’enregistrement SRV est TCP 5061 et l' <strong>hôte offrant ce service</strong> est défini en tant que SIP.</span><span class="sxs-lookup"><span data-stu-id="7cab9-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="7cab9-137">&lt;nom de domaine externe &gt; : nom de domaine complet de votre service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="7cab9-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="7cab9-138">Pour plus d’informations sur la création de l’enregistrement SRV <a href="lync-server-2013-configure-dns-for-edge-support.md">, voir Configurer DNS pour la prise en charge du serveur Edge dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cab9-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7cab9-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7cab9-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7cab9-p110">Les versions précédentes faisaient référence à ce type de fédération sous le nom de <strong>Fédération ouverte améliorée</strong>. La création de l’enregistrement SRV est nécessaire pour ce type de fédération et doit permettre aux autres partenaires de découvrir votre fédération.</span><span class="sxs-lookup"><span data-stu-id="7cab9-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7cab9-143">Domaine partenaire autorisé</span><span class="sxs-lookup"><span data-stu-id="7cab9-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="7cab9-144">Configurez un enregistrement SRV au format _sipfederationtls. _tcp. &lt; nom de domaine externe &gt; où la valeur de port pour l’enregistrement SRV est TCP 5061 et l' <strong>hôte offrant ce service</strong> est défini en tant que SIP.</span><span class="sxs-lookup"><span data-stu-id="7cab9-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="7cab9-145">&lt;nom de domaine externe &gt; : nom de domaine complet de votre service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="7cab9-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="7cab9-146">Pour plus d’informations sur la création de l’enregistrement SRV <a href="lync-server-2013-configure-dns-for-edge-support.md">, voir Configurer DNS pour la prise en charge du serveur Edge dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7cab9-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7cab9-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7cab9-148">Les versions précédentes ont fait référence à ce type de Fédération en tant que <strong>fédération étendue</strong>.</span><span class="sxs-lookup"><span data-stu-id="7cab9-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="7cab9-149">La création de l’enregistrement SRV est facultative pour ce type de fédération et doit permettre aux autres partenaires de découvrir votre fédération.</span><span class="sxs-lookup"><span data-stu-id="7cab9-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="7cab9-150">Il s’agit alors d’une <strong>Fédération ouverte améliorée</strong>, ou d’un <strong>Domaine partenaire découvert</strong></span><span class="sxs-lookup"><span data-stu-id="7cab9-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7cab9-151">Serveur partenaire autorisé</span><span class="sxs-lookup"><span data-stu-id="7cab9-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="7cab9-152">Configurer le nom de domaine SIP et le nom de domaine complet du serveur Edge partenaire en tant que partenaire de Fédération dans les stratégies</span><span class="sxs-lookup"><span data-stu-id="7cab9-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7cab9-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7cab9-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurer la prise en charge des domaines externes autorisés dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7cab9-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurer la prise en charge des domaines externes bloqués dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7cab9-p113">Ce type de fédération est la définition d’une relation un-à-un et ne permet pas la découverte d’autres partenaires de fédération. Chaque partenaire de fédération est configuré explicitement. Dans les versions précédentes, on parlait de <strong>Fédération directe</strong></span><span class="sxs-lookup"><span data-stu-id="7cab9-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7cab9-159">Fournisseur d’hébergement et un fournisseur de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="7cab9-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="7cab9-160">Aucune configuration DNS spécifique n’est définie pour ce type de fédération</span><span class="sxs-lookup"><span data-stu-id="7cab9-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7cab9-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7cab9-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Création ou modification de fournisseurs fédérés SIP publics dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7cab9-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Créer ou modifier des fournisseurs fédérés SIP hébergés Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7cab9-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7cab9-164">Ce type de fédération définit les services et les fournisseurs d’hébergement que vous voulez configurer pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7cab9-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="7cab9-165">Ils sont généralement utilisés pour configurer des fournisseurs de messagerie instantanée comme Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7cab9-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="7cab9-166">et AOL, ainsi que pour héberger des fournisseurs tels que Lync Online et Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7cab9-166">and AOL, as well as hosting providers such as Lync Online and Microsoft 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="7cab9-167">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="7cab9-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="7cab9-168">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="7cab9-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="7cab9-169">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="7cab9-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="7cab9-170">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="7cab9-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="7cab9-171">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="7cab9-171">has been announced.</span></span> <span data-ttu-id="7cab9-172">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7cab9-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7cab9-173">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="7cab9-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="7cab9-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="7cab9-174">Messenger.</span></span> <span data-ttu-id="7cab9-175">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="7cab9-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7cab9-176">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="7cab9-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7cab9-177">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="7cab9-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="7cab9-178">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="7cab9-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="7cab9-179">Définir et configurer tout hôte DNS (A ou AAAA pour IPv6) et enregistrements SRV DNS requis</span><span class="sxs-lookup"><span data-stu-id="7cab9-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="7cab9-180">Définissez et configurez les stratégies à l’aide du panneau de configuration Lync Server ou à l’aide de Lync Server Management Shell et des cmdlets appropriées.</span><span class="sxs-lookup"><span data-stu-id="7cab9-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="7cab9-181">Pour plus d’informations sur les applets de commande Lync Server Management Shell, voir [Federation and External Access cmdlets dans Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="7cab9-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7cab9-182">Lync Room System (LRS) n’affiche pas le bouton de jointure pour les réunions envoyées par les organisateurs dans les partenaires Lync fédérés.</span><span class="sxs-lookup"><span data-stu-id="7cab9-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="7cab9-183">Pour qu’un lien de participation à une réunion apparaisse sur LRS, l’organisation d’expédition doit activer le format TNEF à l’aide de l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7cab9-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="7cab9-184">Notez qu’il ne s’agit pas d’un LRS spécifique.</span><span class="sxs-lookup"><span data-stu-id="7cab9-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="7cab9-185">Outlook et Lync n’affichent pas non plus de liens de jointure dans ce cas, les propriétés MAPI n’étant pas transportées, mais dans le cas d’Outlook, l’utilisateur peut ouvrir l’invitation à la réunion et cliquer sur l’URL de la réunion.</span><span class="sxs-lookup"><span data-stu-id="7cab9-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="7cab9-186">Lorsque TNEFEnabled avec est défini sur true, Exchange 2013 ne supprime pas les propriétés MAPI, y compris OnlineMeetingExternalLink et le bouton de jointure apparaît sur le rappel.</span><span class="sxs-lookup"><span data-stu-id="7cab9-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7cab9-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7cab9-187">See Also</span></span>


[<span data-ttu-id="7cab9-188">Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cab9-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="7cab9-189">Gestion de la Fédération et de l’accès externe à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cab9-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

