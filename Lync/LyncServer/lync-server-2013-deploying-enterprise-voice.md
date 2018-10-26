---
title: 'Lync Server 2013 : Déploiement de Voix Entreprise'
TOCTitle: Déploiement de Voix Entreprise
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412876(v=OCS.15)
ms:contentKeyID: 49298593
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement de Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-03_

Le Lync Server 2013Voix Entreprise fait partie de l’infrastructure Lync Server 2013.

Le déploiement de Voix Entreprise requiert de vous les opérations suivantes :

1.  passez en revue la section [Planification de Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) de la documentation de planification ;

2.  finaliser les plans pour les fonctionnalités et les composants à déployer avec cette charge de travail ;

3.  exécuter l’outil de planification pour créer une topologie correspondant à vos décisions de déploiement ;

4.  ouvrir la conception de topologie dans le Générateur de topologie, comme décrit dans la rubrique [Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) de la documentation de déploiement.
    
    > [!NOTE]  
    > L’installation du Générateur de topologie fait partie du processus de déploiement pour le pool interne. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-install-lync-server-administrative-tools.md">Installation des outils d’administration Lync Server 2013</a> dans la documentation de déploiement.

De plus, vous devez au préalable avoir déployé Lync Server Entreprise Edition au niveau du site central et des sites de succursale correspondant à la topologie de référence que vous choisissez de déployer. Pour déployer des composants Voix Entreprise, vous devez d’abord définir, publier et installer des fichiers pour au moins un pool interne, et vous devez utiliser le Générateur de topologie pour définir et publier un pool interne.

Pour consulter des topologies de référence avec des exemples de déploiement possible des rôles de serveur Voix Entreprise (ainsi que leur relation entre eux et avec d’autres rôles de serveur Lync Server 2013), reportez-vous à [Topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification.

Pour consulter une topologie de référence qui illustre et explique un exemple de déploiement du contrôle d’admission des appels, y compris les régions réseau, les sites réseau et les sous-réseaux, reportez-vous à [Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.

> [!IMPORTANT]  
> Pour déployer Voix Entreprise au niveau d’un site central, poursuivez la lecture des rubriques de cette section. Pour déployer Voix Entreprise au niveau d’un site de succursale, passez à la rubrique <a href="lync-server-2013-deploying-branch-sites.md">Déploiement de sites de succursale dans Lync Server 2013</a> dans la documentation de déploiement.

Cette section comprend des procédures pour les déploiements dans lesquels un serveur de médiation est colocalisé sur chaque serveur frontal ou serveur Standard Edition, comme recommandé, ainsi que pour les déploiements avec un pool de serveurs de médiation autonome.

Vous pouvez ignorer le contenu suivant si vous avez utilisé le Générateur de topologie pour définir et publier une topologie qui colocalise un serveur de médiation sur chaque serveur frontal ou serveur Standard Edition, car l’Assistant Déploiement a déjà installé automatiquement les fichiers pour le serveur de médiation lors de l’installation des fichiers pour le pool de serveurs frontaux ou le serveur Standard Edition Server :

  - [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md)

Si vous avez utilisé le Générateur de topologie pour définir et publier un serveur de médiation dans un pool autonome, vous pouvez utiliser le contenu suivant :

  - Vérifiez que votre topologie remplit les conditions préalables de logiciel et d’environnement, telles que décrites dans [Configuration requise de Voix Entreprise pour Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

## Dans cette section

  -   
    [Configuration requise de Voix Entreprise pour Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  -   
    [Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  -   
    [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md)

  -   
    [Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  -   
    [Configuration des stratégies de voix, des enregistrements d’utilisation du RTC et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  -   
    [Exportation et importation de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  -   
    [Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

  -   
    [Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  -   
    [Déploiement de la messagerie unifiée Exchange locale pour fournir la messagerie vocale Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  -   
    [Mise à disposition de la messagerie vocale Lync Server 2013 aux utilisateurs sur la messagerie unifiée Exchange hébergée](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  -   
    [Configuration de l’intégration de Lync Server 2013 local avec Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  -   
    [Déploiement des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [À propos des régions réseau, des sites réseau et des sous-réseaux dans Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Création ou modification d’une région réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Configuration du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Configuration d’Enhanced 9-1-1 dans Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Configuration de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  -   
    [Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

## Voir aussi

#### Autres ressources

[Déploiement de sites de succursale dans Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Configuration de conférences rendez-vous dans Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Configuration du parcage d’appel dans Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Configuration des annonces pour les numéros non affectés dans Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Déploiement du serveur de surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)

