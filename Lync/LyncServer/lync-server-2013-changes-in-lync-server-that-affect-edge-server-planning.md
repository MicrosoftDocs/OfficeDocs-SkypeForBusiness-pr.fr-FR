---
title: "Lync Server 2013 : Modif. dans Lync Server affectant la plan. de serv. Edge"
TOCTitle: Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204965(v=OCS.15)
ms:contentKeyID: 49297443
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge

 

_**Dernière rubrique modifiée :** 2012-10-22_

Lync Server 2013 présente de nouvelles fonctionnalités qui étendent les fonctionnalités et les méthodes de communication offertes aux utilisateurs. Par ailleurs, Lync Server 2013 apporte des modifications à certains services existants afin de mieux intégrer et d’élargir les services disponibles dans votre organisation. Vous trouverez ci-dessous un résumé des modifications susceptibles d’avoir un impact sur vos opérations de planification et de déploiement des services fournis par le serveur Edge  Lync Server 2013.

## Prise en charge de l’adressage IPv6

Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services du serveur Edge. Si vous avez fourni des adresses IPv6 pour les interfaces en les configurant dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration serveur Edge en configurant les adresses IP dans le Générateur de topologie. Par ailleurs, le protocole XMPP (Extensible Messaging and Presence Protocol) prend en charge IPv6. Aucune configuration supplémentaire n’est requise. Si IPv6 est configuré dans la topologie, XMPP utilise IPv6 (au besoin).

Pour assurer la prise en charge de l’adressage IPv6 dans Lync Server 2013, il est également nécessaire de créer des enregistrements DNS (Domain Name System) qui doivent être découverts et résolus en adresse IPv6. DNS IPv6 utilise des enregistrements d’hôte définis sous la forme  **AAAA** et appelés « quad-A ». Les autres types d’enregistrements sont en accord avec leurs homologues IPv4.

## Prise en charge du déploiement XMPP (Extensible Messaging and Presence Protocol)

En guise de nouveauté, serveur Edge propose un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP (déployée sur vos serveurs frontaux). Vous pouvez déployer Fédération XMPP comme un composant facultatif. En ajoutant et en configurant le proxy XMPP et la passerelle XMPP, vous offrez à vos utilisateurs Microsoft Lync 2013 la possibilité d’ajouter des contacts de partenaires XMPP pour la messagerie instantanée et la présence.

> [!NOTE]  
> À l’heure actuelle, les services XMPP dans le serveur Edge assurent uniquement la messagerie instantanée et la présence entre les clients Lync Server et les contacts XMPP. En outre, XMPP est hébergé dans un seul site.

> [!IMPORTANT]  
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tiers pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.

## Prend en charge des certificats pour l’authentification audio/vidéo propagée et l’authentification serveur à serveur

Un certificat est utilisé pour générer des jetons émis aux clients et autres consommateurs du service d’authentication A/V et dans le cadre de l’authentification serveur à serveur. Le certificat d’authentification audio/vidéo est de type *AudioVideoAuthentication* , tandis que le certificat d’authentification serveur à serveur est de type *OAuthTokenIssuer* .

Pour l’authentification audio/vidéo, les jetons sont utilisés pour authentifier les demandes d’allocation de port, et les jetons sont mis en cache pendant la durée de vie par défaut du jeton (jusqu’à 8 heures). En fonctionnement normal, il s’agit d’une méthode très fiable pour créer et distribuer du matériel d’authentification aux consommateurs A/V. Cependant, les certificats ont une durée de vie limitée et expirent à une date et une heure prédéfinies (selon la date de création et les stratégies appliquées au niveau de l’autorité de certification ayant créé le certificat, en général deux ans pour ce type de certificat). Lorsque le certificat expire, les jetons créés par le certificat expiré et mis en cache par les consommateurs ne sont plus valides. Toute tentative d’utilisation d’un jeton créé avec un certificat expiré se traduit par l’échec des allocations du serveur relais multimédia et l’échec de toutes les sessions audio/vidéo actuelles. Le client doit alors acquérir un nouveau jeton créé par un certificat valide pour bénéficier à nouveau de fonctionnalités audio et vidéo normales.

