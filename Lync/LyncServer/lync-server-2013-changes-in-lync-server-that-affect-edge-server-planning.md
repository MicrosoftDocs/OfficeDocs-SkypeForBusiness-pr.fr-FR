---
title: 'Lync Server 2013 : modifications apportées dans Lync Server affectant la planification des serveurs Edge'
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
ms.openlocfilehash: c859df611ea2ad33b36bb7392dfcf2e2b9c5ae94
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Modifications apportées dans Lync Server 2013 affectant la planification des serveurs Edge

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Lync Server 2013 introduit de nouvelles fonctionnalités qui étendent les fonctionnalités et les méthodes de communication pour vos utilisateurs. De plus, Lync Server 2013 introduit les modifications apportées aux services existants afin d’améliorer l’intégration et l’extension des services disponibles pour votre organisation. Vous trouverez ci-dessous un résumé des modifications susceptibles d’avoir un impact sur la planification et le déploiement des services de serveur Edge Lync Server 2013.

<div>

## <a name="support-for-ipv6-addressing"></a>Prise en charge de l’adressage IPv6

Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services de serveur Edge. Si vous avez fourni des adresses IPv6 pour les interfaces par le biais de la configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge par le biais de la configuration d’adresse IP dans le générateur de topologie. Par ailleurs, le protocole XMPP (Extensible Messaging and Presence Protocol) prend en charge IPv6. Aucune configuration supplémentaire n’est requise. Si IPv6 est configuré dans la topologie, XMPP utilise IPv6 (au besoin).

Une configuration requise supplémentaire pour prendre en charge IPv6 dans Lync Server 2013 consiste à créer des enregistrements DNS pour les enregistrements qui doivent être découverts et résolus en adresse IPv6. DNS IPv6 utilise des enregistrements d’hôte qui sont définis sous la forme **AAAA** et qui sont appelés « quad-A ». Les autres types d’enregistrements sont en accord avec leurs homologues IPv4.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Prise en charge du déploiement XMPP (Extensible Messaging and Presence Protocol)

Le serveur Edge introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP (déployé sur vos serveurs frontaux). Vous pouvez déployer Fédération XMPP comme un composant facultatif. En ajoutant et en configurant le proxy XMPP et la passerelle XMPP, vous pouvez permettre à vos utilisateurs Microsoft Lync 2013 d’ajouter des contacts à partir de partenaires XMPP pour la messagerie instantanée et la présence.

<div>


> [!NOTE]  
> Actuellement, les services XMPP du serveur Edge fournissent uniquement la messagerie instantanée et la présence entre les clients Lync Server et les contacts XMPP. En outre, XMPP est hébergé dans un seul site.



</div>

<div>


> [!IMPORTANT]  
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Prend en charge des certificats pour l’authentification audio/vidéo propagée et l’authentification serveur à serveur

Un certificat est utilisé pour générer des jetons qui sont émis aux clients et autres consommateurs du service d’authentication A/V et dans le cadre de l’authentification serveur à serveur. Le certificat d’authentification audio/vidéo est de type *AudioVideoAuthentication*, tandis que le certificat d’authentification serveur à serveur est de type *OAuthTokenIssuer*.

Pour l’authentification audio/vidéo, les jetons sont utilisés pour authentifier les demandes d’allocation de port, et les jetons sont mis en cache pendant la durée de vie par défaut du jeton (jusqu’à 8 heures). En fonctionnement normal, il s’agit d’une méthode très fiable pour créer et distribuer du matériel d’authentification aux consommateurs A/V. Toutefois, les certificats ont une durée de vie limitée et expirent à une date et une heure prédéfinies (selon la date de création et les stratégies appliquées au niveau de l’autorité de certification ayant créé le certificat, en général deux ans pour ce type de certificat). Lorsque le certificat expire, les jetons créés par le certificat expiré et mis en cache par les consommateurs ne sont plus valides. Toute tentative d’utilisation d’un jeton créé avec un certificat expiré se traduit par l’échec des allocations du serveur relais multimédia et l’échec de toutes les sessions audio/vidéo actuelles. Le client doit alors acquérir un nouveau jeton créé par un certificat valide pour bénéficier à nouveau de fonctionnalités audio et vidéo normales.

L’authentification serveur à serveur est gérée par un certificat global qui est demandé et appliqué à tous les serveurs du déploiement. Le certificat est responsable de l’authentification des serveurs dans Lync Server 2013, ainsi que de l’authentification auprès d’Exchange 2013 et de Microsoft SharePoint Server 2013. Pour plus d’informations sur le fonctionnement de l’authentification serveur à serveur, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Une différence très importante entre le processus d’authentification audio/vidéo et le processus d’authentification serveur à serveur est la durée de vie de l’authentification (jetons). Pour l’authentification audio/vidéo, l’authentification expire au bout de huit heures. L’authentification serveur à serveur a une durée de vie de 24 heures. Vous devez prendre les mesures qui conviennent pour chacun des types de certificat.

