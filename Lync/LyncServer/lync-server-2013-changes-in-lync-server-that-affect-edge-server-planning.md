---
title: 'Lync Server 2013 : modifications apportées dans Lync Server affectant la planification des serveurs Edge'
description: 'Lync Server 2013 : modifications apportées dans Lync Server et qui affectent la planification du serveur Edge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660a281d858cf92a48d5eaed6d5caf3141b3817
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543750"
---
# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="199bc-103">Modifications apportées dans Lync Server 2013 affectant la planification des serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="199bc-103">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="199bc-104">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="199bc-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="199bc-105">Lync Server 2013 introduit de nouvelles fonctionnalités qui étendent les fonctionnalités et les méthodes de communication pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="199bc-105">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="199bc-106">De plus, Lync Server 2013 introduit les modifications apportées aux services existants afin d’améliorer l’intégration et l’extension des services disponibles pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="199bc-106">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="199bc-107">Vous trouverez ci-dessous un résumé des modifications susceptibles d’avoir un impact sur la planification et le déploiement des services de serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="199bc-107">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="199bc-108">Prise en charge de l’adressage IPv6</span><span class="sxs-lookup"><span data-stu-id="199bc-108">Support for IPv6 Addressing</span></span>

<span data-ttu-id="199bc-109">Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="199bc-109">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="199bc-110">Si vous avez fourni des adresses IPv6 pour les interfaces par le biais de la configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge par le biais de la configuration d’adresse IP dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="199bc-110">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="199bc-111">Par ailleurs, le protocole XMPP (Extensible Messaging and Presence Protocol) prend en charge IPv6.</span><span class="sxs-lookup"><span data-stu-id="199bc-111">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="199bc-112">Aucune configuration supplémentaire n’est requise.</span><span class="sxs-lookup"><span data-stu-id="199bc-112">No additional configuration is required.</span></span> <span data-ttu-id="199bc-113">Si IPv6 est configuré dans la topologie, XMPP utilise IPv6 (au besoin).</span><span class="sxs-lookup"><span data-stu-id="199bc-113">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="199bc-114">Une configuration requise supplémentaire pour prendre en charge IPv6 dans Lync Server 2013 consiste à créer des enregistrements DNS pour les enregistrements qui doivent être découverts et résolus en adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="199bc-114">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="199bc-115">DNS IPv6 utilise des enregistrements d’hôte qui sont définis sous la forme **AAAA** et qui sont appelés « quad-A ».</span><span class="sxs-lookup"><span data-stu-id="199bc-115">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="199bc-116">Les autres types d’enregistrements sont en accord avec leurs homologues IPv4.</span><span class="sxs-lookup"><span data-stu-id="199bc-116">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="199bc-117">Prise en charge du déploiement XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="199bc-117">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="199bc-118">Le serveur Edge introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP (déployé sur vos serveurs frontaux).</span><span class="sxs-lookup"><span data-stu-id="199bc-118">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="199bc-119">Vous pouvez déployer Fédération XMPP comme un composant facultatif.</span><span class="sxs-lookup"><span data-stu-id="199bc-119">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="199bc-120">En ajoutant et en configurant le proxy XMPP et la passerelle XMPP, vous pouvez permettre à vos utilisateurs Microsoft Lync 2013 d’ajouter des contacts à partir de partenaires XMPP pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="199bc-120">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="199bc-121">Actuellement, les services XMPP du serveur Edge fournissent uniquement la messagerie instantanée et la présence entre les clients Lync Server et les contacts XMPP.</span><span class="sxs-lookup"><span data-stu-id="199bc-121">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="199bc-122">En outre, XMPP est hébergé dans un seul site.</span><span class="sxs-lookup"><span data-stu-id="199bc-122">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="199bc-p106">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="199bc-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="199bc-125">Prend en charge des certificats pour l’authentification audio/vidéo propagée et l’authentification serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="199bc-125">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="199bc-p107">Un certificat est utilisé pour générer des jetons qui sont émis aux clients et autres consommateurs du service d’authentication A/V et dans le cadre de l’authentification serveur à serveur. Le certificat d’authentification audio/vidéo est de type *AudioVideoAuthentication*, tandis que le certificat d’authentification serveur à serveur est de type *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="199bc-p107">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication. The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="199bc-p108">Pour l’authentification audio/vidéo, les jetons sont utilisés pour authentifier les demandes d’allocation de port, et les jetons sont mis en cache pendant la durée de vie par défaut du jeton (jusqu’à 8 heures). En fonctionnement normal, il s’agit d’une méthode très fiable pour créer et distribuer du matériel d’authentification aux consommateurs A/V. Toutefois, les certificats ont une durée de vie limitée et expirent à une date et une heure prédéfinies (selon la date de création et les stratégies appliquées au niveau de l’autorité de certification ayant créé le certificat, en général deux ans pour ce type de certificat). Lorsque le certificat expire, les jetons créés par le certificat expiré et mis en cache par les consommateurs ne sont plus valides. Toute tentative d’utilisation d’un jeton créé avec un certificat expiré se traduit par l’échec des allocations du serveur relais multimédia et l’échec de toutes les sessions audio/vidéo actuelles. Le client doit alors acquérir un nouveau jeton créé par un certificat valide pour bénéficier à nouveau de fonctionnalités audio et vidéo normales.</span><span class="sxs-lookup"><span data-stu-id="199bc-p108">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token. Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers. However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate). When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid. Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail. The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="199bc-134">L’authentification serveur à serveur est gérée par un certificat global qui est demandé et appliqué à tous les serveurs du déploiement.</span><span class="sxs-lookup"><span data-stu-id="199bc-134">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="199bc-135">Le certificat est responsable de l’authentification des serveurs dans Lync Server 2013, ainsi que de l’authentification auprès d’Exchange 2013 et de Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="199bc-135">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="199bc-136">Pour plus d’informations sur le fonctionnement de l’authentification serveur à serveur, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="199bc-136">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="199bc-137">Une différence très importante entre le processus d’authentification audio/vidéo et le processus d’authentification serveur à serveur est la durée de vie de l’authentification (jetons).</span><span class="sxs-lookup"><span data-stu-id="199bc-137">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="199bc-138">Pour l’authentification audio/vidéo, l’authentification expire au bout de huit heures.</span><span class="sxs-lookup"><span data-stu-id="199bc-138">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="199bc-139">L’authentification serveur à serveur a une durée de vie de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="199bc-139">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="199bc-140">Vous devez prendre les mesures qui conviennent pour chacun des types de certificat.</span><span class="sxs-lookup"><span data-stu-id="199bc-140">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="199bc-141">Nouveauté de Lync Server 2013, la possibilité de mettre en place un certificat d’authentification audio/vidéo de remplacement et un certificat d’authentification serveur à serveur avant l’expiration du certificat actuel.</span><span class="sxs-lookup"><span data-stu-id="199bc-141">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="199bc-142">Le nouveau certificat est ensuite utilisé pour générer de nouveaux jetons ou de nouvelles demandes d’authentification.</span><span class="sxs-lookup"><span data-stu-id="199bc-142">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="199bc-143">mais conserve l’ancien certificat pour vérifier les sessions et authentifications actuelles..</span><span class="sxs-lookup"><span data-stu-id="199bc-143">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="199bc-144">Cette action a pour effet d’empêcher presque toutes les défaillances dues à des expirations de jeton et de certificat.</span><span class="sxs-lookup"><span data-stu-id="199bc-144">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="199bc-145">Pour plus d’informations sur cette fonctionnalité et sur la façon de la configurer, voir [Staging AV and OAuth Certificates in Lync Server 2013 using-Rollback in set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="199bc-145">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="199bc-146">Dépendance réduite à l’égard de l’affinité basée sur les cookies</span><span class="sxs-lookup"><span data-stu-id="199bc-146">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="199bc-147">Dans les versions précédentes de Lync Server et Office Communications Server, l’affinité basée sur les cookies était utilisée par les services Web pour garantir la conservation de l’état de session des services Web et client.</span><span class="sxs-lookup"><span data-stu-id="199bc-147">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="199bc-148">Les services Web Lync Server 2013 utilisent un mécanisme d’affinité intégré qui élimine la plupart des exigences en matière d’affinité basée sur les cookies.</span><span class="sxs-lookup"><span data-stu-id="199bc-148">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="199bc-149">Le client mobile Microsoft Lync 2010 doit toujours utiliser l’affinité basée sur les cookies et nécessiter une configuration de l’affinité basée sur les cookies jusqu’à ce que vous ayez migré tous les clients vers le client Microsoft Lync mobile à venir (date de la publication non encore déterminée).</span><span class="sxs-lookup"><span data-stu-id="199bc-149">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="199bc-150">Pour plus d’informations sur l’affinité basée sur les cookies dans Lync Server 2013, voir [composants requis pour l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="199bc-150">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="199bc-151">Améliorations apportées à la découverte automatique</span><span class="sxs-lookup"><span data-stu-id="199bc-151">AutoDiscover Enhancements</span></span>