L’authentification serveur à serveur est gérée par un certificat global demandé et appliqué à tous les serveurs du déploiement. Le certificat est responsable de l’authentification des serveurs dans Lync Server 2013, ainsi que de l’authentification pour Exchange 2013 et Microsoft SharePoint Server 2013. Pour plus d’informations sur le fonctionnement de l’authentification serveur à serveur, reportez-vous à [Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Une différence très importante entre le processus d’authentification audio/vidéo et le processus d’authentification serveur à serveur est la durée de vie de l’authentification (jetons). Pour l’authentification audio/vidéo, l’authentification expire après huit heures. L’authentification serveur à serveur a une durée de vie de 24 heures. Vous devez prendre les mesures qui conviennent pour chacun des types de certificat.

La possibilité de mettre en place un certificat d’authentification audio/vidéo et un certificat d’authentification serveur à serveur de remplacement avant l’expiration du certificat actuel est une nouveauté de Lync Server 2013. Le nouveau certificat est ensuite utilisé pour générer de nouveaux jetons ou de nouvelles demandes d’authentification, mais il conserve l’ancien certificat pour vérifier les sessions et authentifications actuelles. Cela permet d’empêcher efficacement la quasi-totalité des défaillances causées par les expirations de jetons et de certificats. Pour plus d’informations sur cette fonctionnalité et la façon de la configurer, reportez-vous à [Préparation de certificats AV et OAuth dans Lync Server 2013 à l’aide du paramètre -Roll dans l’applet de commande Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate).

## Dépendance réduite à l’égard de l’affinité basée sur les cookies

Dans les versions précédentes de Lync Server et de Office Communications Server, l’affinité basée sur les cookies était utilisée par les services web pour s’assurer que l’état de session du client et des services web était maintenu. Les services web Lync Server 2013 utilisent un mécanisme d’affinité intégré qui élimine la plupart des exigences relatives à l’affinité basée sur les cookies.

> [!WARNING]  
> Le client Microsoft Lync 2010 Mobile doit toujours utiliser l’affinité basée sur les cookies et requiert la configuration de l’affinité basée sur les cookies jusqu’à ce que vous ayez migré tous les clients vers le client Microsoft Lync Mobile à venir (dont la date de sortie n’est pas encore déterminée).

Pour plus d’informations sur l’affinité basée sur les cookies dans Lync Server 2013, reportez-vous à [Composants requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

## Améliorations apportées à la découverte automatique

La fonctionnalité de découverte automatique dans Lync Server 2013 permet aux clients de rechercher des fonctionnalités supplémentaires disponibles pour la communication. La découverte automatique a été introduite dans la mise à jour cumulative pour Lync Server 2010 de novembre 2011 pour la mobilité et Microsoft Lync 2010 Mobile. La fonctionnalité de découverte automatique (également connue sous les noms d’enregistrement DNS LyncDiscover et LyncDiscoverInternal) permet aux clients de rechercher et d’utiliser les services de mobilité (pour les clients Microsoft Lync 2010 Mobile), Microsoft Lync Web App et Lync Web Scheduler, ainsi que d’établir des communications avec Microsoft Exchange Server et SharePoint Server. La découverte automatique est installée dans le cadre normal de l’installation et du déploiement de votre infrastructure et de vos serveurs Lync Server 2013. Le Générateur de topologie et l’Assistant Déploiement de Lync Server éliminent la plupart des tâches de configuration requises dans la mise à jour cumulative pour Lync Server 2010 de novembre 2011.

## Services pour les clients mobiles

Introduits dans la mise à jour cumulative pour Lync Server 2010 de novembre 2011, les services de mobilité dans Lync Server 2013 permettent aux utilisateurs qui possèdent un téléphone mobile exécutant Lync Mobile ou une tablette ou appareil mobile Apple iOS, Android, Windows Phone ou Nokia pris en charge de s’adonner à des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et la notification des appels manqués.

> [!NOTE]  
> Les services de mobilité utilisent le proxy inverse et les services publiés déployés sur vos serveurs frontaux. Il est inutile d’apporter des modifications aux serveurs Edge. Vous avez besoin au minimum d’un accès SIP/TCP/5061 sortant à partir du serveur exécutant le service Edge d’accès Lync Server.

## Le rôle de directeur est facultatif

Le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé. Il héberge toujours les services web, authentifie au préalable les demandes utilisateur entrantes et redirige les utilisateurs externes vers leur pool d’accueil. En affectant au directeur un rôle facultatif à la place d’un rôle recommandé, Microsoft n’envisage pas de diminuer la valeur du directeur. L’intention est de réduire le nombre de serveurs et d’assouplir la configuration matérielle requise (par exemple, les équilibreurs de la charge matérielle pour le directeur) sans compromettre les caractéristiques et les fonctionnalités. Du fait que les serveurs frontaux peuvent accomplir le même travail que le directeur, sans impact sur les services fournis, vous pouvez déployer des directeurs si vous le souhaitez. Vous pouvez en toute sécurité exclure le directeur avec la certitude que les serveurs frontaux offriront les mêmes services qu’un directeur.

