---
title: Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="87b82-102">Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87b82-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87b82-103">_**Dernière modification de la rubrique:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="87b82-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="87b82-104">La Fédération, la connectivité de messagerie instantanée publique et le protocole XMPP (extensible Messaging and Presence Protocol) définissent une catégorie différente d’utilisateurs externes – utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="87b82-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="87b82-105">Les utilisateurs d’un déploiement de déploiement de Lync Server ou de déploiement XMPP peuvent avoir accès à un ensemble de services limité et être authentifiés par le déploiement externe.</span><span class="sxs-lookup"><span data-stu-id="87b82-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="87b82-106">Les utilisateurs distants sont membres de votre déploiement Lync Server et ont accès à tous les services proposés par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="87b82-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="87b82-107">Date de fin de vie du 2014 juin pour AOL et Yahoo!</span><span class="sxs-lookup"><span data-stu-id="87b82-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="87b82-108">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="87b82-108">has been announced.</span></span> <span data-ttu-id="87b82-109">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="87b82-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="87b82-110">La connectivité de messagerie instantanée publique est un type spécial de Fédération qui permet à un client du serveur Lync d’accéder aux fournisseurs de messagerie instantanée publics à l’aide de la 2013 Lync.</span><span class="sxs-lookup"><span data-stu-id="87b82-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="87b82-111">Les partenaires de connectivité de messagerie instantanée publics actuels sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="87b82-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="87b82-112">America Online</span><span class="sxs-lookup"><span data-stu-id="87b82-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="87b82-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="87b82-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="87b82-114">Yahoo!\!</span><span class="sxs-lookup"><span data-stu-id="87b82-114">Yahoo\!</span></span>

<span data-ttu-id="87b82-115">Une configuration de connectivité de messagerie instantanée publique permet aux utilisateurs de Lync d’accéder aux utilisateurs de la connectivité de messagerie instantanée publique de la façon suivante:</span><span class="sxs-lookup"><span data-stu-id="87b82-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="87b82-116">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="87b82-116">IM and Presence</span></span>

  - <span data-ttu-id="87b82-117">Visibilité des contacts sur la connectivité de messagerie instantanée publique dans le client Lync</span><span class="sxs-lookup"><span data-stu-id="87b82-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="87b82-118">Personne à personne conversations par messagerie instantanée avec les contacts</span><span class="sxs-lookup"><span data-stu-id="87b82-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="87b82-119">Appels audio et vidéo avec les utilisateurs de Windows Live</span><span class="sxs-lookup"><span data-stu-id="87b82-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="87b82-120">Lync Server Federation définit un accord entre le déploiement de votre serveur Lync et d’autres déploiements Office Communications Server 2007 R2 ou Lync Server.</span><span class="sxs-lookup"><span data-stu-id="87b82-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="87b82-121">Une configuration fédérée de Lync Server permet aux utilisateurs de Lync d’accéder aux utilisateurs fédérés en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="87b82-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="87b82-122">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="87b82-122">IM and Presence</span></span>

  - <span data-ttu-id="87b82-123">Création de contacts fédérés dans le client Lync</span><span class="sxs-lookup"><span data-stu-id="87b82-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="87b82-124">La Fédération XMPP définit un déploiement externe en fonction du protocole de messagerie eXtensible et de présence.</span><span class="sxs-lookup"><span data-stu-id="87b82-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="87b82-125">Une configuration XMPP permet aux utilisateurs de Lync d’accéder aux utilisateurs de domaine XMPP autorisés en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="87b82-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="87b82-126">Messagerie instantanée et présence-personne à personne uniquement</span><span class="sxs-lookup"><span data-stu-id="87b82-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="87b82-127">Créer des contacts fédérés de XMPP dans le client Lync</span><span class="sxs-lookup"><span data-stu-id="87b82-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="87b82-p106">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="87b82-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="87b82-130">Processus de déploiement de la Fédération externe du serveur Edge, de la connectivité de messagerie instantanée publique et du processus de déploiement des utilisateurs XMPP</span><span class="sxs-lookup"><span data-stu-id="87b82-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87b82-131">Phase</span><span class="sxs-lookup"><span data-stu-id="87b82-131">Phase</span></span></th>