<span data-ttu-id="199bc-152">La fonctionnalité de découverte automatique dans Lync Server 2013 permet aux clients de localiser des fonctionnalités supplémentaires qui sont disponibles pour la communication.</span><span class="sxs-lookup"><span data-stu-id="199bc-152">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="199bc-153">Autodiscover a été introduit pour la première fois dans la mise à jour cumulative de Lync Server 2010 : novembre 2011 pour Mobility et Microsoft Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="199bc-153">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="199bc-154">La fonctionnalité de découverte automatique (également connue par les noms des enregistrements DNS LyncDiscover et LyncDiscoverInternal) permet aux clients de localiser et d’utiliser des services de mobilité (pour les clients mobiles Microsoft Lync 2010), Microsoft Lync Web App et Lync Web Scheduler, ainsi que les communications avec Microsoft Exchange Server et SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="199bc-154">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="199bc-155">La découverte automatique est installée normalement dans le cadre de la configuration et du déploiement de votre infrastructure et des serveurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="199bc-155">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="199bc-156">Le générateur de topologie et l’Assistant Déploiement Lync Server éliminent la plupart des tâches de configuration requises dans la mise à jour cumulative pour Lync Server 2010 : novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="199bc-156">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="199bc-157">Services pour les clients mobiles</span><span class="sxs-lookup"><span data-stu-id="199bc-157">Services for Mobile Clients</span></span>

