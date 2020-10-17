---
title: Configuration de la Fédération SIP, de la Fédération XMPP et de la messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3fa4f3b78f53df101da42a2e6b7630cdfb71dd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537071"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="65e71-102">Configuration de la Fédération SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65e71-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65e71-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="65e71-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="65e71-104">La fédération, la connectivité de messagerie instantanée publique et le protocole XMPP (Extensible Messaging and Presence Protocol) définissent une classe différente d’utilisateurs externes : les utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="65e71-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="65e71-105">Les utilisateurs d’un déploiement de Lync Server fédéré ou d’un déploiement XMPP ont accès à un ensemble limité de services et sont authentifiés par le déploiement externe.</span><span class="sxs-lookup"><span data-stu-id="65e71-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="65e71-106">Les utilisateurs distants sont membres de votre déploiement Lync Server et ont accès à tous les services offerts par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="65e71-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="65e71-107">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="65e71-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="65e71-108">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="65e71-108">has been announced.</span></span> <span data-ttu-id="65e71-109">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="65e71-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="65e71-110">La connectivité de messagerie instantanée publique est un type de Fédération particulier qui permet à un client Lync Server d’accéder à des partenaires de messagerie instantanée publics configurés à l’aide de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="65e71-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="65e71-111">Les partenaires de connectivité de messagerie instantanée publique actuels sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="65e71-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="65e71-112">America Online</span><span class="sxs-lookup"><span data-stu-id="65e71-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="65e71-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="65e71-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="65e71-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="65e71-114">Yahoo\!</span></span>

<span data-ttu-id="65e71-115">Une configuration de connectivité de messagerie instantanée publique permet aux utilisateurs de Lync d’accéder à des utilisateurs de connectivité de messagerie instantanée publique grâce à :</span><span class="sxs-lookup"><span data-stu-id="65e71-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="65e71-116">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="65e71-116">IM and Presence</span></span>

  - <span data-ttu-id="65e71-117">Visibilité des contacts de connectivité de messagerie instantanée publique dans le client Lync</span><span class="sxs-lookup"><span data-stu-id="65e71-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="65e71-118">Conversations de messagerie instantanée de personne à personne avec des contacts</span><span class="sxs-lookup"><span data-stu-id="65e71-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="65e71-119">Appels audio et vidéo avec des utilisateurs de Windows Live</span><span class="sxs-lookup"><span data-stu-id="65e71-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="65e71-p104">La fédération Lync Server définit un contrat entre votre déploiement de Lync Server et d’autres déploiements d’Office Communications Server 2007 R2 ou de Lync Server. Une configuration fédérée de Lync Server permet aux utilisateurs de Lync d’accéder aux utilisateurs fédérés grâce à :</span><span class="sxs-lookup"><span data-stu-id="65e71-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="65e71-122">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="65e71-122">IM and Presence</span></span>

  - <span data-ttu-id="65e71-123">Création de contacts fédérés dans le client Lync</span><span class="sxs-lookup"><span data-stu-id="65e71-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="65e71-p105">La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs de Lync d’accéder aux utilisateurs de domaine XMPP autorisés grâce à :</span><span class="sxs-lookup"><span data-stu-id="65e71-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="65e71-126">Messagerie instantanée et présence – de personne à personne uniquement</span><span class="sxs-lookup"><span data-stu-id="65e71-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="65e71-127">la création de contacts fédérés XMPP dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="65e71-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="65e71-p106">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="65e71-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="65e71-130">Fédération externe de serveur Edge, connectivité de messagerie instantanée publique et processus de déploiement d’utilisateurs XMPP</span><span class="sxs-lookup"><span data-stu-id="65e71-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65e71-131">Phase</span><span class="sxs-lookup"><span data-stu-id="65e71-131">Phase</span></span></th>