<th><span data-ttu-id="87b82-132">Étapes</span><span class="sxs-lookup"><span data-stu-id="87b82-132">Steps</span></span></th>
<th><span data-ttu-id="87b82-133">Autorisations</span><span class="sxs-lookup"><span data-stu-id="87b82-133">Permissions</span></span></th>
<th><span data-ttu-id="87b82-134">Documentation</span><span class="sxs-lookup"><span data-stu-id="87b82-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87b82-135">Déterminez les options à ajouter au déploiement Edge existant.</span><span class="sxs-lookup"><span data-stu-id="87b82-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="87b82-136">Exécutez le générateur de topologie pour modifier les paramètres du serveur de bord et créez et publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="87b82-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="87b82-137">Votre topologie de périphérie existante réplique les modifications du magasin central de gestion sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="87b82-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="87b82-138">Groupe administrateurs de domaine et groupe RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="87b82-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="87b82-139">Vous pouvez modifier une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais la publication d’une topologie nécessite un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="87b82-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="87b82-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de serveurs Edge et directeurs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87b82-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b82-141">Préparer l’installation</span><span class="sxs-lookup"><span data-stu-id="87b82-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="87b82-142">Vérifiez que les conditions système préalables sont remplies.</span><span class="sxs-lookup"><span data-stu-id="87b82-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="87b82-143">Configurer les enregistrements DNS internes et externes pour la prise en charge de la connectivité de messagerie instantanée publique, de la Fédération Lync et de la Fédération de XMPP</span><span class="sxs-lookup"><span data-stu-id="87b82-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="87b82-144">Configurer les ports et les protocoles dans le pare-feu pour prendre en charge les types de Fédération que vous déployez</span><span class="sxs-lookup"><span data-stu-id="87b82-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="87b82-145">Obtenez et installez des certificats publics.</span><span class="sxs-lookup"><span data-stu-id="87b82-145">Obtain and install public certificates.</span></span> <span data-ttu-id="87b82-146">Le temps requis pour obtenir des certificats dépend de l’autorité de certification qui émet le certificat.</span><span class="sxs-lookup"><span data-stu-id="87b82-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="87b82-147">Cette étape est facultative à ce stade du déploiement.</span><span class="sxs-lookup"><span data-stu-id="87b82-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="87b82-148">Si vous n’effectuez pas cette étape à ce stade, vous devez le faire pendant la configuration du serveur de périmètre.</span><span class="sxs-lookup"><span data-stu-id="87b82-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="87b82-149">Le service Edge Server ne peut pas être démarré tant qu’aucun certificat n’est obtenu</span><span class="sxs-lookup"><span data-stu-id="87b82-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="87b82-150">En fonction de votre organisation, car ces rôles sont généralement répartis entre de nombreux groupes de tâches.</span><span class="sxs-lookup"><span data-stu-id="87b82-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="87b82-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planification de la Fédération SIP, de XMPP et de la messagerie instantanée publique dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87b82-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b82-152">Configurer des serveurs de périphérie pour des scénarios de Fédération</span><span class="sxs-lookup"><span data-stu-id="87b82-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="87b82-153">Transférez le fichier de configuration topologique exporté vers chaque serveur Edge ou attendez la fin de la réplication.</span><span class="sxs-lookup"><span data-stu-id="87b82-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="87b82-154">Exécutez de nouveau l’Assistant déploiement pour installer les composants de prise en charge de la Fédération</span><span class="sxs-lookup"><span data-stu-id="87b82-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="87b82-155">Configurer les serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="87b82-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="87b82-156">Demander et installer des certificats pour chaque serveur Edge</span><span class="sxs-lookup"><span data-stu-id="87b82-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="87b82-157">Redémarrer les services Edge Server</span><span class="sxs-lookup"><span data-stu-id="87b82-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="87b82-158">Groupe administrateurs</span><span class="sxs-lookup"><span data-stu-id="87b82-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="87b82-159"><a href="lync-server-2013-setting-up-lync-federation.md">Configuration de la fédération Lync dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87b82-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="87b82-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configuration de la connectivité PIC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87b82-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="87b82-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Configuration de la fédération XMPP dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87b82-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b82-162">Configurer la prise en charge de l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="87b82-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="87b82-163">Utiliser l’accès aux utilisateurs externes de Lync Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="87b82-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="87b82-164">Configurer une stratégie d’accès externe pour activer les communications avec les utilisateurs fédérés ou les utilisateurs publics</span><span class="sxs-lookup"><span data-stu-id="87b82-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="87b82-165">Configurer des domaines fédérés SIP pour autoriser ou bloquer des domaines</span><span class="sxs-lookup"><span data-stu-id="87b82-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="87b82-166">Activer les fournisseurs fédérés SIP pour les fournisseurs de connectivité de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="87b82-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="87b82-167">Configurer des partenaires fédérés de XMPP par domaine XMPP</span><span class="sxs-lookup"><span data-stu-id="87b82-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="87b82-168">RTCUniversalServerAdmins groupe ou compte d’utilisateur affecté au rôle CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="87b82-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="87b82-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87b82-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="87b82-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configuration du chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87b82-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87b82-171">Vérifier la configuration de votre serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="87b82-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="87b82-172">Vérifier la connectivité du serveur et la réplication des données de configuration de serveurs internes</span><span class="sxs-lookup"><span data-stu-id="87b82-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="87b82-173">Pour la vérification de la réplication, du groupe RTCUniversalServerAdmins ou du compte d’utilisateur qui est attribué à CSAdministrator roleFor vérification de la connectivité utilisateur, un utilisateur pour chaque type d’utilisateur fédéré</span><span class="sxs-lookup"><span data-stu-id="87b82-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="87b82-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Vérification de votre déploiement Edge dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87b82-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="87b82-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="87b82-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

