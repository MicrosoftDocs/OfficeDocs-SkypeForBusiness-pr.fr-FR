---
title: 'Lync Server 2013 : Modifications apportées dans Lync Server affectant la planification de serveurs Edge'
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
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Lync Server 2013 introduit de nouvelles fonctionnalités qui étendent les fonctionnalités et méthodes de communication pour vos utilisateurs. Par ailleurs, Lync Server 2013 introduit des modifications apportées aux services existants pour améliorer l’intégration et l’extension des services disponibles pour votre organisation. Vous trouverez ci-dessous un résumé des modifications qui peuvent affecter votre planification et le déploiement de Lync Server 2013 Edge Server services.

<div>

## <a name="support-for-ipv6-addressing"></a>Prise en charge de l’adressage IPv6

Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services Edge Server. Si vous avez fourni des adresses IPv6 pour les interfaces via une configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge via la configuration d’adresse IP dans le générateur de topologie. Par ailleurs, le protocole XMPP (extensible Messaging and Presence Protocol) prend en charge le protocole IPv6. Aucune configuration supplémentaire n’est requise. Si le protocole IPv6 est configuré dans la topologie, XMPP utilisera le protocole IPv6 (le cas échéant).

La configuration requise pour la prise en charge du protocole IPv6 dans Lync Server 2013 consiste à créer des enregistrements DNS pour les enregistrements qui doivent être identifiés et résolus à une adresse IPv6. Le DNS IPv6 utilise des enregistrements d’hôte définis comme **aaaa** et appelé « quadruple A ». Les autres types d’enregistrements sont conformes aux équivalents IPv4.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Prise en charge du déploiement de protocoles de messagerie extensible et de présence

Edge Server introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP (déployée sur votre serveur principal). Vous pouvez déployer la Fédération XMPP en tant que composant facultatif. En ajoutant et en configurant le proxy XMPP et la passerelle XMPP, vous pouvez permettre aux utilisateurs de Microsoft Lync 2013 d’ajouter des contacts des partenaires de XMPP pour la messagerie instantanée et la présence.

<div>


> [!NOTE]  
> Pour l’instant, les services XMPP dans Edge Server fournissent uniquement la messagerie instantanée et la présence entre des clients Lync Server et des contacts de type XMPP. Par ailleurs, XMPP est hébergé sur un seul site.



</div>

<div>


> [!IMPORTANT]  
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Prise en charge de l’authentification audio et vidéo et des certificats d’authentification de serveur à serveur

Un certificat est utilisé pour générer des jetons émis pour les clients et d’autres utilisateurs du service d’authentification A/V et de l’authentification serveur à serveur. Le certificat d’authentification audio/vidéo est de type *AudioVideoAuthentication* et le certificat d’authentification serveur à serveur est de type *OAuthTokenIssuer*.

Pour l’authentification audio et vidéo, les jetons sont utilisés pour authentifier les demandes d’attribution de port, et les jetons sont mis en cache pendant 8 heures maximum par défaut (durée de vie par défaut du jeton). En fonctionnement normal, il s’agit d’une méthode très fiable permettant de créer et de distribuer des ressources d’authentification aux consommateurs A/V. Toutefois, les certificats ont une durée de vie limitée et arrivent à expiration sur une date et une heure prédéfinies (en fonction de la date de création et des stratégies mises en œuvre dans l’autorité de certification qui a créé le certificat, généralement 2 ans pour ce type de certificat). Lorsque le certificat expire, tout jeton créé par le certificat expiré et mis en cache par les consommateurs devient incorrect. Toute tentative d’utilisation d’un jeton créé avec un certificat arrivé à expiration entraînait l’échec des allocations de relais de média et des sessions audio/vidéo actuelles. Le client doit acquérir un nouveau jeton créé par un certificat valide pour reprendre les fonctionnalités audio et vidéo normales.

