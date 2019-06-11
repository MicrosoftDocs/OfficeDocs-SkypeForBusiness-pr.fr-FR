---
title: 'Lync Server 2013 : Modifications apportées dans Lync Server affectant la planification de serveurs Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="62e06-102">Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="62e06-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62e06-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="62e06-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="62e06-104">Lync Server 2013 introduit de nouvelles fonctionnalités qui étendent les fonctionnalités et méthodes de communication pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="62e06-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="62e06-105">Par ailleurs, Lync Server 2013 introduit des modifications apportées aux services existants pour améliorer l’intégration et l’extension des services disponibles pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="62e06-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="62e06-106">Vous trouverez ci-dessous un résumé des modifications qui peuvent affecter votre planification et le déploiement de Lync Server 2013 Edge Server services.</span><span class="sxs-lookup"><span data-stu-id="62e06-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="62e06-107">Prise en charge de l’adressage IPv6</span><span class="sxs-lookup"><span data-stu-id="62e06-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="62e06-108">Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services Edge Server.</span><span class="sxs-lookup"><span data-stu-id="62e06-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="62e06-109">Si vous avez fourni des adresses IPv6 pour les interfaces via une configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge via la configuration d’adresse IP dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="62e06-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="62e06-110">Par ailleurs, le protocole XMPP (extensible Messaging and Presence Protocol) prend en charge le protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="62e06-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="62e06-111">Aucune configuration supplémentaire n’est requise.</span><span class="sxs-lookup"><span data-stu-id="62e06-111">No additional configuration is required.</span></span> <span data-ttu-id="62e06-112">Si le protocole IPv6 est configuré dans la topologie, XMPP utilisera le protocole IPv6 (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="62e06-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="62e06-113">La configuration requise pour la prise en charge du protocole IPv6 dans Lync Server 2013 consiste à créer des enregistrements DNS pour les enregistrements qui doivent être identifiés et résolus à une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="62e06-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="62e06-114">Le DNS IPv6 utilise des enregistrements d’hôte définis comme **aaaa** et appelé «quadruple A».</span><span class="sxs-lookup"><span data-stu-id="62e06-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="62e06-115">Les autres types d’enregistrements sont conformes aux équivalents IPv4.</span><span class="sxs-lookup"><span data-stu-id="62e06-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="62e06-116">Prise en charge du déploiement de protocoles de messagerie extensible et de présence</span><span class="sxs-lookup"><span data-stu-id="62e06-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="62e06-117">Edge Server introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP (déployée sur votre serveur principal).</span><span class="sxs-lookup"><span data-stu-id="62e06-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="62e06-118">Vous pouvez déployer la Fédération XMPP en tant que composant facultatif.</span><span class="sxs-lookup"><span data-stu-id="62e06-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="62e06-119">En ajoutant et en configurant le proxy XMPP et la passerelle XMPP, vous pouvez permettre aux utilisateurs de Microsoft Lync 2013 d’ajouter des contacts des partenaires de XMPP pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="62e06-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62e06-120">Pour l’instant, les services XMPP dans Edge Server fournissent uniquement la messagerie instantanée et la présence entre des clients Lync Server et des contacts de type XMPP.</span><span class="sxs-lookup"><span data-stu-id="62e06-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="62e06-121">Par ailleurs, XMPP est hébergé sur un seul site.</span><span class="sxs-lookup"><span data-stu-id="62e06-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="62e06-p106">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="62e06-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="62e06-124">Prise en charge de l’authentification audio et vidéo et des certificats d’authentification de serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="62e06-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="62e06-125">Un certificat est utilisé pour générer des jetons émis pour les clients et d’autres utilisateurs du service d’authentification A/V et de l’authentification serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="62e06-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="62e06-126">Le certificat d’authentification audio/vidéo est de type *AudioVideoAuthentication* et le certificat d’authentification serveur à serveur est de type *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="62e06-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="62e06-127">Pour l’authentification audio et vidéo, les jetons sont utilisés pour authentifier les demandes d’attribution de port, et les jetons sont mis en cache pendant 8 heures maximum par défaut (durée de vie par défaut du jeton).</span><span class="sxs-lookup"><span data-stu-id="62e06-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="62e06-128">En fonctionnement normal, il s’agit d’une méthode très fiable permettant de créer et de distribuer des ressources d’authentification aux consommateurs A/V.</span><span class="sxs-lookup"><span data-stu-id="62e06-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="62e06-129">Toutefois, les certificats ont une durée de vie limitée et arrivent à expiration sur une date et une heure prédéfinies (en fonction de la date de création et des stratégies mises en œuvre dans l’autorité de certification qui a créé le certificat, généralement 2 ans pour ce type de certificat).</span><span class="sxs-lookup"><span data-stu-id="62e06-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="62e06-130">Lorsque le certificat expire, tout jeton créé par le certificat expiré et mis en cache par les consommateurs devient incorrect.</span><span class="sxs-lookup"><span data-stu-id="62e06-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="62e06-131">Toute tentative d’utilisation d’un jeton créé avec un certificat arrivé à expiration entraînait l’échec des allocations de relais de média et des sessions audio/vidéo actuelles.</span><span class="sxs-lookup"><span data-stu-id="62e06-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="62e06-132">Le client doit acquérir un nouveau jeton créé par un certificat valide pour reprendre les fonctionnalités audio et vidéo normales.</span><span class="sxs-lookup"><span data-stu-id="62e06-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="62e06-133">L’authentification de serveur à serveur est gérée par un certificat global demandé et appliqué à tous les serveurs du déploiement.</span><span class="sxs-lookup"><span data-stu-id="62e06-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="62e06-134">Le certificat est chargé d’authentifier les serveurs dans Lync Server 2013 et d’s’authentifier auprès d’Exchange 2013 et de Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62e06-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="62e06-135">Pour plus d’informations sur le fonctionnement de l’authentification de serveur à serveur, voir [gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="62e06-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="62e06-136">Une différence très importante entre le processus d’authentification audio et vidéo et le processus d’authentification de serveur à serveur est la durée de vie de l’authentification ou des jetons.</span><span class="sxs-lookup"><span data-stu-id="62e06-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="62e06-137">Pour l’authentification audio et vidéo, l’authentification expire au bout de huit heures.</span><span class="sxs-lookup"><span data-stu-id="62e06-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="62e06-138">L’authentification de serveur à serveur a une durée de vie de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="62e06-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="62e06-139">Vous devez planifier en conséquence pour chacun des types de certificats.</span><span class="sxs-lookup"><span data-stu-id="62e06-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="62e06-140">La nouvelle version de Lync Server 2013 est la possibilité de définir un certificat d’authentification audio/vidéo de remplacement, ainsi que le certificat d’authentification serveur et serveur à l’avance de l’expiration du certificat actuel.</span><span class="sxs-lookup"><span data-stu-id="62e06-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="62e06-141">Le nouveau certificat est ensuite utilisé pour générer de nouveaux jetons ou de nouvelles demandes d’authentification.</span><span class="sxs-lookup"><span data-stu-id="62e06-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="62e06-142">mais conserve l’ancien certificat pour vérifier les sessions et les authentifications actuelles.</span><span class="sxs-lookup"><span data-stu-id="62e06-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="62e06-143">Ce qu’il faut faire est d’empêcher presque toutes les échecs en raison de l’expiration des jetons et des certificats.</span><span class="sxs-lookup"><span data-stu-id="62e06-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="62e06-144">Pour plus d’informations sur cette fonctionnalité et la façon de configurer celle-ci, reportez-vous à la rubrique [mise en place des certificats d’audiovisuel et de certification OAuth dans Lync Server 2013 avec l’option Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="62e06-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="62e06-145">Dépendance réduite de l’affinité basée sur les cookies</span><span class="sxs-lookup"><span data-stu-id="62e06-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="62e06-146">Dans les versions précédentes de Lync Server et Office Communications Server, l’affinité basée sur les cookies a été utilisée par les services Web pour garantir la conservation de l’état de la session du client et du service Web.</span><span class="sxs-lookup"><span data-stu-id="62e06-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="62e06-147">Lync Server 2013 Web Services utilise un mécanisme d’affinité intégré qui élimine la plupart des exigences relatives à l’affinité basée sur les cookies.</span><span class="sxs-lookup"><span data-stu-id="62e06-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="62e06-148">Le client mobile Microsoft Lync 2010 doit toujours utiliser une affinité basée sur les cookies et nécessite une configuration de l’affinité basée sur les cookies tant que vous n’avez pas migré tous les clients vers le client Microsoft Lync mobile à venir (date de publication non encore déterminée).</span><span class="sxs-lookup"><span data-stu-id="62e06-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="62e06-149">Pour plus d’informations sur l’affinité basée sur les cookies dans Lync Server 2013, voir [composants requis pour l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="62e06-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="62e06-150">Améliorations apportées à la découverte automatique</span><span class="sxs-lookup"><span data-stu-id="62e06-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="62e06-151">La fonctionnalité de découverte automatique de Lync Server 2013 permet aux clients de trouver des fonctionnalités supplémentaires mises à disposition pour la communication.</span><span class="sxs-lookup"><span data-stu-id="62e06-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="62e06-152">La découverte automatique a été introduite pour la première fois dans la mise à jour cumulative pour Lync Server 2010:2011 novembre pour mobilité et Microsoft Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="62e06-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="62e06-153">La fonctionnalité de découverte automatique (également connue sous le nom d’enregistrement DNS LyncDiscover et LyncDiscoverInternal) permet aux clients de rechercher et d’utiliser les services de mobilité (pour les clients mobiles Microsoft Lync 2010), Microsoft Lync Web App et Lync Web Scheduler, ainsi que communications avec Microsoft Exchange Server et SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="62e06-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="62e06-154">La découverte automatique est installée normalement dans le cadre de l’installation et du déploiement de vos serveurs d’infrastructure et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62e06-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="62e06-155">Le générateur de topologie et l’Assistant Déploiement de Lync Server éliminent la plupart des tâches de configuration requises dans la mise à jour cumulative pour Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="62e06-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="62e06-156">Services pour les clients mobiles</span><span class="sxs-lookup"><span data-stu-id="62e06-156">Services for Mobile Clients</span></span>

