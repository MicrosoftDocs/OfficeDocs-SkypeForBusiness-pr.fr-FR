---
title: Nouveautés de Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype pour Business Server 2015. Pour plus d’informations sur l’expérience du client, voir que Lync est désormais Skype pour les entreprises : nouveautés.'
ms.openlocfilehash: e1ae2a046b955e83ccc7c811984a526c26f7c526
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "24961028"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Nouveautés de Skype Entreprise Server 2015

**Résumé :** Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype pour Business Server 2015. Pour obtenir des informations détaillées sur l’expérience du client, voir [Lync est maintenant Skype pour les entreprises, voir Nouveautés](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync est désormais Skype pour plate-forme Business, une communication et de collaboration qui intègre une expérience inspirés par Skype avec la sécurité de niveau entreprise, la conformité et le contrôle de Lync. Skype pour les entreprises offre des fonctionnalités, y compris la présence, messagerie instantanée, voix et les appels vidéo et les réunions en ligne. Skype pour les entreprises fournit un nouveau client expérience, une nouvelle version de serveur et de mises à jour vers le service dans Office 365. Si les utilisateurs de votre organisation sont déjà familiarisés avec Skype, ils apprécierez la puissance et la simplicité de Skype pour les entreprises où il est facile de trouver et de communiquer avec vos collègues. Si provenant des utilisateurs de votre organisation à Skype pour les entreprises de Lync, ils allez reconnaît toutes les fonctionnalités qu’ils déjà utilisent mais ils dans une nouvelle interface vierge avec des contrôles et des ajouts. Outre la nouvelle expérience client, Skype pour Business Server 2015 fournit plusieurs nouvelles fonctionnalités pour améliorer la gestion des serveurs locaux et les solutions hybrides.
  
Nouvelles fonctionnalités de Skype pour Business Server 2015 incluent des améliorations :
  
- Expérience utilisateur  
- Prise en charge de la voix et de la vidéo
- Prise en charge de la mobilité
- Gestion des serveurs sur site
- Déploiement et gestion de solutions hybrides
- Prise en charge de l’authentification multifacteur
    
## <a name="user-experience"></a>Expérience utilisateur

Le Skype pour client d’entreprise est très similaire à la version consommateur de Skype et utilise les mêmes boutons et icônes. Un nombre moindre de menus et une arborescence plus horizontale des tâches permettent de trouver plus rapidement les contrôles et les commandes dont vous avez besoin. 
  
Skype pour les entreprises inclut la nouvelle expérience utilisateur décrites ci-dessus et l’expérience utilisateur de Lync 2013 publié précédemment. L’inclusion de ces deux expériences permet aux entreprises de gérer les modifications de leurs utilisateurs à contrôler le processus et le minutage de la nouvelle client déploiement. L’expérience utilisateur par défaut dépend de la version du serveur que vous utilisez. Les administrateurs peuvent choisir l’expérience préférée à l’aide de l’applet de commande **Set-CsClientPolicy** avec le paramètre EnableSkypeUI. Pour plus d’informations sur la configuration de l’expérience du client, voir [pour configurer le client expérience avec Skype pour les entreprises](deploy/deploy-clients/configure-the-client-experience.md) et la [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> L’expérience du client Lync 2013 n’est pas une option pour Skype pour les versions clientes de 2016 Business. Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro de 16 ; par exemple : 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Améliorations de la voix et de la vidéo

Skype pour Business Server 2015 inclut les améliorations apportées aux fonctionnalités audio et vidéo, notamment la collecte de données d’appel et d’analyse et d’une meilleure interopérabilité avec les systèmes tiers vidéoconférences.
  
### <a name="call-data-collection-and-analysis"></a>Collecte et analyse des données des appels

La taux de mon appel fonction vous permet de Skype pour les administrateurs d’entreprise Server 2015 collecte des données d’appel. Cette fonctionnalité est disponible uniquement pour les déploiements sur site. Les utilisateurs sont invités à répondre à une enquête au terme de leur appel. Pour plus d’informations, reportez-vous à [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Amélioration de l’interopérabilité avec des systèmes tiers de téléconférence vidéo.

Le serveur vidéo Interop (pouces) joue le rôle d’intermédiaire entre Skype pour les systèmes de téléconférence (VTC) Business Server et Cisco. Lorsqu’ils rejoignent une réunion, les utilisateurs peuvent maintenant sélectionner un système Cisco VTC. VIS (Video Interop Server) est implémenté en tant que rôle de serveur autonome pour les déploiements sur site. Pour plus d’informations, voir [planifier vidéo Interop Server dans Skype pour Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Appel via le bureau

L’appel via la fonctionnalité de travail permet aux utilisateurs de contenu d’entreprise passer des appels vocaux à partir de la Skype pour client d’entreprise. Lorsqu’un utilisateur passe un appel vocal, il est acheminé de Skype pour les entreprises à téléphone PBX ou PSTN de l’expéditeur. Une fois que l’utilisateur à l’origine de l’appel répond au téléphone, l’appel est alors dirigé vers le numéro de destination. Les réponses de destinataire d’appel et l’appel est établi avec Skype pour entreprise sert le panneau de configuration. L’expéditeur peut gérer leur présence et les contrôles d’appel à partir de Skype pour les entreprises. Les administrateurs des serveurs activent et configurent la fonctionnalité Appel via le bureau pour leur entreprise. Pour plus d’informations, voir [planifier des appels via le bureau dans Skype pour Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Améliorations apportées à la prise en charge des appareils mobiles

Améliorations apportées à la prise en charge de l’appareil mobile incluent des fonctionnalités pour améliorer l’expérience mobile pour les utilisateurs d’Enterprise Edition, telles que les accès aux données de l’historique et les journaux de conversation, une expérience améliorée de réunion mobile et authentification prise en charge unique sur Office. En outre, il existe des améliorations apportées à la prise en charge Android, des améliorations des performances et des fonctionnalités pour simplifier l’intégration par le biais de l’infrastructure des applications courantes. 
  
> [!NOTE]
> Serveurs Lync 2013 UCWA doivent être mis à niveau vers Skype pour Business Server 2015 prendre en charge les clients mobiles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>L’historique des conversations côté serveur est maintenant disponible sur les appareils mobiles

Pour activer l’accès mobile à l’historique des conversations par messagerie instantanée manquée et appel de données du journal, l’archivage de ces informations est maintenant traité par le serveur pour tous les clients mobiles. La fonction Accepter automatiquement pour la messagerie instantanée améliore la fiabilité en empêchant les messages de dépassement du délai du serveur quand un utilisateur mobile ne répond pas immédiatement à un message instantané. Pour tirer parti de l’intégration de dossiers de serveur Exchange/Outlook, Exchange Server 2013 ou plus récentes et mis à jour les clients mobiles, sont requis. 
  
### <a name="enhanced-meeting-experiences"></a>Amélioration de l’expérience des réunions

La fonctionnalité des réunions disponible sur le bureau est maintenant disponible pour les utilisateurs mobiles. Cette nouvelle fonctionnalité comprend ce qui suit :
  
- Navigation asynchrone du contenu PowerPoint partagé
- Permet de prendre le contrôle de PowerPoint partagé contenu du présentateur
- Gestion de la salle d’attente pour les présentateurs, leur permettant d’accepter ou de refuser des participants
    
### <a name="skype-for-business-on-android-improvements"></a>Skype pour les entreprises sur les améliorations Android

Skype pour les entreprises sur Android offre désormais des fonctionnalités similaires à ce qui est disponible sur Skype pour les entreprises sur iOS et Skype pour les entreprises sur Windows :
  
- Continuer ou rejoindre des conversations
- Activer l’authentification des certificats et l’authentification passive
- Inviter un autre contact à une conversation
- Lancer simplement des conversations de groupe
- Joindre une réunion sans être un utilisateur Skype Entreprise
- Activer l’interface utilisateur smartphone sur les tablettes Android
- Gérer des réunions en ajoutant ou en supprimant des participants
    
> [!NOTE]
> Ces fonctionnalités nécessitent Android OS version 4.0 ou supérieure. 
  
## <a name="management-of-on-premises-servers"></a>Gestion des serveurs sur site

Skype pour Business Server 2015 fournit plusieurs nouvelles fonctionnalités pour améliorer la gestion des serveurs locaux, y compris à niveau sur place, le programme d’installation active, mise à jour corrective améliorée et mise à niveau traite, capacité à froid de pool frontal améliorée, SQL Server AlwaysOn prise en charge et centralisée journalisation et le dépannage.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Mise à niveau sur place pour les serveurs locaux

Vous pouvez maintenant mise Lync Server 2013 Skype pour Business Server 2015 à l’aide de la fonctionnalité de mise à niveau sur place nouveau, qui utilise des investissements matériels et serveur Lync Server 2013 existants, ce qui réduit le coût global pour déployer Skype pour Business Server 2015.
  
Il existe deux scénarios pour la mise à niveau sur place : la méthode Déplacer l’utilisateur, qui ne demande aucun temps d’arrêt, et la méthode Hors ligne, qui exige un temps d’arrêt. Pour plus d’informations sur la meilleure option pour votre entreprise, reportez-vous à [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> L’option place n’est pas disponible si vous mettez à niveau à partir de Lync Server 2010. Pour plus d’informations sur la mise à niveau de Lync Server 2010, voir [planifier la mise à niveau vers Skype pour Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Installation intelligente (Smart Setup)

La fonctionnalité d’installation intelligente, qui détecte et télécharge automatiquement les mises à jour, fait partie intégrante du programme d’installation. Au cours du processus d’installation, l’utilisateur est invité si le processus d’installation doit vérifier les mises à jour. Pour plus d’informations, reportez-vous à [Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Amélioration du processus des correctifs et de mise à jour du serveur frontal

Skype pour Business Server présente deux nouvelles applets de commande qui permettent de rendre la mise à niveau ou mise à jour des serveurs frontaux beaucoup plus facile que dans les versions précédentes de Lync Server.
  
Lorsque vous devez appliquer un correctif, ou effectuer toute maintenance pour un serveur frontal, simplement taper **Invoke-CsComputerFailOver** et spécifiez le nom de ce serveur. Skype pour Business Server déplace temporairement la charge de travail de ce serveur pour les autres serveurs du pool. Vous pouvez ensuite effectuer l’opération de maintenance, puis utiliser l’applet de commande **Invoke-CsComputerFailback** pour remettre ce serveur en service. Si vous avez besoin d’appliquer un correctif à chaque serveur d’un pool, il suffit de suivre cette procédure pour chaque serveur, un à la fois. Ces nouvelles applets de commande vous permettent d’installer les correctifs des serveurs beaucoup plus rapidement que dans les versions précédentes et avec plus de fiabilité et un flux de travail plus simple.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Amélioration de la capacité de démarrage à froid du pool frontal

Skype pour Business Server présente une nouvelle applet de commande qui simplifie et améliore le processus de démarrage à froid d’un pool frontal entier. Quand vous utilisez la nouvelle applet de commande **Start-CsPool**, celle-ci vérifie les conditions préalables pour tous les serveurs frontaux du pool, puis tente de démarrer chaque serveur. Si elle rencontre des problèmes, elle les diagnostique et vous alerte avec des détails et des solutions de contournement. Dans certains cas, elle vous permet de démarrer le pool même si certains des serveurs sont incapables de démarrer.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Prise en charge de SQL Server AlwaysOn pour les serveurs locaux

Skype pour Business Server 2015 ajoute la prise en charge pour les groupes de disponibilité AlwaysOn SQL Server et les Instances de Cluster de basculement SQL Server AlwaysOn. Outre ces fonctionnalités, Skype pour Business Server continue la prise en charge pour la mise en miroir de base de données et le clustering de SQL Server, comme dans les versions précédentes de Lync Server.
  
Groupes de disponibilité AlwaysOn SQL Server est une haute disponibilité et la solution de récupération d’urgence dans SQL Server 2012 et SQL Server 2014 qui offre une alternative à la mise en miroir de base de données. Un groupe de disponibilité prend en charge un environnement de basculement pour un ensemble discret de bases de données (bases de données de disponibilité appelé) basculer l’ensemble. Un groupe de disponibilité prend en charge un ensemble de bases de données primaires en lecture-écriture et un à quatre ensembles de bases de données secondaires correspondantes. Si vous le souhaitez, les bases de données secondaires peuvent être effectuées disponibles pour un accès en lecture seule et pour certaines opérations de sauvegarde.
  
Instances de Cluster de basculement SQL Server tirent parti de la fonctionnalité Clustering de basculement serveur Windows (WSFC) pour fournir la haute disponibilité locale par le biais de la redondance au niveau de l’instance de serveur, une instance de cluster de basculement (FCI). Un FCI est une seule instance de SQL Server qui est installé sur les nœuds du cluster de basculement serveur Windows (WSFC) et, éventuellement, sur plusieurs sous-réseaux.
  
Pour plus d'informations, reportez-vous à la rubrique [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Amélioration de la journalisation centralisée et de la résolution des problèmes sur les serveurs locaux

Le Service de journalisation centralisée est l’environnement de connexion préféré pour Skype pour Business Server 2015. Il n’existe pas de nouvelles fonctionnalités dans cette version, mais la fiabilité et les performances ont été améliorées à la fois pour le service et l’Agent du service de journalisation centralisée (NlsAgent.exe), l’exécutable du service qui communique avec le contrôleur et reçoit des commandes qui sont émises par l’administrateur.
  
Skype pour Business Server 2015 utilise des applets de commande Windows PowerShell pour gérer les agents de service de journalisation, lancer le suivi et générer des rapports. (Lync Server 2013 utilisé ClsController.exe pour effectuer ces tâches.)
  
Le Service de journalisation centralisée puisse s’exécuter sur n’importe quel Skype pour Business Server 2015. Les scénarios intégrés (traces prédéfinies) ne changent pas, tout comme la possibilité de créer des scénarios personnalisés. Il existe un scénario spécial appelé AlwaysOn qui est toujours en exécution et qui permet aux administrateurs de localiser les problèmes courants en temps quasi-réel.
  
L’outil de débogage Snooper a également été mis à jour pour permettre le débogage des journaux de mobilité et fonctionne avec les périphériques connectés à Lync 2013 ou Skype pour Business Server 2015. L’outil est disponible en tant que téléchargement Web à partir des [Outils de débogage](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Gestion et déploiement hybrides

Skype pour Business Server 2015 permet d’administration du déploiement hybride et les fonctionnalités de gestion présente les fonctionnalités suivantes :
  
- Recommandations pour les déploiements hybrides en fonction de l’état des ressources du client local, tel que déterminé par OnRamp for O365 : outil d’assistance automatique.
- Améliorations apportées à la Skype pour le panneau de configuration serveur Business et le Skype pour Business Server Admin Center afin que les administrateurs peuvent utiliser ces outils pour gérer un déploiement hybride.
- Contrôler les améliorations du Panneau de configuration qui permettent aux administrateurs de se connecter à un client O365 et configurer hybride avec Skype pour Business Online à l’aide de l’Assistant configuration hybride.
- Contrôler la prise en charge du Panneau de configuration pour le déplacement des utilisateurs locaux à Skype pour Business Online ou placer Skype pour les utilisateurs professionnels en ligne en local.
- Contrôler les fonctionnalités du Panneau de configuration pour identifier et filtrer les objets utilisateur local qui ont été déplacés vers Skype pour Business Online (autrement dit, les utilisateurs hybride) à partir des utilisateurs locaux.
- Fonctionnalités du centre d’administration pour identifier et filtrer les utilisateurs de nuage initialement créées dans Skype pour Business Online des utilisateurs hybride migrés depuis locale en ligne.
- La possibilité d’administrer des utilisateurs hybride l’aide du panneau Propriétés gérable sur site et centre d’administration pour Skype permet de gérer les propriétés d’entreprise en ligne.
- Utilisation de la synchronisation des mots de passe avec DirSync et possibilité de synchroniser les mots de passe Active Directory locaux avec le locataire en ligne. Si elle est configurée, cette fonction supprime la nécessité de déployer AD FS pour l’authentification fédérée, mais AD FS est toujours nécessaire pour l’authentification multifacteur. 
- Suite à la prise en charge de la coexistence entre Skype pour Business Online et Exchange sur site.
    
> [!NOTE]
> Il n’existe aucune modification par rapport à la Lync Online 2013 et Exchange sur site coexistence et prise en charge de l’expérience. 
  
## <a name="multi-factor-authentication"></a>Authentification multifacteur

L’authentification multifacteur est une méthode d’authentification qui nécessite l’utilisation de plusieurs méthodes de vérification et ajoute une deuxième couche critique de sécurité aux connexions et transactions des utilisateurs. Par exemple, la nécessité d’un nom et d’un mot de passe et un certificat. Skype pour Business Server 2015 continue à générer sur les fonctionnalités de l’authentification multifacteur disponibles dans les mises à jour Cumulative de Lync Server 2013. Les principaux changements introduits dans l’authentification multifacteur sont les suivants :
  
- Utilisation de la bibliothèque d’authentification Active Directory d’Office 2013 SP1 pour l’intégration avec Exchange et SharePoint
- Prise en charge de la fonctionnalité de l’authentification multifacteur dans le Skype pour le client de l’application Web de gestion
    
Avec Skype pour l’authentification multifacteur Business, il est possible de fournir les différentes options d’authentification basées sur l’emplacement géographique. Par exemple, les clients peuvent configurer leur environnement afin que l’authentification interne repose sur l’authentification Windows intégrée, tandis que les employés s’authentifiant en dehors de l’organisation utilisent l’authentification multifacteur. 
  
Le Skype pour une expérience d’authentification multifacteur est transparent, quel que soit :
  
- Emplacement géographique - indique si l’utilisateur est une session depuis à l’intérieur ou à l’extérieur de l’organisation 
- Type de client/périphérique - le Skype pour client d’entreprise est utilisé et le périphérique, le client s’exécute sur (PC, mobile, iPad, etc.).
- Emplacement de - de compte si l’utilisateur est hébergé dans Active Directory sur site ou dans Azure Active Directory Online (O365)