<th><span data-ttu-id="65e71-132">Étapes</span><span class="sxs-lookup"><span data-stu-id="65e71-132">Steps</span></span></th>
<th><span data-ttu-id="65e71-133">Autorisations</span><span class="sxs-lookup"><span data-stu-id="65e71-133">Permissions</span></span></th>
<th><span data-ttu-id="65e71-134">Documentation</span><span class="sxs-lookup"><span data-stu-id="65e71-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65e71-135">Déterminer les options à ajouter au déploiement Edge existant</span><span class="sxs-lookup"><span data-stu-id="65e71-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="65e71-136">Exécutez le générateur de topologie pour modifier les paramètres du serveur Edge et créer et publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="65e71-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="65e71-137">Votre topologie Edge existante répliquera les modifications du magasin central de gestion sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="65e71-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="65e71-138">Groupe Administrateurs du domaine et groupe RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="65e71-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="65e71-139">Vous pouvez modifier une topologie à l’aide d’un compte qui est membre du groupe d’utilisateurs locaux, mais la publication d’une topologie nécessite un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="65e71-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="65e71-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de serveur Edge et de directeur dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65e71-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65e71-141">Préparer l’installation</span><span class="sxs-lookup"><span data-stu-id="65e71-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="65e71-142">S’assurer que la configuration système requise est satisfaite.</span><span class="sxs-lookup"><span data-stu-id="65e71-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="65e71-143">Configurer les enregistrements DNS internes et externes afin de prendre en charge la connectivité de messagerie instantanée publique, la fédération Lync et la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="65e71-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="65e71-144">Configurer les ports et protocoles au niveau du pare-feu afin de prendre en charge les types de fédération que vous déployez</span><span class="sxs-lookup"><span data-stu-id="65e71-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="65e71-p108">Obtenir et installer les certificats publics. La durée nécessaire à l’obtention des certificats dépend de l’autorité de certification qui émet le certificat. Cette étape est facultative à ce stade du déploiement. Si vous ne l’effectuez pas maintenant, vous devez le faire durant la configuration du serveur Edge. Le service du serveur Edge ne peut pas être démarré avant l’obtention des certificats.</span><span class="sxs-lookup"><span data-stu-id="65e71-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="65e71-150">En fonction de votre organisation, car ces rôles sont généralement distribués parmi plusieurs groupes de travail</span><span class="sxs-lookup"><span data-stu-id="65e71-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="65e71-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65e71-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65e71-152">Configurer les serveurs Edge pour les scénarios de fédération</span><span class="sxs-lookup"><span data-stu-id="65e71-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="65e71-153">Transporter le fichier de configuration de topologie exporté vers chaque serveur Edge ou laisser la réplication se terminer</span><span class="sxs-lookup"><span data-stu-id="65e71-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="65e71-154">Réexécuter l’Assistant Déploiement pour installer les composants de prise en charge pour la fédération</span><span class="sxs-lookup"><span data-stu-id="65e71-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="65e71-155">Configurer les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="65e71-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="65e71-156">Demander et installer des certificats pour chaque serveur Edge</span><span class="sxs-lookup"><span data-stu-id="65e71-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="65e71-157">Redémarrer les services du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="65e71-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="65e71-158">Groupe Administrateurs</span><span class="sxs-lookup"><span data-stu-id="65e71-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="65e71-159"><a href="lync-server-2013-setting-up-lync-federation.md">Configuration de la Fédération Lync dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65e71-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="65e71-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configuration de la connectivité de messagerie instantanée publique dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65e71-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="65e71-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Configuration de la Fédération XMPP dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65e71-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65e71-162">Configurer la prise en charge de l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="65e71-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="65e71-163">Utilisation de l’accès des utilisateurs externes au panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="65e71-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="65e71-164">Configurer la stratégie d’accès externe pour activer les communications avec les utilisateurs fédérés ou publics</span><span class="sxs-lookup"><span data-stu-id="65e71-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="65e71-165">Configurer des domaines fédérés SIP pour autoriser ou bloquer des domaines</span><span class="sxs-lookup"><span data-stu-id="65e71-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="65e71-166">Activer des fournisseurs fédérés SIP pour les fournisseurs de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="65e71-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="65e71-167">Configurer des partenaires fédérés XMPP par domaine XMPP</span><span class="sxs-lookup"><span data-stu-id="65e71-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="65e71-168">Groupe RTCUniversalServerAdmins ou compte d’utilisateur affecté au rôle CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="65e71-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="65e71-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65e71-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="65e71-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurer le chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65e71-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65e71-171">Vérifier votre configuration de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="65e71-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="65e71-172">Vérifier la connectivité serveur et la réplication des données de configuration à partir des serveurs internes</span><span class="sxs-lookup"><span data-stu-id="65e71-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="65e71-173">Pour la vérification de la réplication, un groupe RTCUniversalServerAdmins ou compte d’utilisateur affecté au rôle CSAdministrator. Pour la vérification de la connectivité utilisateur, un utilisateur de chaque type d’utilisateur fédéré</span><span class="sxs-lookup"><span data-stu-id="65e71-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="65e71-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Vérification de votre déploiement Edge dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65e71-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="65e71-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="65e71-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

