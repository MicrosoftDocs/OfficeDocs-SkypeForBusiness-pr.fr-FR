---
title: "Lync Server 2013 : Conf. req. et autor. pour la conf. de conférence rdv"
TOCTitle: Configuration requise et autorisations pour la configuration de conférence rendez-vous
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412865(v=OCS.15)
ms:contentKeyID: 49298592
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise et autorisations pour la configuration de conférence rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-20_

La fonction de conférence rendez-vous est un composant facultatif de la charge de travail Conférence de Lync Server 2013. Les composants à installer avant de pouvoir configurer la conférence rendez-vous sont déployés lorsque vous utilisez le Générateur de topologie pour créer votre topologie et que vous installez ensuite votre pool frontal ou votre serveur Standard Edition. Cette rubrique décrit les étapes à accomplir avant de pouvoir configurer la conférence rendez-vous.

Elle suppose que vous avez pris connaissance des sections de planification liées à la charge de travail Conférence et en particulier à la conférence rendez-vous.

## Conditions préalables à la configuration de la conférence rendez-vous

La conférence rendez-vous nécessite les composants Lync Server 2013 suivants :

  - service d’application de communications unifiées (UCAS), désigné par *Service d’application*

  - application Intendant Conférence

  - application d’annonce de conférence

  - page web Paramètres de conférence rendez-vous

  - au moins un serveur de médiation Lync Server 2013 et une passerelle RTC

Vous déployez ces composants lorsque vous utilisez le Générateur de topologie pour définir et publier votre topologie et que vous déployez ensuite un pool frontal ou un serveur Standard Edition. Si vous déployez Voix Entreprise, vous devez le faire avant de configurer la conférence rendez-vous. Si vous ne déployez pas Voix Entreprise, vous pouvez déployer un serveur de médiation et une passerelle de réseau téléphonique commuté (RTC) lorsque vous déployez votre pool frontal ou votre serveur Standard Edition.

> [!NOTE]  
> Si vous effectuez la mise à niveau d’Office Communications Server 2007 R2 vers Lync Server 2013, déployez la conférence rendez-vous dans chaque pool que vous souhaitez utiliser pour héberger des conférences Lync Server 2013. Pour plus d’informations sur la migration de la conférence rendez-vous, reportez-vous à <a href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration d’Office Communications Server 2007 R2 vers Lync Server 2013</a>.

Cette section suppose que vous avez :

  - appliqué les dernières mises à jour à votre environnement Office Communications Server 2007 R2, si vous effectuez une migration vers Lync Server 2013 ;

  - utilisé le Générateur de topologie pour créer et configurer votre topologie. Lors de la spécification de votre charge de travail Conférence, vous avez sélectionné l’option de conférence rendez-vous. Pour plus d’informations sur la définition de votre topologie, reportez-vous à [Définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) dans la documentation de déploiement ;

  - publié votre topologie et configuré le pool frontal ou le serveur Standard Edition. Pour plus d’informations sur la publication de la topologie et l’installation de Lync Server 2013, reportez-vous à [Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.
    
    > [!NOTE]  
    > Lorsque vous installez votre topologie publiée, la page web Paramètres de conférence rendez-vous est installée sur le serveur frontal ou le serveur Standard Edition dans le cadre des services web.    
    > [!IMPORTANT]  
    > Si vous modifiez le chemin d’accès du magasin de fichiers dans le Générateur de topologie après le déploiement de Lync Server 2013, vous devez redémarrer les applications Intendant Conférence et Annonce de conférence pour utiliser le nouveau chemin d’accès.

  - déployé Voix Entreprise. Si vous ne déployez pas Voix Entreprise, vous avez soit colocalisé un serveur de médiation sur le serveur frontal Entreprise Edition ou sur le serveur Standard Edition, soit déployé un serveur de médiation autonome, et vous avez déployé une passerelle RTC. Pour plus d’informations sur le déploiement de Voix Entreprise, reportez-vous à [Déploiement de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement. Pour plus d’informations sur l’installation d’un serveur de médiation et d’une passerelle RTC autonomes, reportez-vous à [Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) dans la documentation de déploiement.

Le graphique suivant présente les étapes à effectuer avant de pouvoir configurer la conférence rendez-vous, ainsi que celles permettant de configurer la conférence rendez-vous.

**Déploiement de la conférence rendez-vous**

![Organigramme de déploiement de conférence rendez-vous](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Organigramme de déploiement de conférence rendez-vous")

## Autorisations de la conférence rendez-vous

Pour configurer la conférence rendez-vous, vous devez utiliser les outils d’administration suivants :

  - Panneau de configuration Lync Server 2013

  - Lync Server Management Shell

Ces outils permettent de configurer les paramètres de conférence rendez-vous ainsi que les plans de numérotation, les stratégies et les autres paramètres nécessaires à la conférence rendez-vous.

La configuration de la conférence rendez-vous nécessite l’un des rôles administratifs suivants, selon la tâche :

  - **CsVoiceAdministrator**   Ce rôle administratif permet de créer, configurer et gérer les stratégies et les paramètres liés à la voix.

  - **CsUserAdministrator**   Ce rôle administratif permet d’activer et de désactiver des utilisateurs pour Lync Server et d’affecter des stratégies existantes aux utilisateurs, telles que les stratégies de conférence et les stratégies de code confidentiel.

  - **CsAdministrator**   Ce rôle administratif permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.

## Voir aussi

#### Concepts

[Déploiement de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)

