---
title: Nouveautés de Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype Entreprise Server 2015. Pour plus d’informations sur la nouvelle expérience client, voir Lync est désormais Skype Entreprise - découvrez les nouveautés.'
ms.openlocfilehash: 09774f722020ef750ae16ad01a29873d43d25e76
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827584"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Nouveautés de Skype Entreprise Server 2015

**Résumé :** Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype Entreprise Server 2015. Pour plus d’informations sur la nouvelle expérience client, voir [Lync est](https://go.microsoft.com/fwlink/p/?LinkId=529022)désormais Skype Entreprise - voir les nouveautés.
  
Lync est désormais Skype Entreprise, une plateforme de communication et de collaboration qui regroupe une expérience s’inspire de Skype avec la sécurité, la conformité et le contrôle de qualité professionnelle de Lync. Skype Entreprise offre des fonctionnalités, notamment la présence, la messagerie instantanée, les appels vocaux et vidéo et les réunions en ligne. Skype Entreprise offre une nouvelle expérience client, une nouvelle version de serveur et des mises à jour du service dans Microsoft 365 ou Office 365. Si les utilisateurs de votre organisation sont déjà familiarisés avec Skype, ils apprécieront la puissance et la simplicité de Skype Entreprise, où il est facile de trouver des collègues et de communiquer avec eux. Si les utilisateurs de votre organisation viennent à Skype Entreprise à partir de Lync, ils reconnaîtront toutes les fonctionnalités qu’ils utilisent déjà, mais dans une nouvelle interface avec des contrôles simplifiés et de nouveaux ajouts. En plus de la nouvelle expérience client, Skype Entreprise Server 2015 propose plusieurs nouvelles fonctionnalités pour améliorer la gestion des serveurs locaux et des solutions hybrides.
  
Les nouvelles fonctionnalités de Skype Entreprise Server 2015 incluent des améliorations apportées aux éléments suivants :
  
- Expérience utilisateur  
- Prise en charge de la voix et de la vidéo
- Prise en charge mobile
- Gestion des serveurs locaux
- Déploiement et gestion de solutions hybrides
- Prise en charge de l’authentification multifacteur
    
## <a name="user-experience"></a>Expérience utilisateur

Le client Skype Entreprise ressemble beaucoup à la version grand public de Skype et utilise les mêmes boutons et icônes. Moins de menus et une hiérarchie de tâches plus plate, les utilisateurs peuvent facilement trouver rapidement les contrôles et commandes dont ils ont besoin. 
  
Skype Entreprise inclut la nouvelle expérience utilisateur décrite ci-dessus et l’expérience utilisateur Lync 2013 publiée précédemment. L’inclusion des deux expériences permet aux entreprises de gérer les changements pour leurs utilisateurs en contrôlant le processus et le minutage du nouveau déploiement client. L’expérience utilisateur par défaut dépend de la version du serveur que vous utilisez. Les administrateurs choisissent l’expérience préférée à l’aide de l’cmdlet **Set-CsClientPolicy** avec le paramètre EnableSkypeUI. Pour plus d’informations sur la configuration de l’expérience client, voir Configuration de l’expérience client avec [Skype](deploy/deploy-clients/configure-the-client-experience.md) Entreprise et comparaison des fonctionnalités client de bureau pour [Skype Entreprise.](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
  
> [!NOTE]
> L’expérience client Lync 2013 n’est pas une option pour les versions du client Skype Entreprise 2016. Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez sa version pour vous assurer qu’elle ne commence pas par le numéro 16 . par exemple : 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Améliorations de la voix et de la vidéo

Skype Entreprise Server 2015 comprend des améliorations en matière de fonctionnalités vocales et vidéo, notamment la collecte et l’analyse des données d’appel, ainsi qu’une meilleure interopérabilité avec des systèmes de téléconférence vidéo tiers.
  
### <a name="call-data-collection-and-analysis"></a>Collecte et analyse des données d’appel

La fonctionnalité Évaluer mon appel permet aux administrateurs Skype Entreprise Server 2015 de collecter des données d’appel. Cette fonctionnalité est disponible uniquement pour les déploiements locaux. Les utilisateurs sont invités à effectuer une enquête après avoir répondu à un appel. Pour plus d’informations, voir [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interopérabilité améliorée avec les systèmes de téléconférence vidéo tiers

Le vis (Video Interop Server) fait office d’intermédiaire entre skype entreprise server et systèmes de téléconférence vidéo Cisco (VTC). Lorsque vous rejoignez une réunion, les utilisateurs peuvent désormais sélectionner un système Cisco VTC. Le vis (Video Interop Server) est implémenté en tant que rôle serveur autonome pour les déploiements locaux. Pour plus d’informations, voir [Plan for Video Interop Server in Skype for Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Appel via le travail

La fonctionnalité Appel via le travail permet aux utilisateurs d’entreprise d’effectuer des appels vocaux à partir du client Skype Entreprise. Lorsqu’un utilisateur passe un appel vocal, il est acheminé de Skype Entreprise vers le téléphone PBX ou PSTN de l’utilisateur d’origine. Une fois que l’appelant répond au téléphone, l’appel est dirigé vers le numéro de destination. Le destinataire de l’appel répond et l’appel est établi avec Skype Entreprise servant de panneau de contrôle. L’utilisateur d’origine peut gérer ses contrôles de présence et d’appel à partir de Skype Entreprise. Les administrateurs de serveur activent et configurent l’appel via le bureau pour l’entreprise. Pour plus d’informations, voir [Plan for Call Via Work in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Améliorations de la prise en charge des appareils mobiles

Les améliorations apportées à la prise en charge des appareils mobiles incluent des fonctionnalités qui améliorent l’expérience mobile pour les utilisateurs Enterprise Edition, telles que l’accès à l’historique des conversations et aux données de journal, l’amélioration des expériences de réunion mobile et la prise en charge de l' connecter unique dans Office. En outre, des améliorations ont été apportées à la prise en charge d’Android, aux améliorations des performances et aux fonctionnalités pour simplifier l’intégration via Common App Framework. 
  
> [!NOTE]
> Les serveurs UCWA Lync 2013 doivent être mis à niveau vers Skype Entreprise Server 2015 pour prendre en charge les clients mobiles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>L’historique des conversations côté serveur est désormais disponible sur les appareils mobiles

Pour activer l’accès mobile à l’historique des conversations, à la messagerie instantanée manquée et aux données du journal des appels, l’archivage de ces informations est désormais traitée via le serveur pour tous les clients mobiles. La fonctionnalité d’acceptation automatique pour la messagerie instantanée améliore la fiabilité en empêchant les messages de délai d’accès du serveur lorsqu’un utilisateur mobile ne répond pas immédiatement à un message instantané. Pour tirer parti de l’intégration des dossiers Exchange/Outlook basée sur le serveur, Exchange Server 2013 ou version plus nouvelle et les clients mobiles mis à jour sont requis. 
  
### <a name="enhanced-meeting-experiences"></a>Expériences de réunion améliorées

Les fonctionnalités de réunion disponibles sur le bureau sont désormais également disponibles pour les utilisateurs mobiles. Les nouvelles fonctionnalités incluent :
  
- Navigation asynchrone de contenu PowerPoint partagé
- Capacité du présentateur à prendre le contrôle du contenu PowerPoint partagé
- Gestion de la salle d’accueil pour les présentateurs, leur permettant d’admettre ou de refuser des participants
    
### <a name="skype-for-business-on-android-improvements"></a>Améliorations de Skype Entreprise sur Android

Skype Entreprise sur Android offre désormais des fonctionnalités similaires à ce qui est disponible sur Skype Entreprise sur iOS et Skype Entreprise sur Windows :
  
- Continuer ou rejoindre des conversations
- Activer le certificat et l’authentification passive
- Inviter d’autres personnes dans une conversation
- Démarrer facilement des conversations de groupe
- Rejoindre une réunion sans être utilisateur de Skype Entreprise
- Activer l’interface utilisateur de smartphone sur les tablettes Android
- Gérer les réunions en ajoutant ou en supprimant des participants
    
> [!NOTE]
> Ces fonctionnalités nécessitent Android OS version 4.0 ou supérieure. 
  
## <a name="management-of-on-premises-servers"></a>Gestion des serveurs locaux

Skype Entreprise Server 2015 propose plusieurs nouvelles fonctionnalités pour améliorer la gestion des serveurs locaux, notamment la mise à niveau sur place, l’installation intelligente, l’amélioration des correctifs et des processus de mise à niveau, l’amélioration de la fonctionnalité de démarrage à froid du pool frontal, la prise en charge de SQL Server AlwaysOn et la journalisation centralisée et la résolution des problèmes.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Mise à niveau sur place pour les serveurs locaux

Vous pouvez désormais mettre à niveau les systèmes Lync Server 2013 vers Skype Entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau sur place, qui utilise des investissements matériels et serveur Lync Server 2013 existants, réduisant ainsi le coût global du déploiement de Skype Entreprise Server 2015.
  
Il existe deux scénarios de mise à niveau sur place : la méthode Move User, qui ne nécessite aucun temps d’arrêt, et la méthode Hors connexion, qui nécessite un temps d’arrêt. Pour plus d’informations sur la procédure de mise à niveau qui est la plus pertinente pour votre entreprise, voir [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> L’option sur place n’est pas disponible si vous êtes en cours de mise à niveau à partir de Lync Server 2010. Pour plus d’informations sur la mise à niveau à partir de Lync Server 2010, voir [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Configuration intelligente

La fonctionnalité d’installation intelligente, qui détecte et télécharge automatiquement les mises à jour, fait désormais partie du programme d’installation. Pendant le processus d’installation, l’utilisateur est invité à vérifier si le processus d’installation doit vérifier les mises à jour. Pour plus d’informations, [voir Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Amélioration du processus de mise à jour et de mise à jour des correctifs du serveur frontal

Skype Entreprise Server introduit deux nouvelles cmdlets qui facilitent la mise à niveau ou l’application de correctifs aux serveurs frontaux par rapport aux versions précédentes de Lync Server.
  
Lorsque vous devez appliquer un correctif ou effectuer toute autre maintenance à un serveur frontal, tapez **simplement Invoke-CsComputerFailOver** et spécifiez le nom de ce serveur. Skype Entreprise Server déplace temporairement la charge de travail de ce serveur vers les autres serveurs du pool. Vous pouvez ensuite effectuer la maintenance, puis utiliser l’cmdlet **Invoke-CsComputerFailback** pour remettre ce serveur en service. Si vous devez mettre à jour chaque serveur d’un pool, suivez simplement cette procédure pour chaque serveur, un par un. Ces nouvelles cmdlets vous permettent de mettre à jour les serveurs beaucoup plus rapidement que dans les versions précédentes, avec plus de fiabilité et un flux de travail plus simple.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Amélioration de la fonctionnalité de démarrage à froid du pool frontal

Skype Entreprise Server introduit une nouvelle cmdlet qui simplifie et améliore le processus de démarrage à froid d’un pool frontal entier. Lorsque vous utilisez la nouvelle cmdlet **Start-CsPool,** elle vérifie les conditions préalables pour tous les serveurs frontaux du pool, puis tente de démarrer chaque serveur. S’il rencontre des problèmes, il les diagnostice et vous avertit avec des détails et des solutions de contournement. Dans certains cas, il vous permet de démarrer le pool même si certains serveurs individuels ne peuvent pas démarrer.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server alwayson pour les serveurs locaux

Skype Entreprise Server 2015 ajoute la prise en charge des groupes de disponibilité AlwaysOn SQL Server des instances de cluster de SQL Server AlwaysOn. En plus de ces fonctionnalités, Skype Entreprise Server continue de prendre en charge la mise en miroir de bases de données et SQL Server clustering, comme dans les versions précédentes de Lync Server.
  
SQL Server Groupes de disponibilité AlwaysOn est une solution de haute disponibilité et de récupération d’urgence dans SQL Server 2012 et SQL Server 2014 qui offre une alternative à la mise en miroir de bases de données. Un groupe de disponibilité prend en charge un environnement de failover pour un ensemble discret de bases de données (appelées bases de données de disponibilité) qui échouent ensemble. Un groupe de disponibilité prend en charge un ensemble de bases de données primaires en lecture-écriture et un à quatre ensembles de bases de données secondaires correspondantes. Éventuellement, les bases de données secondaires peuvent être rendues disponibles pour l’accès en lecture seule et pour certaines opérations de sauvegarde.
  
SQL Server instances de cluster de failover utilisent la fonctionnalité WSFC (Failover Clustering) de Windows Server pour fournir une haute disponibilité locale via la redondance au niveau de l’instance de serveur ( instance de cluster de failover). Un FCI est une instance unique de SQL Server installée sur plusieurs sous-réseaux et sur plusieurs sous-réseaux.
  
Pour plus d’informations, voir [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Améliorations de la journalisation centralisée et de la résolution des problèmes pour les serveurs locaux

Le service de journalisation centralisée est l’environnement de journalisation préféré pour Skype Entreprise Server 2015. Il n’existe aucune nouvelle fonctionnalité de cette version, mais la fiabilité et les performances ont été améliorées pour le service et l’agent du service de journalisation centralisée (ClsAgent.exe), le service exécutable qui communique avec le contrôleur et reçoit les commandes émises par l’administrateur.
  
Skype Entreprise Server 2015 utilise Windows PowerShell cmdlets pour gérer les agents du service de journalisation, lancer le suivi et générer des rapports. (Lync Server 2013 a utilisé ClsController.exe pour effectuer ces tâches.)
  
Le service de journalisation centralisée peut s’exécuter sur n’importe quel serveur Skype Entreprise Server 2015. Les scénarios intégrés (suivis prédéfinits) restent les mêmes, tout comme la possibilité de créer des scénarios personnalisés. Il existe un scénario spécial appelé AlwaysOn qui est toujours en cours d’exécution et qui permet aux administrateurs de localiser les problèmes courants en temps quasi réel.
  
L’outil de débogage Snooper a également été mis à jour pour permettre le débogage des journaux de mobilité et fonctionne avec les appareils qui se connectent à Lync 2013 ou Skype Entreprise Server 2015. L’outil est disponible en téléchargement Web à partir [des outils de débogage.](https://go.microsoft.com/fwlink/?LinkId=285257)
  
## <a name="hybrid-deployment-and-management"></a>Déploiement et gestion hybrides

Skype Entreprise Server 2015 permet l’administration et la gestion du déploiement hybride en introduisant les fonctionnalités suivantes :
  
- Recommandations pour les déploiements hybrides en fonction de l’état des ressources sur site du client, telles que déterminées par l’outil d’assistance automatisée OnRamp pour Office 365.
- Améliorations apportées au Panneau de contrôle Skype Entreprise Server et au Centre d’administration Skype Entreprise Server afin que les administrateurs peuvent utiliser ces outils pour gérer un déploiement hybride.
- Améliorations du Panneau de configuration qui permet aux administrateurs de se connectent à un client Microsoft 365 ou Office 365 et de configurer une configuration hybride avec Skype Entreprise Online à l’aide de l’Assistant configuration hybride.
- Prise en charge du Panneau de contrôle pour le déplacement d’utilisateurs locaux vers Skype Entreprise Online ou le déplacement des utilisateurs de Skype Entreprise Online vers l’local.
- Fonctionnalités du Panneau de contrôle permettant d’identifier et de filtrer les objets utilisateur locaux qui ont été déplacés vers Skype Entreprise Online (c’est-à-dire, les utilisateurs hybrides) des utilisateurs locaux.
- Fonctionnalités du Centre d’administration permettant d’identifier et de filtrer les utilisateurs cloud initialement créés dans Skype Entreprise Online à partir d’utilisateurs hybrides migrés en local vers Online.
- La possibilité d’administrer des utilisateurs hybrides à l’aide du Panneau de contrôle pour les propriétés gérables en local et du Centre d’administration pour les propriétés gérables à partir de Skype Entreprise Online.
- À l’aide de la synchronisation de mot de passe avec DirSync, la possibilité de synchroniser les mots de passe Active Directory locaux avec le client en ligne. Si elle est configurée, cette fonctionnalité supprime la nécessité de déployer AD FS pour l’authentification fédérée, mais AD FS est toujours requis pour l’authentification multifacteur. 
- Prise en charge continue de la coexistence entre Skype Entreprise Online et Exchange en local.
    
> [!NOTE]
> Il n’existe aucune modification par rapport à l’expérience de prise en charge et de coexistence Lync Online 2013 et Exchange sur site. 
  
## <a name="multi-factor-authentication"></a>Authentification multifacteur

L’authentification multifacteur est une méthode d’authentification qui nécessite l’utilisation de plusieurs méthodes de vérification et ajoute une deuxième couche critique de sécurité aux transactions et aux signatures des utilisateurs. Par exemple, l’utilisation d’un nom d’utilisateur et d’un mot de passe, ainsi que d’un certificat. Skype Entreprise Server 2015 continue de s’appuyer sur les fonctionnalités d’authentification multifacteur disponibles dans les mises à jour cumulatives de Lync Server 2013. Les modifications importantes apportées à l’authentification multifacteur sont les suivants :
  
- Utilisation de la bibliothèque d’authentification Active Directory Office 2013 SP1 pour l’intégration avec Exchange et SharePoint
- Prise en charge de la fonctionnalité d’authentification multifacteur dans le client Skype Entreprise Web App
    
Avec l’authentification multifacteur Skype Entreprise, il est désormais possible de fournir différentes options d’authentification en fonction de la géographie. Par exemple, les clients peuvent configurer leur environnement de sorte que l’authentification interne repose sur l’authentification Windows intégrée, tandis que les employés qui s’authentifier en dehors de l’organisation utilisent l’authentification multifacteur. 
  
L’expérience d’authentification multifacteur Skype Entreprise est transparente, indépendamment des éléments suivants :
  
- Emplacement géographique : si l’utilisateur se signe à l’intérieur ou à l’extérieur de l’organisation 
- Type de client/appareil : le client Skype Entreprise utilisé et l’appareil sur lequel le client s’exécute (PC, mobile, iPad, etc.)
- Emplacement du compte : si l’utilisateur est hébergé dans un annuaire Active Directory local ou dans Azure Active Directory Online.
