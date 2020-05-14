---
title: Nouveautés de Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Résumé : consultez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype entreprise Server 2015. Pour plus d’informations sur la nouvelle expérience client, voir Lync est maintenant Skype entreprise--voir what’s New.'
ms.openlocfilehash: b8d0d8334977b5367419991d1bcabba303718c89
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221084"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Nouveautés de Skype entreprise Server 2015

**Résumé :** Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype entreprise Server 2015. Pour plus d’informations sur la nouvelle expérience client, voir [Lync est maintenant Skype entreprise--voir what’s New](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync est désormais Skype entreprise, une plateforme de communication et de collaboration qui offre une expérience inspirée par Skype avec la sécurité de niveau entreprise, la conformité et le contrôle de Lync. Skype entreprise offre des fonctionnalités telles que la présence, la messagerie instantanée, les appels vocaux et vidéo, ainsi que les réunions en ligne. Skype entreprise offre une nouvelle expérience client, une nouvelle version du serveur et des mises à jour du service dans Microsoft 365 ou Office 365. Si les utilisateurs de votre organisation connaissent déjà Skype, ils apprécieront la puissance et la simplicité de Skype entreprise, où il est facile de trouver et de communiquer avec les collègues. Si les utilisateurs de votre organisation acvenaient à Skype entreprise à partir de Lync, ils reconnaîtront toutes les fonctionnalités qu’ils utilisent déjà, mais dans une nouvelle interface avec des contrôles simplifiés et de nouveaux ajouts. En plus de la nouvelle expérience client, Skype entreprise Server 2015 offre plusieurs nouvelles fonctionnalités pour améliorer la gestion des serveurs locaux et des solutions hybrides.
  
Les nouvelles fonctionnalités de Skype entreprise Server 2015 incluent des améliorations apportées aux éléments suivants :
  
- Expérience utilisateur  
- Prise en charge de la voix et de la vidéo
- Prise en charge mobile
- Gestion des serveurs locaux
- Déploiement et gestion de solutions hybrides
- Prise en charge de l’authentification multifacteur
    
## <a name="user-experience"></a>Expérience utilisateur

Le client Skype entreprise ressemble beaucoup à la version grand public de Skype et utilise les mêmes boutons et icônes. Un nombre réduit de menus et une hiérarchie des tâches simplifiée permettent aux utilisateurs de trouver rapidement les contrôles et les commandes dont ils ont besoin. 
  
Skype entreprise inclut la nouvelle expérience utilisateur décrite ci-dessus et l’expérience utilisateur Lync 2013 publiée précédemment. L’inclusion des deux expériences permet aux entreprises de gérer les modifications apportées à leurs utilisateurs en contrôlant le processus et le calendrier du déploiement du nouveau client. L’expérience utilisateur par défaut dépend de la version du serveur que vous utilisez. Les administrateurs choisissent l’expérience par défaut à l’aide de la cmdlet **Set-CsClientPolicy** avec le paramètre EnableSkypeUI. Pour plus d’informations sur la configuration de l’expérience client, reportez-vous à [la rubrique Configure the client expérience with Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) and [Desktop Client Feature Comparison for Skype for Business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> L’expérience client Lync 2013 n’est pas une option pour les versions clientes de Skype entreprise 2016. Avant de configurer votre environnement client pour qu’il utilise le client Lync 2013, vérifiez la version du client pour vous assurer qu’elle ne commence pas par le numéro 16 ; par exemple : 16. x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Améliorations de la voix et de la vidéo

Skype entreprise Server 2015 inclut des améliorations des fonctionnalités vocales et vidéo, notamment la collecte et l’analyse des données d’appel, ainsi qu’une meilleure interopérabilité avec les systèmes de téléconférence vidéo tiers.
  
### <a name="call-data-collection-and-analysis"></a>Collecte et analyse des données d’appel

La fonctionnalité taux d’appel permet aux administrateurs de Skype entreprise Server 2015 de collecter les données d’appel. Cette fonctionnalité est disponible uniquement pour les déploiements locaux. Les utilisateurs sont invités à effectuer une enquête après la fin d’un appel. Pour plus d’informations, consultez la rubrique [rate My Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Amélioration de l’interopérabilité avec les systèmes de téléconférence vidéo tiers

Le serveur d’interopérabilité vidéo (VIS) agit comme un intermédiaire entre les systèmes Skype entreprise Server et Cisco Video Teleconferencing (VTC). Lors de la participation à une réunion, les utilisateurs peuvent désormais sélectionner un système Cisco VTC. Le serveur d’interopérabilité vidéo (VIS) est implémenté en tant que rôle serveur autonome pour les déploiements locaux. Pour plus d’informations, reportez-vous à la rubrique [plan for Video Interop Server in Skype for Business server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Appel via le Bureau

La fonctionnalité appel via le bureau permet aux utilisateurs d’entreprise d’effectuer des appels vocaux à partir du client Skype entreprise. Lorsqu’un utilisateur passe un appel vocal, il est acheminé depuis Skype entreprise vers le PBX ou le téléphone RTC de l’expéditeur. Une fois que l’expéditeur répond au téléphone, l’appel est ensuite dirigé vers le numéro de destination. Les réponses aux destinataires d’appel et l’appel sont établis avec Skype entreprise servant de panneau de configuration. L’expéditeur peut gérer sa présence et les contrôles d’appel à partir de Skype entreprise. Les administrateurs de serveur activent et configurent l’appel via le Bureau pour l’entreprise. Pour plus d’informations, reportez-vous à [plan for Call via Work in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Améliorations de la prise en charge des appareils mobiles

Les améliorations apportées à la prise en charge des appareils mobiles incluent des fonctionnalités visant à améliorer l’expérience mobile pour les utilisateurs d’Enterprise Edition, telles que l’accès à l’historique des conversations et aux données de journal, l’expérience de réunion mobile améliorée et la prise en charge de l’authentification unique sur Office. En outre, des améliorations ont été apportées à la prise en charge d’Android, des améliorations de performances et des fonctionnalités pour simplifier l’intégration via l’infrastructure d’application commune. 
  
> [!NOTE]
> Les serveurs UCWA Lync 2013 doivent être mis à niveau vers Skype entreprise Server 2015 pour prendre en charge les clients mobiles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>L’historique des conversations côté serveur est désormais disponible sur les appareils mobiles

Pour activer l’accès mobile à l’historique des conversations, aux messages instantanés manqués et aux données du journal d’appels, l’archivage de ces informations est désormais traité par le serveur pour tous les clients mobiles. La fonctionnalité d’acceptation automatique pour la messagerie instantanée améliore la fiabilité en empêchant les messages de délai d’attente du serveur lorsqu’un utilisateur mobile ne répond pas immédiatement à un message instantané. Pour tirer parti de l’intégration de dossiers Exchange/Outlook basée sur le serveur, vous devez disposer d’Exchange Server 2013 ou une version plus récente, ainsi que de clients mobiles mis à jour. 
  
### <a name="enhanced-meeting-experiences"></a>Amélioration des expériences de réunion

Les fonctionnalités de réunion disponibles sur le bureau sont également disponibles pour les utilisateurs mobiles. Les nouvelles fonctionnalités incluent :
  
- Navigation asynchrone du contenu PowerPoint partagé
- Possibilité pour le présentateur de prendre le contrôle du contenu PowerPoint partagé
- Gestion de la salle d’attente pour les présentateurs, ce qui leur permet d’admettre ou de refuser des participants
    
### <a name="skype-for-business-on-android-improvements"></a>Améliorations de Skype entreprise sur Android

Skype entreprise sur Android offre désormais des fonctionnalités similaires à celles disponibles sur Skype entreprise sur iOS et Skype entreprise sur Windows :
  
- Continuer ou rejoindre les conversations
- Activer le certificat et l’authentification passive
- Inviter d’autres personnes à une conversation
- Démarrer facilement les conversations de groupe
- Participer à une réunion sans être un utilisateur de Skype entreprise
- Activer l’interface utilisateur de smartphone sur les tablettes Android
- Gérer les réunions en ajoutant ou en supprimant des participants
    
> [!NOTE]
> Ces fonctionnalités nécessitent le système d’exploitation Android version 4,0 ou supérieure. 
  
## <a name="management-of-on-premises-servers"></a>Gestion des serveurs locaux

Skype entreprise Server 2015 offre plusieurs nouvelles fonctionnalités qui facilitent la gestion des serveurs locaux, notamment la mise à niveau sur place, la configuration intelligente, les processus de mise à niveau et de mise à jour améliorés, la capacité de démarrage à haute disponibilité des pools frontaux, la prise en charge de SQL Server AlwaysOn, ainsi que la journalisation et la résolution des problèmes.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Mise à niveau sur place pour les serveurs locaux

Vous pouvez désormais mettre à niveau les systèmes Lync Server 2013 vers Skype entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau sur place, qui utilise les investissements existants du matériel et des serveurs Lync Server 2013, réduisant ainsi le coût global de déploiement de Skype entreprise Server 2015.
  
Il existe deux scénarios pour la mise à niveau sur place : la méthode déplacer l’utilisateur, qui ne nécessite aucun temps d’arrêt, et la méthode hors ligne, qui nécessite un temps d’arrêt. Pour plus d’informations sur la procédure de mise à niveau appropriée pour votre entreprise, reportez-vous à la rubrique [plan to Upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> L’option sur place n’est pas disponible si vous effectuez une mise à niveau à partir de Lync Server 2010. Pour plus d’informations sur la mise à niveau à partir de Lync Server 2010, reportez-vous à la rubrique [plan to Upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Installation intelligente

La fonctionnalité d’installation intelligente, qui détecte et télécharge automatiquement les mises à jour, fait désormais partie du programme d’installation. Pendant le processus d’installation, l’utilisateur est invité à indiquer si le processus d’installation doit vérifier les mises à jour. Pour plus d’informations, consultez la rubrique [install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Amélioration de la mise à jour et du processus de mise à niveau du serveur frontal

Skype entreprise Server introduit deux nouvelles applets de commande qui facilitent grandement la mise à niveau ou l’application de correctifs aux serveurs frontaux que dans les versions précédentes de Lync Server.
  
Lorsque vous avez besoin d’appliquer un correctif ou d’effectuer d’autres opérations de maintenance sur un serveur frontal, il vous suffit de taper **Invoke-CsComputerFailOver** et de spécifier le nom de ce serveur. Skype entreprise Server déplace temporairement la charge de travail de ce serveur vers les autres serveurs du pool. Vous pouvez ensuite effectuer la maintenance, puis utiliser l’applet de commande **Invoke-CsComputerFailback** pour remettre ce serveur en service. Si vous devez appliquer un correctif à chaque serveur d’un pool, il suffit de suivre cette procédure pour chaque serveur, un à la fois. Ces nouvelles applets de commande vous permettent d’appliquer des correctifs beaucoup plus rapidement que dans les versions précédentes, avec davantage de fiabilité et un flux de travail plus simple.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Capacité de démarrage à froid de pool frontal amélioré

Skype entreprise Server introduit une nouvelle cmdlet qui simplifie et améliore le processus de démarrage à froid d’un pool frontal complet. Lorsque vous utilisez la nouvelle cmdlet **Start-applet cspool** , elle vérifie les conditions préalables pour tous les serveurs frontaux du pool, puis tente de démarrer chaque serveur. S’il rencontre des problèmes, il les diagnostique et vous alerte avec des détails et des solutions de contournement. Dans certains cas, il vous permet de démarrer le pool même si certains serveurs individuels ne peuvent pas démarrer.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Prise en charge de SQL Server AlwaysOn pour les serveurs locaux

Skype entreprise Server 2015 ajoute la prise en charge des groupes de disponibilité AlwaysOn SQL Server et des instances de cluster de basculement SQL Server AlwaysOn. En plus de ces fonctionnalités, Skype entreprise Server continue de prendre en charge la mise en miroir de bases de données et le clustering SQL Server, comme dans les versions précédentes de Lync Server.
  
Les groupes de disponibilité AlwaysOn SQL Server sont une solution de haute disponibilité et de récupération d’urgence dans SQL Server 2012 et SQL Server 2014 qui offre une alternative à la mise en miroir de bases de données. Un groupe de disponibilité prend en charge un environnement de basculement pour un ensemble discret de bases de données (appelées bases de données de disponibilité) qui basculent ensemble. Un groupe de disponibilité prend en charge un ensemble de bases de données primaires en lecture-écriture et un à quatre ensembles de bases de données secondaires correspondantes. Éventuellement, les bases de données secondaires peuvent être mises à disposition pour un accès en lecture seule et pour certaines opérations de sauvegarde.
  
Les instances de cluster de basculement SQL Server exploitent la fonctionnalité de clustering de basculement Windows Server (WSFC) pour fournir une haute disponibilité locale via la redondance au niveau de l’instance de serveur, une instance de cluster de basculement (ICF). Un ICF est une instance unique de SQL Server installée sur des nœuds de clustering de basculement Windows Server (WSFC) et, éventuellement, sur plusieurs sous-réseaux.
  
Pour plus d’informations, reportez-vous à la rubrique [plan for High Availability and Disaster Recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Journalisation centralisée et améliorations de résolution des problèmes pour les serveurs locaux

Le service de journalisation centralisée est l’environnement de journalisation par défaut pour Skype entreprise Server 2015. Il n’y a pas de nouvelles fonctionnalités pour cette version, mais la fiabilité et les performances ont été améliorées pour le service et l’agent de service de journalisation centralisée (ClsAgent. exe), le service exécutable qui communique avec le contrôleur et reçoit les commandes émises par l’administrateur.
  
Skype entreprise Server 2015 utilise des applets de commande Windows PowerShell pour gérer les agents des services de journalisation, initier le suivi et générer des rapports. (Lync Server 2013 a utilisé ClsController. exe pour effectuer ces tâches.)
  
Le service de journalisation centralisée peut s’exécuter sur n’importe quel Skype entreprise Server 2015. Les scénarios intégrés (suivis prédéfinis) restent identiques, tout comme la possibilité de créer des scénarios personnalisés. Il existe un scénario spécial appelé AlwaysOn qui est toujours en cours d’exécution et permet aux administrateurs de localiser des problèmes courants en temps réel.
  
L’outil de débogage du Snooping a également été mis à jour pour permettre le débogage des journaux de mobilité et fonctionnera avec les appareils qui se connectent à Lync 2013 ou Skype entreprise Server 2015. L’outil peut être téléchargé sur le Web à partir des [outils de débogage](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Déploiement et gestion hybrides

Skype entreprise Server 2015 permet des fonctionnalités d’administration et de gestion de déploiement hybride en introduisant les fonctionnalités suivantes :
  
- Recommandations pour les déploiements hybrides en fonction de l’état des ressources locales du client, tel que déterminé par l’outil d’assistance automatisée OnRamp pour Office 365.
- Améliorations apportées au panneau de configuration Skype entreprise Server et au centre d’administration Skype entreprise Server pour que les administrateurs puissent utiliser ces outils pour gérer un déploiement hybride.
- Améliorations apportées au panneau de configuration permettant aux administrateurs de se connecter à un client Microsoft 365 ou Office 365 et de configurer un environnement hybride avec Skype entreprise Online à l’aide de l’Assistant Configuration hybride.
- Le panneau de configuration prend en charge le déplacement des utilisateurs locaux vers Skype entreprise Online ou le déplacement des utilisateurs de Skype entreprise Online vers l’environnement local.
- Fonctionnalités du panneau de configuration permettant d’identifier et de filtrer les objets utilisateur sur site qui ont été déplacés vers Skype entreprise Online (c’est-à-dire, les utilisateurs hybrides) à partir d’utilisateurs locaux.
- Fonctionnalités du centre d’administration permettant d’identifier et de filtrer les utilisateurs du nuage initialement créés dans Skype entreprise Online à partir d’utilisateurs hybrides migrés de l’environnement local vers le service en ligne.
- Possibilité d’administrer des utilisateurs hybrides à l’aide du panneau de configuration pour les propriétés gérables à partir de la version locale et du centre d’administration pour les propriétés gérables à partir de Skype entreprise online.
- À l’aide de la synchronisation de mot de passe avec DirSync, la possibilité de synchroniser les mots de passe Active Directory sur site avec le client en ligne. S’il est configuré, cette fonctionnalité supprime la nécessité de déployer AD FS pour l’authentification fédérée, mais AD FS est toujours requis pour l’authentification multifacteur. 
- Prise en charge continue de la coexistence entre Skype entreprise Online et Exchange en local.
    
> [!NOTE]
> Aucune modification n’est apportée à la coexistence et au support sur Lync Online 2013 et Exchange sur site. 
  
## <a name="multi-factor-authentication"></a>Authentification multifacteur

L’authentification multifacteur est une méthode d’authentification qui nécessite l’utilisation de plusieurs méthodes de vérification et ajoute une deuxième couche de sécurité critique aux connexions et transactions des utilisateurs. Par exemple, exiger un nom d’utilisateur et un mot de passe, ainsi qu’un certificat. Skype entreprise Server 2015 continue de s’appuyer sur les fonctionnalités d’authentification multifacteur disponibles dans les mises à jour cumulatives de Lync Server 2013. Les principales modifications apportées à l’authentification multifacteur sont les suivantes :
  
- Utilisation de la bibliothèque d’authentification Active Directory d’Office 2013 SP1 pour une intégration avec Exchange et SharePoint
- Prise en charge de la fonctionnalité d’authentification multifacteur dans le client Skype entreprise Web App
    
Avec l’authentification multifacteur de Skype entreprise, il est désormais possible de fournir différentes options d’authentification basées sur la géographie. Par exemple, les clients peuvent configurer leur environnement de sorte que l’authentification interne repose sur l’authentification Windows intégrée, tandis que les employés qui s’authentifient en dehors de l’organisation utilisent l’authentification multifacteur. 
  
L’expérience d’authentification multifacteur Skype entreprise est transparente indépendamment des éléments suivants :
  
- Emplacement géographique : indique si l’utilisateur se connecte à l’intérieur ou à l’extérieur de l’Organisation 
- Type de client/périphérique : le client Skype entreprise est utilisé et l’appareil sur lequel le client est exécuté (PC, mobile, iPad, etc.)
- Emplacement du compte : indique si l’utilisateur est hébergé dans un environnement Active Directory local ou Azure Active Directory en ligne.