<span data-ttu-id="199bc-158">Introduit dans la mise à jour cumulative de Lync Server 2010 : novembre 2011, services de mobilité dans Lync Server 2013 activer les téléphones mobiles exécutant Lync mobile et les périphériques tablettes à l’aide des appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence.</span><span class="sxs-lookup"><span data-stu-id="199bc-158">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="199bc-159">En outre, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler via le bureau, atteindre un seul numéro, messagerie vocale et notification d’appel en absence.</span><span class="sxs-lookup"><span data-stu-id="199bc-159">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="199bc-160">Les services de mobilité utilisent le proxy inverse et les services publiés qui sont déployés sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="199bc-160">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="199bc-161">Il est inutile d’apporter des modifications aux serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="199bc-161">No changes are required to Edge Servers.</span></span> <span data-ttu-id="199bc-162">Au minimum, vous avez besoin d’un SIP/TCP/5061from sortant du serveur exécutant le service Edge d’accès Lync Server.</span><span class="sxs-lookup"><span data-stu-id="199bc-162">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="199bc-163">Le rôle de directeur est facultatif</span><span class="sxs-lookup"><span data-stu-id="199bc-163">Director Role is Optional</span></span>

<span data-ttu-id="199bc-164">Le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé.</span><span class="sxs-lookup"><span data-stu-id="199bc-164">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="199bc-165">Il héberge toujours les services web, authentifie au préalable les demandes utilisateur entrantes et redirige les utilisateurs externes vers leur pool d’accueil.</span><span class="sxs-lookup"><span data-stu-id="199bc-165">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="199bc-166">En définissant le directeur d’un rôle recommandé sur un rôle facultatif, Microsoft n’a pas l’intention de diminuer la valeur du directeur.</span><span class="sxs-lookup"><span data-stu-id="199bc-166">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="199bc-167">L’objectif est de réduire le nombre de serveurs et d’autres exigences matérielles (par exemple, les programmes d’équilibrage de la charge matérielle pour le directeur) sans compromettre les fonctionnalités et les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="199bc-167">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="199bc-168">Étant donné que les serveurs frontaux peuvent effectuer le même travail que le directeur sans impact sur les services fournis, vous pouvez déployer des directeurs si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="199bc-168">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="199bc-169">Vous pouvez en toute sécurité exclure le directeur en toute confiance que les serveurs frontaux fourniront les mêmes services à la place d’un directeur.</span><span class="sxs-lookup"><span data-stu-id="199bc-169">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

