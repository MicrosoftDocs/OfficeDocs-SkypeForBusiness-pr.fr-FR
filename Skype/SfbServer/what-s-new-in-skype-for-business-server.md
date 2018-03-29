---
title: Nouveautés de Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype pour Business Server 2015. Pour obtenir des informations détaillées sur l’expérience du client, consultez que Lync est désormais Skype pour les entreprises : Voir nouveautés.'
ms.openlocfilehash: 0d8172e5031f8b2e51373051b2674e99f5539b6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Nouveautés de Skype Entreprise Server 2015

**Résumé :** Lisez cette rubrique pour en savoir plus sur les nouvelles fonctionnalités de Skype pour Business Server 2015. Pour obtenir des informations détaillées sur l’expérience du client, reportez-vous à la section [Lync est maintenant Skype pour entreprise--Voir nouveautés](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync est désormais Skype pour plate-forme Business, une communication et de collaboration qui réunit une expérience inspiré par Skype avec la sécurité de l’entreprise, la conformité et le contrôle de Lync. Skype pour entreprise propose des fonctionnalités, y compris la présence, messagerie instantanée, voix des appels vidéo et des réunions en ligne. Skype pour entreprise fournit un nouveau client, expérience, une nouvelle version de serveur et les mises à jour pour le service dans Office 365. Si les utilisateurs de votre organisation sont déjà familiarisés avec Skype, ils apprécieront la puissance et la simplicité de Skype pour les entreprises où il est facile de trouver et de communiquer avec vos collègues. Si provenant des utilisateurs de votre organisation à Skype pour entreprise de Lync, ils vous reconnaîtrez, toutes les fonctionnalités qu’ils déjà utilisent mais ils dans une nouvelle interface de frais avec les contrôles et les nouveaux ajouts. En plus de la nouvelle expérience client, Skype pour Business Server 2015 fournit plusieurs nouvelles fonctionnalités pour améliorer la gérabilité des serveurs sur site et les solutions hybrides.
  
Nouvelles fonctionnalités de Skype pour Business Server 2015 incluent des améliorations :
  
- Expérience utilisateur  
- Prise en charge de la voix et de la vidéo
- Prise en charge de la mobilité
- Gestion des serveurs sur site
- Déploiement et gestion de solutions hybrides
- Prise en charge de l’authentification multifacteur
    
## <a name="user-experience"></a>Expérience utilisateur

Le Skype pour client d’entreprise très similaire à la version consommateur de Skype et utilise les mêmes boutons et icônes. Un nombre moindre de menus et une arborescence plus horizontale des tâches permettent de trouver plus rapidement les contrôles et les commandes dont vous avez besoin. 
  
Skype pour entreprise inclut la nouvelle expérience utilisateur décrit ci-dessus et l’expérience utilisateur de Lync 2013 publié précédemment. L’inclusion de ces deux expériences permet aux entreprises de gérer les modifications que les utilisateurs en contrôlant le processus et le minutage de la nouvelle client sortie. L’expérience de l’utilisateur par défaut dépend de la version du serveur que vous utilisez. Les administrateurs peuvent choisir l’expérience préférée à l’aide de l’applet de commande **Set-CsClientPolicy** avec le paramètre EnableSkypeUI. Pour plus d’informations sur la configuration de l’expérience du client, consultez [configurer le client expérience avec Skype pour les entreprises](deploy/deploy-clients/configure-the-client-experience.md) et [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> L’expérience du client Lync 2013 n’est pas une option pour Skype pour les versions clientes de 2016 de l’entreprise. Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez la version du client pour vous assurer qu’il ne démarre pas avec le nombre 16 ; par exemple : 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Améliorations de la voix et de la vidéo

Skype pour Business Server 2015 comprend des améliorations aux fonctionnalités de voix et vidéo, y compris la collecte de données d’appel et d’analyse et d’une meilleure interopérabilité avec les systèmes tiers de vidéoconférences.
  
### <a name="call-data-collection-and-analysis"></a>Collecte et analyse des données des appels

La taux de mon appel fonction vous permet de Skype pour les administrateurs d’entreprise serveur 2015 collecte des données de l’appel. Cette fonctionnalité est disponible uniquement pour les déploiements sur site. Les utilisateurs sont invités à répondre à une enquête au terme de leur appel. Pour plus d’informations, voir [taux de mon appel dans Skype pour Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Amélioration de l’interopérabilité avec des systèmes tiers de téléconférence vidéo.

Le serveur d’interopérabilité vidéo (VIS) joue le rôle d’intermédiaire entre Skype pour Business Server et Cisco systems de téléconférence vidéo (VTC). Lorsqu’ils rejoignent une réunion, les utilisateurs peuvent maintenant sélectionner un système Cisco VTC. VIS (Video Interop Server) est implémenté en tant que rôle de serveur autonome pour les déploiements sur site. Pour plus d’informations, reportez-vous à [planification pour serveur d’interopérabilité vidéo dans Skype pour Business Server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Appel via le bureau

L’appel via la fonctionnalité de travail permet aux utilisateurs d’enterprise effectuer des appels vocaux à partir de la Skype pour client d’entreprise. Lorsqu’un utilisateur place un appel vocal, il est acheminé dans Skype pour les entreprises à l’expéditeur PBX ou un téléphone RTC. Une fois que l’utilisateur à l’origine de l’appel répond au téléphone, l’appel est alors dirigé vers le numéro de destination. Les réponses de destinataire d’appel et l’appel est établie avec Skype pour entreprise agissant comme le panneau de configuration. L’expéditeur peut gérer leur présence et appeler des contrôles à partir de Skype pour les entreprises. Les administrateurs des serveurs activent et configurent la fonctionnalité Appel via le bureau pour leur entreprise. Pour plus d’informations, reportez-vous à [planification pour appeler Via le travail dans Skype pour Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Améliorations apportées à la prise en charge des appareils mobiles

Améliorations apportées à la prise en charge des périphériques mobiles incluent des fonctionnalités pour améliorer l’expérience mobile pour les utilisateurs de Enterprise Edition, comme l’accès aux données de l’historique et journal de conversation, les expériences d’améliorée de réunion mobiles et support d’ouverture de session unique sur le bureau. En outre, il existe des améliorations en matière de prise en charge Android, performances et fonctionnalités qui simplifient l’intégration via l’infrastructure d’application commune. 
  
> [!NOTE]
> Les serveurs Lync 2013 UCWA doivent être mis à niveau à Skype pour 2015 de serveur d’entreprise prendre en charge les clients mobiles. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>L’historique des conversations côté serveur est maintenant disponible sur les appareils mobiles

Pour activer l’accès mobile à l’historique des conversations manquées de messagerie instantanée et données de journal d’appel, l’archivage de ces informations est désormais traité par le serveur pour tous les clients mobiles. La fonction Accepter automatiquement pour la messagerie instantanée améliore la fiabilité en empêchant les messages de dépassement du délai du serveur quand un utilisateur mobile ne répond pas immédiatement à un message instantané. Pour tirer parti de l’intégration de dossiers de serveur Exchange/Outlook, Exchange Server 2013 ou nouveaux et mis à jour, les clients mobiles, sont requis. 
  
### <a name="enhanced-meeting-experiences"></a>Amélioration de l’expérience des réunions

La fonctionnalité des réunions disponible sur le bureau est maintenant disponible pour les utilisateurs mobiles. Cette nouvelle fonctionnalité comprend ce qui suit :
  
- Navigation asynchrone du contenu PowerPoint partagé
- Permet de prendre le contrôle de PowerPoint partagé contenu du présentateur
- Gestion de la salle d’attente pour les présentateurs, leur permettant d’accepter ou de refuser des participants
    
### <a name="skype-for-business-on-android-improvements"></a>Skype pour le commerce sur améliorations Android

Skype pour le commerce sur Android offre désormais des fonctionnalités similaires à ce qui est disponible sur Skype pour entreprise sur iOS et Skype pour le commerce sur Windows :
  
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

Skype pour Business Server 2015 fournit plusieurs nouvelles fonctionnalités pour améliorer la gestion des serveurs sur site, y compris à niveau sur place, le programme d’installation dynamique, correction améliorée et mise à niveau des processus, une meilleure capacité de démarrage à froid de pool de Front-End, SQL Server AlwaysOn prise en charge et centralisée journalisation et le dépannage.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Mise à niveau sur place pour les serveurs locaux

Vous pouvez désormais mettre à niveau les systèmes de Lync Server 2013 à Skype pour Business Server 2015 à l’aide de la fonctionnalité de mise à niveau sur place nouveau, qui utilise des investissements existants de Lync Server 2013 matériel et le serveur, ce qui réduit le coût total pour déployer Skype pour Business Server 2015.
  
Il existe deux scénarios pour la mise à niveau sur place : la méthode Déplacer l’utilisateur, qui ne demande aucun temps d’arrêt, et la méthode Hors ligne, qui exige un temps d’arrêt. Pour plus d’informations sur les procédure de mise à niveau est adaptée à votre entreprise, consultez [mise à niveau à Skype pour Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> L’option de remplacement n’est pas disponible si vous mettez à niveau à partir de Lync Server 2010. Pour plus d’informations sur la mise à niveau à partir de Lync Server 2010, reportez-vous à la section [planifier la mise à niveau vers Skype pour Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Installation intelligente (Smart Setup)

La fonctionnalité d’installation intelligente, qui détecte et télécharge automatiquement les mises à jour, fait partie intégrante du programme d’installation. Pendant l’installation, l’utilisateur est invité si le processus d’installation doit vérifier les mises à jour. Pour plus d’informations, consultez [Installation de Skype pour Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Amélioration du processus des correctifs et de mise à jour du serveur frontal

Skype pour Business Server introduit deux nouvelles applets de commande qui permettent de rendre la mise à niveau ou une correction des serveurs frontaux beaucoup plus facile que dans les versions précédentes de Lync Server.
  
Lorsque vous devez appliquer un correctif, ou exécuter les autres opérations de maintenance, pour un serveur frontal simplement tapez **Invoke-CsComputerFailOver** , spécifiez le nom de ce serveur. Skype pour Business Server déplace la charge de travail de ce serveur temporairement vers les autres serveurs dans le pool. Vous pouvez ensuite effectuer l’opération de maintenance, puis utiliser l’applet de commande **Invoke-CsComputerFailback** pour remettre ce serveur en service. Si vous avez besoin d’appliquer un correctif à chaque serveur d’un pool, il suffit de suivre cette procédure pour chaque serveur, un à la fois. Ces nouvelles applets de commande vous permettent d’installer les correctifs des serveurs beaucoup plus rapidement que dans les versions précédentes et avec plus de fiabilité et un flux de travail plus simple.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Amélioration de la capacité de démarrage à froid du pool frontal

Skype pour Business Server introduit une nouvelle applet de commande qui simplifie et améliore le processus de démarrage à froid d’un pool entier de Front-End. Quand vous utilisez la nouvelle applet de commande **Start-CsPool**, celle-ci vérifie les conditions préalables pour tous les serveurs frontaux du pool, puis tente de démarrer chaque serveur. Si elle rencontre des problèmes, elle les diagnostique et vous alerte avec des détails et des solutions de contournement. Dans certains cas, elle vous permet de démarrer le pool même si certains des serveurs sont incapables de démarrer.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Prise en charge de SQL Server AlwaysOn pour les serveurs locaux

Skype pour Business Server 2015 prend en charge les groupes de disponibilité AlwaysOn de SQL Server et les Instances de clusters avec basculement SQL Server AlwaysOn. Outre ces fonctionnalités, Skype pour Business Server continue de prise en charge de la mise en miroir de base de données et mise en cluster de SQL Server, comme dans les versions précédentes de Lync Server.
  
Groupes de disponibilité AlwaysOn de SQL Server est une solution de reprise après sinistre dans SQL Server 2012 et 2014 de SQL Server qui fournit une alternative à la mise en miroir de base de données et de haute disponibilité. Un groupe de disponibilité prend en charge un environnement de basculement d’une liste de bases de données (appelés des bases de données de disponibilité) basculent ensemble. Un groupe de disponibilité prend en charge un ensemble de bases de données primaires en lecture-écriture et d’un à quatre des ensembles de bases de données secondaires correspondantes. Le cas échéant, des bases de données secondaires peuvent être accessibles pour l’accès en lecture seule et pour certaines opérations de sauvegarde.
  
Instances de clusters avec basculement SQL Server exploiter la fonctionnalité de Clustering de basculement serveur Windows (WSFC) pour fournir une disponibilité élevée grâce à la redondance au niveau de l’instance de serveur locale, une instance de cluster de basculement (FCI). Un FCI est une instance unique de SQL Server qui est installé sur les nœuds de cluster de basculement serveur Windows (WSFC) et, éventuellement, sur plusieurs sous-réseaux.
  
Pour plus d’informations, consultez [planification de la haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Amélioration de la journalisation centralisée et de la résolution des problèmes sur les serveurs locaux

Le Service de journalisation centralisée est l’environnement de connexion préféré pour Skype pour Business Server 2015. Il n’existe pas de nouvelles fonctionnalités dans cette version, mais la fiabilité et les performances ont été améliorées à la fois pour le service et l’Agent du service de journalisation centralisée (NlsAgent.exe), l’exécutable du service qui communique avec le contrôleur et reçoit des commandes qui sont émises par l’administrateur.
  
Skype pour Business Server 2015 utilise des applets de commande Windows PowerShell pour gérer les agents de service d’enregistrement, de suivi de lancer et de générer des rapports. (Lync Server 2013 utilisé ClsController.exe pour effectuer ces tâches.)
  
Le Service de journalisation centralisée peut s’exécuter sur n’importe quel Skype pour Business Server 2015. Les scénarios intégrés (traces prédéfinies) ne changent pas, tout comme la possibilité de créer des scénarios personnalisés. Il existe un scénario spécial appelé AlwaysOn qui est toujours en exécution et qui permet aux administrateurs de localiser les problèmes courants en temps quasi-réel.
  
L’outil de débogage détecte également a été mis à jour pour permettre le débogage des journaux de mobilité et fonctionne avec les périphériques de connexion à Lync 2013 ou Skype pour Business Server 2015. L’outil est disponible sous la forme d’un téléchargement Web à partir des [Outils de débogage](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Gestion et déploiement hybrides

Skype pour Business Server 2015 permet les fonctions de gestion et d’administration du déploiement hybride présente les fonctionnalités suivantes :
  
- Recommandations pour les déploiements hybride basées sur l’état des actifs des locaux du client, tel que déterminé par la OnRamp pour l’outil d’assistance automatisée O365.
- Améliorations apportées à la Skype pour panneau de Business Server et le Skype pour Business Server Admin Center afin que les administrateurs peuvent utiliser ces outils pour gérer un déploiement hybride.
- Contrôler les améliorations du panneau qui permettent aux administrateurs de se connecter à un locataire O365 et configurer hybride avec Skype pour Business Online à l’aide de l’Assistant de configuration hybride.
- Contrôle la prise en charge de panneau pour le déplacement des utilisateurs locaux à Skype pour Business Online ou placer Skype pour les utilisateurs professionnels en ligne en local.
- Contrôler les fonctions de panneau pour identifier et filtrer les objets utilisateur sur site qui ont été déplacés à Skype pour Business Online (autrement dit, les utilisateurs hybride) à partir d’utilisateurs locaux.
- Fonctionnalités du centre d’administration pour identifier et filtrer les utilisateurs de nuage initialement créés dans Skype pour entreprise en ligne des utilisateurs de hybride migrés du site en ligne.
- La possibilité d’administrer les utilisateurs hybride en utilisant le panneau Propriétés gérables à partir de locaux et Admin Center pour Skype permet de gérer les propriétés d’activité en ligne.
- Utilisation de la synchronisation des mots de passe avec DirSync et possibilité de synchroniser les mots de passe Active Directory locaux avec le locataire en ligne. Si elle est configurée, cette fonction supprime la nécessité de déployer AD FS pour l’authentification fédérée, mais AD FS est toujours nécessaire pour l’authentification multifacteur. 
- Suite à la prise en charge de la coexistence entre Skype pour Business Online et Exchange sur site.
    
> [!NOTE]
> Il n’y a aucune modification de l’expérience du support et la coexistence sur site Lync Online 2013 et Exchange. 
  
## <a name="multi-factor-authentication"></a>Authentification multifacteur

L’authentification multifacteur est une méthode d’authentification qui nécessite l’utilisation de plusieurs méthodes de vérification et ajoute une deuxième couche critique de sécurité aux connexions et transactions des utilisateurs. Par exemple, la nécessité d’un nom et d’un mot de passe et un certificat. Skype pour Business Server 2015 continue à renforcer les fonctionnalités de plusieurs facteurs d’authentification disponibles dans les mises à jour Cumulative de Lync Server 2013. Les principaux changements introduits dans l’authentification multifacteur sont les suivants :
  
- Utilisation de la bibliothèque d’authentification Active Directory d’Office 2013 SP1 pour l’intégration avec Exchange et SharePoint
- Prise en charge de la fonctionnalité d’authentification à plusieurs facteurs dans la Skype pour client d’entreprise Web App
    
Avec Skype pour l’entreprise une authentification multifacteur, il est maintenant possible de fournir des options d’authentification basées sur l’emplacement géographique. Par exemple, les clients peuvent configurer leur environnement afin que l’authentification interne repose sur l’authentification Windows intégrée, tandis que les employés s’authentifiant en dehors de l’organisation utilisent l’authentification multifacteur. 
  
Le Skype pour une expérience plusieurs facteurs d’authentification est transparente, quelle que soit :
  
- Emplacement géographique : si l’utilisateur est une session depuis l’intérieur ou à l’extérieur de l’organisation 
- Type de périphérique client - le Skype pour client d’entreprise est utilisé et le périphérique qui le client est en cours d’exécution (PC, mobile, iPad, etc.).
- Emplacement - du compte si l’utilisateur est hébergé dans un local d’Active Directory ou dans Azure Active Directory Online (O365)