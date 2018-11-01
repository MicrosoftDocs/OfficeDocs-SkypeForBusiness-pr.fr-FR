---
title: 'Lync Server 2013 : Configuration des serveurs proxy inverses'
TOCTitle: Configuration des serveurs proxy inverses
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398069(v=OCS.15)
ms:contentKeyID: 49296055
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des serveurs proxy inverses pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour les déploiements de serveurs Edge Microsoft Lync Server 2013, il est nécessaire de prévoir un proxy HTTPS inverse dans le réseau de périmètre pour que les clients externes puissent accéder aux services web Lync Server 2013 (appelés *composants web* dans Office Communications Server) sur le directeur et le pool d’accueil de l’utilisateur. Les fonctionnalités qui nécessitent un accès externe via un proxy inverse sont les suivantes :

  - Permettre aux utilisateurs externes de télécharger le contenu de vos réunions

  - Permettre aux utilisateurs externes de développer des groupes de distribution

  - Permettre aux utilisateurs distants de télécharger des fichiers du Service de carnet d’adresses

  - Accès au client Lync Web App

  - Accès à la page web des paramètres de conférence rendez-vous

  - Permettre aux périphériques externes de se connecter au service web de mise à jour des périphériques et d’obtenir des mises à jour

  - Permettre aux applications mobiles de découvrir et d’utiliser automatiquement des URL de mobilité (Mcx) depuis Internet

  - Permettre au client Lync 2013, à application Lync du Windows Store et au client mobile Lync 2013 de rechercher les URL de découverte Lync (découverte automatique) et d’utiliser l’API Web Communications unifiées (UCWA).

Nous vous recommandons de configurer le proxy inverse HTTP de sorte qu’il publie tous les services web dans tous les pools. Par exemple, la publication de https:// *ExternalFQDN* /\* permet de publier tous les répertoires virtuels des services Internet (IIS) d’un pool. Une règle de publication est nécessaire pour chaque serveur Standard Edition, pool de serveurs frontaux, directeur ou pool de directeurs dans votre organisation.

En outre, vous devez publier les URL simples. Si l’organisation dispose d’un directeur ou d’un pool de directeurs, le proxy inverse HTTP écoute les requêtes HTTP/HTTPS vers les URL simples et les redirige via proxy vers le répertoire virtuel externe des services web sur le directeur ou le pool de directeurs. Si vous n’avez pas déployé de directeur, vous devez désigner un pool pour traiter les requêtes transmises aux URL simples. (S’il ne s’agit pas du pool d’accueil de l’utilisateur, le proxy redirigera ces requêtes vers les services web sur le pool d’accueil de l’utilisateur). Les URL simples peuvent être traitées par une règle de publication web pour le directeur. Vous devez également publier l’URL du service de découverte automatique externe.

Vous pouvez utiliser Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 ou Internet Information Server 7.0, 7.5 ou 8.0 avec Application Request Routing (IIS ARR) comme proxy inverse. Les étapes détaillées dans cette section décrivent comment configurer Forefront Threat Management Gateway 2010. Les étapes de configuration d’ISA Server 2006 sont presque identiques. Des instructions sont également disponibles pour IIS ARR. Si vous utilisez un autre proxy inverse, consultez la documentation du produit et associez les conditions définies ici aux fonctions correspondantes dans le proxy inverse.

> [!IMPORTANT]  
> Internet Information Server Application Request Routing (IIS ARR) est une option entièrement testée et prise en charge d’implémentation d’un proxy inverse pour Lync Server 2010 et Lync Server 2013. Depuis novembre 2012, Microsoft ne vend plus de licences ForeFront Threat Management Gateway 2010 (TMG). TMG reste entièrement pris en charge et peut être inclus sur des ordinateurs vendus par des tiers. Par ailleurs, plusieurs équilibreurs de charge et pare-feux prennent en charge les proxys inverses. Pour les connaître, contactez votre fournisseur pour obtenir des instructions spécifiques sur la configuration de son produit afin de prendre en charge les proxys inverses pour Lync Server. Vous pouvez également consulter la liste des tiers ayant transmis la documentation relative à leur produit à Microsoft. La prise en charge est assurée par le tiers pour sa solution. Pour consulter la liste des tiers proposant des solutions, reportez-vous à <a href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync (Infrastructure agréée pour Microsoft Lync)</a>.

Les rubriques et les procédures suivantes utilisent Forefront Threat Management Gateway 2010 et IIS ARR comme base des procédures de déploiement et de configuration.

  - [Configuration des noms de domaine complets d’une batterie de serveurs web pour Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configuration des cartes réseau dans Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Demande et configuration d’un certificat pour votre proxy HTTP inverse dans Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configuration des règles de publication web pour un pool interne unique dans Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Création des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Vérification de l’accès avec le proxy inverse dans Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

## Avant de commencer

Pour déployer Forefront Threat Management Gateway 2010 en tant que proxy inverse, vous devez installer et configurer un serveur en vous conformant aux conditions préalables et à la configuration matérielle requise définies dans la documentation de Forefront Threat Management Gateway 2010. Consultez les rubriques suivantes pour configurer correctement le matériel et installer Forefront Threat Management Gateway 2010 sur le serveur avant de commencer.

  - [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - [Recommandations sur le matériel de Forefront TMG 2010](http://go.microsoft.com/fwlink/?linkid=291293)

Pour déployer correctement IIS ARR comme proxy inverse, consultez les rubriques suivantes pour configurer le matériel et les logiciels prérequis.

  - Pour installer les services Internet (IIS) sur Windows Server 2008 ou Windows Server 2008 R2, reportez-vous à [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2 (Installation des services Internet (IIS) 7 sur Windows Server 2008 ou Windows Server 2008 R2)](http://go.microsoft.com/fwlink/?linkid=291296)

  - Pour installer les services Internet (IIS) sur Windows Server 2012, reportez-vous à [Installing IIS 8 on Windows Server 2012 (Installation des services Internet (IIS) 8 sur Windows Server 2012)](http://go.microsoft.com/fwlink/?linkid=291297)

  - Pour installer les services Internet (IIS) sur Windows Server 2012 R2, reportez-vous à [Installing IIS 8.5 on Windows Server 2012 R2 (Installation des services Internet (IIS) 8.5 sur Windows Server 2012 R2)](http://go.microsoft.com/fwlink/?linkid=330687)

  - Pour télécharger l’extension Application Request Routing pour les services Internet (IIS), suivez les instructions de la page [Application Request Routing v2.5 Download (Téléchargement d’Application Request Routing v2.5)](http://go.microsoft.com/fwlink/?linkid=291298)

  - Pour installer ARR, reportez-vous aux instructions de la page [Install Application Request Routing Version 2 (Installation d’Application Request Routing Version 2)](http://go.microsoft.com/fwlink/?linkid=291299)
    
  > [!NOTE]  
  > Les instructions publiées actuellement concernent ARR 2.0. La procédure d’installation de cette version et de l’extension sont identiques.
