---
title: Nouveautés de Skype Entreprise Server 2015
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
description: 'Résumé : pour en savoir plus sur les nouvelles fonctionnalités, voir Skype entreprise Server 2015. Pour plus d’informations sur la nouvelle interface client, voir Lync devient Skype entreprise--nouveautés.'
ms.openlocfilehash: 0a11c94f7c31b0140a256ab350f5dad6112bc71e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824078"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Nouveautés de Skype Entreprise Server 2015

**Résumé :** Consultez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype entreprise Server 2015. Pour plus d’informations sur la nouvelle interface client, voir [Lync devient Skype entreprise--](https://go.microsoft.com/fwlink/p/?LinkId=529022)nouveautés.
  
Lync devient Skype entreprise, une plate-forme de communication et de collaboration qui réunit une connaissance inspirée de Skype, avec la sécurité et le contrôle de Lync en entreprise. Skype entreprise propose des fonctionnalités telles que la présence, la messagerie instantanée, les appels vocaux et vidéo et les réunions en ligne. Skype entreprise fournit une nouvelle utilisation du client, une nouvelle version du serveur et des mises à jour du service dans Office 365. Si les utilisateurs de votre organisation connaissent déjà Skype, ils apprécieront la puissance et la simplicité de Skype entreprise pour faciliter la recherche et la connexion avec des collègues. Si les utilisateurs de votre organisation arrivent dans Skype entreprise à partir de Lync, ils reconnaîtront toutes les fonctionnalités qu’ils utilisent déjà et dans une nouvelle interface avec des commandes simplifiées et de nouveaux ajouts. Outre la nouvelle interface client, Skype entreprise Server 2015 offre plusieurs nouvelles fonctionnalités pour améliorer la gestion des serveurs locaux et des solutions hybrides.
  
Les nouvelles fonctionnalités de Skype entreprise Server 2015 incluent des améliorations apportées à :
  
- Expérience utilisateur  
- Prise en charge de la voix et de la vidéo
- Prise en charge de la mobilité
- Gestion des serveurs sur site
- Déploiement et gestion de solutions hybrides
- Prise en charge de l’authentification multifacteur
    
## <a name="user-experience"></a>Expérience utilisateur

Le client Skype entreprise ressemble beaucoup à la version grand public de Skype et utilise les mêmes boutons et icônes. Un nombre moindre de menus et une arborescence plus horizontale des tâches permettent de trouver plus rapidement les contrôles et les commandes dont vous avez besoin. 
  
Skype entreprise inclut la nouvelle utilisation de l’utilisateur décrite ci-dessus et l’interface utilisateur de Lync 2013 publiée précédemment. L’inclusion de ces deux expériences permet aux entreprises de gérer le changement de leurs utilisateurs en contrôlant le processus et le calendrier du déploiement du nouveau client. L’utilisation de l’interface utilisateur par défaut dépend de la version du serveur que vous utilisez. Les administrateurs peuvent choisir l’expérience préférée à l’aide de l’applet de commande **Set-CsClientPolicy** avec le paramètre EnableSkypeUI. Pour plus d’informations sur la configuration de l’expérience client, reportez-vous à [la rubrique Configuration de l’expérience client avec Skype entreprise](deploy/deploy-clients/configure-the-client-experience.md) et [comparaison des fonctionnalités du client de bureau pour Skype entreprise](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> L’interface du client 2013 de Lync n’est pas disponible pour les versions clientes de Skype entreprise 2016. Avant de configurer votre environnement client pour qu’il utilise le client 2013 Lync, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro 16 ; par exemple : 16. x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Améliorations de la voix et de la vidéo

Skype entreprise Server 2015 inclut des améliorations apportées aux fonctionnalités audio et vidéo, y compris la collecte et l’analyse des données d’appel, ainsi que l’interopérabilité améliorée avec les systèmes de visioconférence vidéo tiers.
  
### <a name="call-data-collection-and-analysis"></a>Collecte et analyse des données des appels

La fonction taux d’appel permet aux administrateurs 2015 de Skype entreprise Server de collecter des données d’appel. Cette fonctionnalité est disponible uniquement pour les déploiements sur site. Les utilisateurs sont invités à répondre à une enquête au terme de leur appel. Pour plus d’informations, reportez-vous à [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Amélioration de l’interopérabilité avec des systèmes tiers de téléconférence vidéo.

Le serveur vidéo intervient en tant qu’intermédiaire entre les systèmes Skype entreprise Server et Cisco Video Teleconferencing (VTC). Lorsqu’ils rejoignent une réunion, les utilisateurs peuvent maintenant sélectionner un système Cisco VTC. VIS (Video Interop Server) est implémenté en tant que rôle de serveur autonome pour les déploiements sur site. Pour plus d’informations, reportez-vous à la rubrique [planification du serveur Video Interop dans Skype entreprise server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Appel via le bureau

La fonction d’appel via le bureau permet aux utilisateurs d’entreprise de passer des appels vocaux à partir du client Skype entreprise. Lorsqu’un utilisateur place un appel audio, il est acheminé depuis Skype entreprise vers le PBX ou le téléphone RTC de l’émetteur. Une fois que l’utilisateur à l’origine de l’appel répond au téléphone, l’appel est alors dirigé vers le numéro de destination. Le destinataire de l’appel répond et l’appel est établi avec Skype entreprise, comme le panneau de configuration. L’émetteur peut gérer ses contrôles de présence et d’appel à partir de Skype entreprise. Les administrateurs des serveurs activent et configurent la fonctionnalité Appel via le bureau pour leur entreprise. Pour plus d’informations, reportez-vous à la section [planifier un appel via le travail dans Skype entreprise Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Améliorations apportées à la prise en charge des appareils mobiles

Les améliorations apportées à la prise en charge des appareils mobiles incluent des fonctionnalités permettant d’améliorer l’expérience mobile pour les utilisateurs d’Enterprise Edition, par exemple pour accéder à l’historique des conversations et aux données de journalisation, expériences de réunion mobile améliorées et prise en charge de l’authentification unique dans Office. De plus, il existe des améliorations apportées à la prise en charge de Android, des améliorations des performances et des fonctionnalités permettant de simplifier l’intégration via l’infrastructure d’application commune. 
  
> [!NOTE]
> Les serveurs UCWA Lync 2013 doivent être mis à niveau vers Skype entreprise Server 2015 pour la prise en charge des clients mobiles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>L’historique des conversations côté serveur est maintenant disponible sur les appareils mobiles

Pour permettre l’accès mobile aux données de l’historique des conversations, de la messagerie instantanée manquée et du journal des appels, l’archivage de ces informations est désormais traité via le serveur pour tous les clients mobiles. La fonction Accepter automatiquement pour la messagerie instantanée améliore la fiabilité en empêchant les messages de dépassement du délai du serveur quand un utilisateur mobile ne répond pas immédiatement à un message instantané. Pour tirer parti de l’intégration de dossiers Exchange/Outlook basée sur Server, vous devez disposer d’Exchange Server 2013 ou version ultérieure, et de clients mobiles mis à jour. 
  
### <a name="enhanced-meeting-experiences"></a>Amélioration de l’expérience des réunions

La fonctionnalité des réunions disponible sur le bureau est maintenant disponible pour les utilisateurs mobiles. Cette nouvelle fonctionnalité comprend ce qui suit :
  
- Navigation asynchrone du contenu PowerPoint partagé
- La capacité du présentateur à prendre le contrôle du contenu PowerPoint partagé
- Gestion de la salle d’attente pour les présentateurs, leur permettant d’accepter ou de refuser des participants
    
### <a name="skype-for-business-on-android-improvements"></a>Améliorations de Skype entreprise sur Android

Skype entreprise sur Android propose désormais des fonctions similaires à celles disponibles dans Skype entreprise pour iOS et Skype entreprise sur Windows :
  
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

Skype entreprise Server 2015 offre plusieurs nouvelles fonctionnalités permettant d’améliorer la gestion des serveurs locaux, y compris la mise à niveau sur place, la configuration intelligente, les processus de mise à jour et de mise à niveau améliorés, la fonctionnalité de démarrage à froid de la liste frontale améliorée, SQL Server alwaysn support et journalisation centralisée et résolution des problèmes.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Mise à niveau sur place pour les serveurs locaux

Vous pouvez à présent mettre à niveau les systèmes Lync Server 2013 vers Skype entreprise Server 2015 à l’aide de la nouvelle fonctionnalité de mise à niveau sur place, qui utilise les investissements de matériel et serveur Lync Server 2013 existants, ce qui réduit le coût global de déploiement de Skype entreprise Server 2015.
  
Il existe deux scénarios pour la mise à niveau sur place : la méthode Déplacer l’utilisateur, qui ne demande aucun temps d’arrêt, et la méthode Hors ligne, qui exige un temps d’arrêt. Pour plus d’informations sur la meilleure option pour votre entreprise, reportez-vous à [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> L’option d’emplacement n’est pas disponible si vous effectuez une mise à niveau à partir de Lync Server 2010. Pour plus d’informations sur la mise à niveau de Lync Server 2010, voir [planifier la mise à niveau vers Skype entreprise server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Installation intelligente (Smart Setup)

La fonctionnalité d’installation intelligente, qui détecte et télécharge automatiquement les mises à jour, fait partie intégrante du programme d’installation. Pendant le processus d’installation, l’utilisateur est invité à indiquer si le processus d’installation doit rechercher les mises à jour. Pour plus d’informations, reportez-vous à [Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Amélioration du processus des correctifs et de mise à jour du serveur frontal

Skype entreprise Server introduit deux nouvelles applets de nouvelle applet de création permettant de mettre à niveau ou de mettre à jour les serveurs frontaux plus facilement que dans les versions précédentes de Lync Server.
  
Lorsque vous devez appliquer un correctif ou effectuer une autre maintenance, sur un serveur frontal, il suffit de taper **Invoke-CsComputerFailOver** et de spécifier ce nom de serveur. Skype entreprise Server déplace temporairement la charge de travail de ce serveur vers les autres serveurs de la liste. Vous pouvez ensuite effectuer l’opération de maintenance, puis utiliser l’applet de commande **Invoke-CsComputerFailback** pour remettre ce serveur en service. Si vous avez besoin d’appliquer un correctif à chaque serveur d’un pool, il suffit de suivre cette procédure pour chaque serveur, un à la fois. Ces nouvelles applets de commande vous permettent d’installer les correctifs des serveurs beaucoup plus rapidement que dans les versions précédentes et avec plus de fiabilité et un flux de travail plus simple.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Amélioration de la capacité de démarrage à froid du pool frontal

Skype entreprise Server introduit une nouvelle applet de nouvelle cmdlet qui simplifie et améliore le processus de démarrage à froid d’un pool frontal complet. Quand vous utilisez la nouvelle applet de commande **Start-CsPool**, celle-ci vérifie les conditions préalables pour tous les serveurs frontaux du pool, puis tente de démarrer chaque serveur. Si elle rencontre des problèmes, elle les diagnostique et vous alerte avec des détails et des solutions de contournement. Dans certains cas, elle vous permet de démarrer le pool même si certains des serveurs sont incapables de démarrer.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Prise en charge de SQL Server AlwaysOn pour les serveurs locaux

Skype entreprise Server 2015 ajoute une prise en charge des groupes de disponibilité SQL Server AlwaysOn et des instances de cluster de basculement SQL Server AlwaysOn. Outre ces fonctions, Skype entreprise Server continue de prendre en charge la mise en miroir de base de données et le regroupement SQL Server comme dans les versions précédentes de Lync Server.
  
Le groupe de disponibilité SQL Server AlwaysOn est une solution de haute disponibilité et de récupération d’urgence dans SQL Server 2012 et SQL Server 2014 qui offre une alternative à la mise en miroir de la base de données. Un groupe de disponibilité prend en charge un environnement de basculement pour un ensemble discret de bases de données (appelées bases de données de disponibilité) qui échouent ensemble. Un groupe de disponibilité prend en charge un ensemble de bases de données principales en lecture-écriture et un à quatre ensembles de bases de données secondaires correspondantes. Les bases de données secondaires peuvent éventuellement être mises à disposition d’un accès en lecture seule et de certaines opérations de sauvegarde.
  
Les instances de cluster de basculement SQL Server exploitent les fonctionnalités de clustering par basculement de Windows Server (WSFC) pour fournir une disponibilité élevée locale via la redondance au niveau de l’instance de serveur, une instance de cluster de basculement (ICF). Un ICF est une instance unique de SQL Server installée sur des nœuds de clustering (WSFC) de basculement de Windows Server et éventuellement sur plusieurs sous-réseaux.
  
Pour plus d'informations, reportez-vous à la rubrique [Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Amélioration de la journalisation centralisée et de la résolution des problèmes sur les serveurs locaux

Le service de journalisation centralisé est l’environnement de connexion préféré pour Skype entreprise Server 2015. Il n’existe pas de nouvelles fonctionnalités dans cette version, mais la fiabilité et les performances ont été améliorées à la fois pour le service et l’Agent du service de journalisation centralisée (NlsAgent.exe), l’exécutable du service qui communique avec le contrôleur et reçoit des commandes qui sont émises par l’administrateur.
  
Skype entreprise Server 2015 utilise des cmdlets Windows PowerShell pour gérer les agents de service de journalisation, lancer le suivi et générer des rapports. (Lync Server 2013 a utilisé ClsController. exe pour effectuer ces tâches.)
  
Le service de journalisation centralisé peut s’exécuter sur n’importe quel serveur Skype entreprise Server 2015. Les scénarios intégrés (traces prédéfinies) ne changent pas, tout comme la possibilité de créer des scénarios personnalisés. Il existe un scénario spécial appelé AlwaysOn qui est toujours en exécution et qui permet aux administrateurs de localiser les problèmes courants en temps quasi-réel.
  
L’outil de débogage Snoop a également été mis à jour pour permettre le débogage des journaux de mobilité et fonctionne avec des appareils qui se connectent à Lync 2013 ou Skype entreprise Server 2015. L’outil est disponible sous la forme d’un téléchargement Web à partir d' [outils de débogage](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Gestion et déploiement hybrides

Skype entreprise Server 2015 offre des fonctionnalités d’administration et de gestion hybrides du déploiement en introduisant les fonctionnalités suivantes :
  
- Recommandations en matière de déploiements hybrides en fonction de l’état des ressources locales du client, tel que déterminé par l’outil d’assistance automatique OnRamp pour O365.
- Les améliorations apportées au panneau de configuration Skype entreprise Server et au centre d’administration de Skype entreprise Server permettent aux administrateurs d’utiliser ces outils pour gérer un déploiement hybride.
- Les améliorations apportées au panneau de configuration permettent aux administrateurs de se connecter à un client O365 et de configurer une connexion hybride avec Skype entreprise Online à l’aide de l’Assistant Configuration hybride.
- Le panneau de configuration est pris en charge pour les utilisateurs de Skype entreprise Online, ou vers les utilisateurs de Skype entreprise online.
- Fonctionnalités du panneau de configuration pour identifier et filtrer les objets utilisateurs locaux qui ont été déplacés vers Skype entreprise Online (c’est-à-dire, les utilisateurs hybrides) des utilisateurs locaux.
- Les fonctionnalités du centre d’administration permettent d’identifier et de filtrer les utilisateurs Cloud initialement créés dans Skype entreprise Online à partir des utilisateurs hybrides migrés de local vers connecté.
- La possibilité de gérer les utilisateurs hybrides à l’aide du panneau de configuration pour les propriétés gérables depuis le centre d’administration et les propriétés gérables par Skype entreprise online.
- Utilisation de la synchronisation des mots de passe avec DirSync et possibilité de synchroniser les mots de passe Active Directory locaux avec le locataire en ligne. Si elle est configurée, cette fonction supprime la nécessité de déployer AD FS pour l’authentification fédérée, mais AD FS est toujours nécessaire pour l’authentification multifacteur. 
- Prenez en charge la coexistence entre Skype entreprise Online et Exchange en local.
    
> [!NOTE]
> Il n’y a aucune modification par rapport à l’interface utilisateur et au support technique de Lync Online 2013 et d’Exchange. 
  
## <a name="multi-factor-authentication"></a>Authentification multifacteur

L’authentification multifacteur est une méthode d’authentification qui nécessite l’utilisation de plusieurs méthodes de vérification et ajoute une deuxième couche critique de sécurité aux connexions et transactions des utilisateurs. Par exemple, la nécessité d’un nom et d’un mot de passe et un certificat. Skype entreprise Server 2015 continue de s’appuyer sur les fonctionnalités d’authentification multifacteur disponibles dans les mises à jour cumulatives de Lync Server 2013. Les principaux changements introduits dans l’authentification multifacteur sont les suivants :
  
- Utilisation de la bibliothèque d’authentification Active Directory d’Office 2013 SP1 pour l’intégration avec Exchange et SharePoint
- Prise en charge de la fonctionnalité d’authentification multifacteur dans le client Skype entreprise Web App
    
Avec l’authentification multifacteur de Skype entreprise, il est désormais possible d’offrir différentes options d’authentification en fonction de votre géographie. Par exemple, les clients peuvent configurer leur environnement afin que l’authentification interne repose sur l’authentification Windows intégrée, tandis que les employés s’authentifiant en dehors de l’organisation utilisent l’authentification multifacteur. 
  
L’interface d’authentification multifacteur de Skype entreprise est transparente, quels que soient les éléments suivants :
  
- Emplacement géographique : si l’utilisateur se connecte à l’intérieur ou à l’extérieur de l’organisation. 
- Client/type d’appareil : le client Skype entreprise est utilisé et l’appareil sur lequel s’exécute le client (PC, mobile, iPad, etc.)
- Emplacement du compte : indique si l’utilisateur est hébergé dans un environnement Active Directory local ou dans Azure Active Directory Online (O365)