<span data-ttu-id="62e06-157">Introduction à la mise à jour cumulative pour Lync Server 2010 2011: les services de mobilité de Lync Server 2013 permettent des téléphones mobiles exécutant des appareils mobiles et tablettes Lync utilisant des appareils mobiles Apple iOS, Android, Windows Phone ou Nokia. activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence.</span><span class="sxs-lookup"><span data-stu-id="62e06-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="62e06-158">De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, par exemple, cliquer pour participer à une conférence, appeler par le biais de votre bureau, joindre un numéro de téléphone unique et envoyer une notification d’appel manqué.</span><span class="sxs-lookup"><span data-stu-id="62e06-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62e06-159">Les services de mobilité utilisent le proxy inverse et les services publiés déployés sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="62e06-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="62e06-160">Aucune modification n’est requise sur les serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="62e06-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="62e06-161">Vous avez besoin d’un SIP/TCP/5061from sortant du serveur exécutant le service Edge d’accès de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62e06-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="62e06-162">Le rôle de directeur est facultatif</span><span class="sxs-lookup"><span data-stu-id="62e06-162">Director Role is Optional</span></span>

<span data-ttu-id="62e06-163">Le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé.</span><span class="sxs-lookup"><span data-stu-id="62e06-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="62e06-164">Il héberge toujours les services Web, préauthentifie les demandes des utilisateurs entrantes, et redirige les utilisateurs externes vers leur liste de démarrage.</span><span class="sxs-lookup"><span data-stu-id="62e06-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="62e06-165">Le fait de changer le directeur d’un rôle recommandé en rôle facultatif consiste à ne pas diminuer la valeur du directeur.</span><span class="sxs-lookup"><span data-stu-id="62e06-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="62e06-166">L’intention est de réduire le nombre de serveurs et les autres exigences matérielles (par exemple, les équilibreurs de charge matérielle pour le directeur) sans compromettre les fonctionnalités et fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="62e06-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="62e06-167">Étant donné que les serveurs front-end peuvent faire la même chose que le directeur sans avoir d’impact sur les services fournis, vous pouvez déployer des directeurs si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="62e06-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="62e06-168">Vous pouvez exclure en toute sécurité le directeur en ayant confiance aux serveurs frontaux pour proposer les mêmes services à la place d’un directeur.</span><span class="sxs-lookup"><span data-stu-id="62e06-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