L’authentification de serveur à serveur est gérée par un certificat global demandé et appliqué à tous les serveurs du déploiement. Le certificat est chargé d’authentifier les serveurs dans Lync Server 2013 et d’s’authentifier auprès d’Exchange 2013 et de Microsoft SharePoint Server 2013. Pour plus d’informations sur le fonctionnement de l’authentification de serveur à serveur, voir [gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Une différence très importante entre le processus d’authentification audio et vidéo et le processus d’authentification de serveur à serveur est la durée de vie de l’authentification ou des jetons. Pour l’authentification audio et vidéo, l’authentification expire au bout de huit heures. L’authentification de serveur à serveur a une durée de vie de 24 heures. Vous devez planifier en conséquence pour chacun des types de certificats.

La nouvelle version de Lync Server 2013 est la possibilité de définir un certificat d’authentification audio/vidéo de remplacement, ainsi que le certificat d’authentification serveur et serveur à l’avance de l’expiration du certificat actuel. Le nouveau certificat est ensuite utilisé pour générer de nouveaux jetons ou de nouvelles demandes d’authentification. mais conserve l’ancien certificat pour vérifier les sessions et les authentifications actuelles. Ce qu’il faut faire est d’empêcher presque toutes les échecs en raison de l’expiration des jetons et des certificats. Pour plus d’informations sur cette fonctionnalité et la façon de configurer celle-ci, reportez-vous à la rubrique [mise en place des certificats d’audiovisuel et de certification OAuth dans Lync Server 2013 avec l’option Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Dépendance réduite de l’affinité basée sur les cookies

Dans les versions précédentes de Lync Server et Office Communications Server, l’affinité basée sur les cookies a été utilisée par les services Web pour garantir la conservation de l’état de la session du client et du service Web. Lync Server 2013 Web Services utilise un mécanisme d’affinité intégré qui élimine la plupart des exigences relatives à l’affinité basée sur les cookies.

<div>


> [!WARNING]  
> Le client mobile Microsoft Lync 2010 doit toujours utiliser une affinité basée sur les cookies et nécessite une configuration de l’affinité basée sur les cookies tant que vous n’avez pas migré tous les clients vers le client Microsoft Lync mobile à venir (date de publication non encore déterminée).



</div>

Pour plus d’informations sur l’affinité basée sur les cookies dans Lync Server 2013, voir [composants requis pour l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Améliorations apportées à la découverte automatique

La fonctionnalité de découverte automatique de Lync Server 2013 permet aux clients de trouver des fonctionnalités supplémentaires mises à disposition pour la communication. La découverte automatique a été introduite pour la première fois dans la mise à jour cumulative pour Lync Server 2010:2011 novembre pour mobilité et Microsoft Lync 2010 mobile. La fonctionnalité de découverte automatique (également connue sous le nom d’enregistrement DNS LyncDiscover et LyncDiscoverInternal) permet aux clients de rechercher et d’utiliser les services de mobilité (pour les clients mobiles Microsoft Lync 2010), Microsoft Lync Web App et Lync Web Scheduler, ainsi que communications avec Microsoft Exchange Server et SharePoint Server. La découverte automatique est installée normalement dans le cadre de l’installation et du déploiement de vos serveurs d’infrastructure et Lync Server 2013. Le générateur de topologie et l’Assistant Déploiement de Lync Server éliminent la plupart des tâches de configuration requises dans la mise à jour cumulative pour Lync Server 2010 : novembre 2011.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Services pour les clients mobiles

Introduction à la mise à jour cumulative pour Lync Server 2010 2011 : les services de mobilité de Lync Server 2013 permettent des téléphones mobiles exécutant des appareils mobiles et tablettes Lync utilisant des appareils mobiles Apple iOS, Android, Windows Phone ou Nokia. activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, par exemple, cliquer pour participer à une conférence, appeler par le biais de votre bureau, joindre un numéro de téléphone unique et envoyer une notification d’appel manqué.

<div>


> [!NOTE]  
> Les services de mobilité utilisent le proxy inverse et les services publiés déployés sur vos serveurs frontaux. Aucune modification n’est requise sur les serveurs de périphérie. Vous avez besoin d’un SIP/TCP/5061from sortant du serveur exécutant le service Edge d’accès de Lync Server.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>Le rôle de directeur est facultatif

Le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé. Il héberge toujours les services Web, préauthentifie les demandes des utilisateurs entrantes, et redirige les utilisateurs externes vers leur liste de démarrage. Le fait de changer le directeur d’un rôle recommandé en rôle facultatif consiste à ne pas diminuer la valeur du directeur. L’intention est de réduire le nombre de serveurs et les autres exigences matérielles (par exemple, les équilibreurs de charge matérielle pour le directeur) sans compromettre les fonctionnalités et fonctionnalités. Étant donné que les serveurs front-end peuvent faire la même chose que le directeur sans avoir d’impact sur les services fournis, vous pouvez déployer des directeurs si vous le souhaitez. Vous pouvez exclure en toute sécurité le directeur en ayant confiance aux serveurs frontaux pour proposer les mêmes services à la place d’un directeur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