Nouveauté de Lync Server 2013, la possibilité de mettre en place un certificat d’authentification audio/vidéo de remplacement et un certificat d’authentification serveur à serveur avant l’expiration du certificat actuel. Le nouveau certificat est ensuite utilisé pour générer de nouveaux jetons ou de nouvelles demandes d’authentification. mais conserve l’ancien certificat pour vérifier les sessions et authentifications actuelles.. Cette action a pour effet d’empêcher presque toutes les défaillances dues à des expirations de jeton et de certificat. Pour plus d’informations sur cette fonctionnalité et sur la façon de la configurer, voir [Staging AV and OAuth Certificates in Lync Server 2013 using-Rollback in set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Dépendance réduite à l’égard de l’affinité basée sur les cookies

Dans les versions précédentes de Lync Server et Office Communications Server, l’affinité basée sur les cookies était utilisée par les services Web pour garantir la conservation de l’état de session des services Web et client. Les services Web Lync Server 2013 utilisent un mécanisme d’affinité intégré qui élimine la plupart des exigences en matière d’affinité basée sur les cookies.

<div>


> [!WARNING]  
> Le client mobile Microsoft Lync 2010 doit toujours utiliser l’affinité basée sur les cookies et nécessiter une configuration de l’affinité basée sur les cookies jusqu’à ce que vous ayez migré tous les clients vers le client Microsoft Lync mobile à venir (date de la publication non encore déterminée).



</div>

Pour plus d’informations sur l’affinité basée sur les cookies dans Lync Server 2013, voir [composants requis pour l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Améliorations apportées à la découverte automatique

La fonctionnalité de découverte automatique dans Lync Server 2013 permet aux clients de localiser des fonctionnalités supplémentaires qui sont disponibles pour la communication. Autodiscover a été introduit pour la première fois dans la mise à jour cumulative de Lync Server 2010 : novembre 2011 pour Mobility et Microsoft Lync 2010 mobile. La fonctionnalité de découverte automatique (également connue par les noms des enregistrements DNS LyncDiscover et LyncDiscoverInternal) permet aux clients de localiser et d’utiliser des services de mobilité (pour les clients mobiles Microsoft Lync 2010), Microsoft Lync Web App et Lync Web Scheduler, ainsi que communications avec Microsoft Exchange Server et SharePoint Server. La découverte automatique est installée normalement dans le cadre de la configuration et du déploiement de votre infrastructure et des serveurs Lync Server 2013. Le générateur de topologie et l’Assistant Déploiement Lync Server éliminent la plupart des tâches de configuration requises dans la mise à jour cumulative pour Lync Server 2010 : novembre 2011.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Services pour les clients mobiles

Introduit dans la mise à jour cumulative de Lync Server 2010 : novembre 2011, services de mobilité dans Lync Server 2013 activer les téléphones mobiles exécutant Lync mobile et les appareils tablettes à l’aide des appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour effectuer activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler via le bureau, atteindre un seul numéro, messagerie vocale et notification d’appel en absence.

<div>


> [!NOTE]  
> Les services de mobilité utilisent le proxy inverse et les services publiés qui sont déployés sur vos serveurs frontaux. Il est inutile d’apporter des modifications aux serveurs Edge. Au minimum, vous avez besoin d’un SIP/TCP/5061from sortant du serveur exécutant le service Edge d’accès Lync Server.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>Le rôle de directeur est facultatif

Le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé. Il héberge toujours les services web, authentifie au préalable les demandes utilisateur entrantes et redirige les utilisateurs externes vers leur pool d’accueil. En définissant le directeur d’un rôle recommandé sur un rôle facultatif, Microsoft n’a pas l’intention de diminuer la valeur du directeur. L’objectif est de réduire le nombre de serveurs et d’autres exigences matérielles (par exemple, les programmes d’équilibrage de la charge matérielle pour le directeur) sans compromettre les fonctionnalités et les fonctionnalités. Étant donné que les serveurs frontaux peuvent effectuer le même travail que le directeur sans impact sur les services fournis, vous pouvez déployer des directeurs si vous le souhaitez. Vous pouvez en toute sécurité exclure le directeur en toute confiance que les serveurs frontaux fourniront les mêmes services à la place d’un directeur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

