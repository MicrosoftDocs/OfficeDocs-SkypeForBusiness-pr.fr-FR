---
title: "Lync Server 2013 : Nlles fonctionnalités du serveur de conversation permanente"
TOCTitle: Nouvelles fonctionnalités du serveur de conversation permanente
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412965(v=OCS.15)
ms:contentKeyID: 49298751
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nouvelles fonctionnalités du serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans Lync Server 2013, le serveur de conversations permanentes permet de participer à des conversations permanentes à plusieurs personnes et portant sur des sujets particuliers. Avec le serveur de conversations permanentes, votre organisation peut :

  - améliorer la communication entre des équipes géographiquement dispersées et multifonctionnelles ;

  - élargir la prise en compte des informations et la participation ;

  - améliorer la communication dans l’ensemble de votre organisation ;

  - réduire la surcharge d’informations ;

  - améliorer la prise en compte des informations ;

  - accroître la dissémination des connaissances et des informations importantes.

Le serveur de conversations permanentesLync Server 2013 n’est pas disponible dans Microsoft Office 365. Il n’est actuellement proposé que pour les clients Lync 2013 locaux.

Dans Lync 2013, la fonctionnalité conversation permanente est intégrée au client Lync 2013. Par conséquent, les utilisateurs ont accès à la messagerie instantanée/présence, aux fichiers audio/vidéo, aux conférences et au conversation permanente sur le client Lync 2013. Pour plus d’informations sur ce client Lync 2013, reportez-vous à <http://go.microsoft.com/fwlink/p/?linkid=270877>.

Cette rubrique décrit les changements apportés aux fonctionnalités entre la nouvelle version du serveur de conversations permanentesLync Server 2013 et la version précédente ( Microsoft Lync Server 2010, conversation de groupe), notamment :

  - Possibilité d’effectuer des opérations d’administration dans le Panneau de configuration Lync Server, et suppression de l’outil d’administration Group Chat

  - Intégration des paramètres de configuration du serveur de conversations permanentes dans le générateur de topologie, et suppression de l’outil de configuration Group Chat

  - Transfert et mise à niveau facilités à partir des versions précédentes du serveur de conversations permanentes

  - Solutions à haute disponibilité et de récupération d’urgence

Pour plus d’informations sur la dernière version du serveur de conversations permanentes, reportez-vous aux ressources suivantes :

  - L’aide conversation permanente, disponible à l’adresse <http://go.microsoft.com/fwlink/p/?linkid=270945>, qui fournit la liste détaillée des fonctionnalités conversation permanente et décrit leurs fonctionnement et mode d’utilisation lors de l’exécution de serveur de conversations permanentes.

  - La rubrique [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, la rubrique [Déploiement d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) dans la documentation de déploiement, la rubrique [Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) dans la documentation de transfert et la rubrique [Gestion de Lync Server 2013, serveur de conversation permanente](managing-lync-server-2013-persistent-chat-server.md) dans la documentation des opérations. Toutes ces rubriques fournissent des instructions sur la configuration du serveur de conversations permanentes.

  - Le fichier Documentation.msi (fichier Windows Installer) du serveur de conversations permanentes, qui permet aux utilisateurs d’accéder hors connexion à une documentation complète sur le serveur de conversations permanentes.

## Principales modifications apportées à la topologie du serveur de conversations permanentes

Les modifications importantes suivantes ont été apportées au serveur de conversations permanentes :

Le serveur de conversations permanentes est maintenant un rôle serveur. Dans Microsoft Lync Server 2010, le serveur Group Chat était une application tierce approuvée pour Microsoft Lync Server 2010. La fonctionnalité de conversation permanente peut être ajoutée à votre topologie Lync Server 2013 à l’aide du Générateur de topologie. Dans Lync Server 2013, la fonctionnalité de serveur de conversations permanentes est implémentée au moyen de trois nouveaux rôles serveur :

  - **PersistentChatService** : rôle serveur frontal pour la conversation permanente. Dans les déploiements Standard Edition, le rôle de service de serveur de conversations permanentes est colocalisé sur le serveur Standard Edition déployé par le programme d’amorçage, comme tous les autres rôles Lync Server. Dans les déploiements Enterprise Edition, le rôle de service de conversation permanente est déployé sur les ordinateurs autonomes par le programme d’amorçage, comme tous les autres rôles Lync Server.

  - **PersistentChatStore** : serveur principal correspondant à la base de données de contenu de conversation permanente, où toutes les conversations sont stockées.

  - **PersistentChatComplianceStore** : rôle serveur principal correspondant à la base de données de conformité de conversation permanente, où sont stockés tous les événements de conformité.

Ces rôles facultatifs de serveur de conversations permanentes sont conçus uniquement pour les clients ayant besoin des fonctionnalités complètes du serveur de conversations permanentes. Le rôle **PersistentChatComplianceStore** n’est nécessaire que si vous déployez la fonctionnalité de conformité de conversation permanente.

Le rôle **PersistentChatService** exécute les deux services suivants :

  - Service de conversation permanente

  - Service de conformité de conversation permanente

L’exécution de ces services sur chaque serveur de conversations permanentes permet de bénéficier de services de haute disponibilité dans un pool de serveurs de conversations permanentes multiserveur.

En outre, pour garantir la prise en charge du chargement et du téléchargement de fichiers dans les salles de conversation permanente, le serveur de conversations permanentes intègre un service web. Dans la version précédente, ce service était colocalisé sur le serveur frontal du serveur de conversations permanentes et nécessitait l’installation préalable des services Internet (IIS). Sur le serveur de conversations permanentesLync Server 2013, le service web de chargement/téléchargement de fichiers est colocalisé avec le serveur frontalLync Server 2013. Par conséquent, il n’est plus nécessaire d’installer les services Internet (IIS) pour le serveur de conversations permanentes. Le service web de chargement/téléchargement de fichiers est identifié sous le nom **PersistentChat** dans le Gestionnaire des services Internet (IIS).

> [!IMPORTANT]  
> Le rôle <strong>PersistentChatService</strong> peut être exécuté sur le même serveur qu’un serveur frontalLync Server 2013 seulement si ce serveur frontal est un serveur frontalStandard Edition. Le rôle <strong>PersistentChatService</strong> ne peut pas être exécuté indépendamment d’un serveur frontal  Lync Server 2013. Il ne peut être installé que dans le cadre d’un déploiement de Lync Server 2013.

Le serveur de conversations permanentes ne contient plus le service de recherche. Dans Lync Server 2010, conversation de groupe, ce service était exécuté sur chaque serveur frontal du serveur Group Chat pour effectuer le routage vers l’un des serveurs de canal. Pour le routage, Lync Server 2013 utilise des objets contact, chacun représentant un pool de serveurs de conversations permanentes. Les serveurs frontaux  Lync Server se réfèrent aux objets contact pour identifier les demandes et les acheminer vers un pool de serveurs de conversations permanentes approprié et vers l’un des ordinateurs exécutant le serveur de conversations permanentes dans ce pool.

Dans Lync Server 2013, le service de conformité a été modifié, comme détaillé ci-dessous :

  - Dans Lync Server 2010, le service de conformité n’était exécuté qu’en mode autonome (non colocalisé) et que sur un seul serveur. Ce service s’exécute maintenant sur tous les serveurs frontaux du serveur de conversations permanentes, avec le service de conversation permanente, ce qui apporte une haute disponibilité au pool de serveurs de conversations permanentes multiserveur. Vous pouvez configurer une seule carte de conformité pour extraire les données de la base de données de conformité et les ajouter à l’un des autres systèmes (fichier XML, archives Exchange hébergées, etc.). Le serveur de conversations permanentes inclut une carte XML.

  - La file d’attente Microsoft Message Queuing (ou MSMQ) utilisée conjointement par le service de conversation permanente et le service de conformité sur chaque serveur frontal du serveur de conversations permanentes est désormais une file d’attente privée partagée uniquement par ces deux services. Tous les services de conformité enregistrent leurs données dans la même base de données sur le serveur principal de conformité. Ils extraient également de cette base de données toutes les données qu’ils doivent envoyer à l’instance de carte associée. Le serveur principal de conformité constitue un nouveau rôle serveur principal.
    
    > [!IMPORTANT]  
    > Comme dans les versions précédentes, toutes les données de conformité sont traitées en une seule fois. Toutes les données peuvent être traitées par n’importe quelle instance de carte appelée par le service de conformité exécuté sur l’un des différents ordinateurs serveur de conversations permanentesLync Server 2013. Sur le serveur de conversations permanentes, chacune des instances de carte peut traiter les données.    
    > [!NOTE]  
    > Pour plus d’informations sur la file d’attente Microsoft Message Queuing, reportez-vous à <a href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Installation des systèmes d’exploitaition et des logiciels prérequis sur les serveurs pour Lync Server 2013</a> dans la documentation de déploiement.

Lync Server 2013 apporte des améliorations en termes de haute disponibilité et de récupération d’urgence :

  - Améliorations de la haute disponibilité : la mise en miroir SQL Server est utilisée pour garantir une haute disponibilité de la base de données de contenu du serveur de conversations permanentes et de la base de données de conformité de conversation permanente au sein d’un centre de données (sur site).

  - Améliorations de la récupération d’urgence : le serveur de conversations permanentes prend en charge une architecture de pool étendue qui permet d’étendre un pool de serveurs de conversations permanentes entre deux sites (autrement dit, la topologie contient un seul pool logique, où les serveurs sont physiquement installés dans deux sites distincts). La copie des journaux de transaction SQL Server est utilisée pour la récupération d’urgence entre les sites.

Pour plus d’informations sur la haute disponibilité et la récupération d’urgence, reportez-vous à [Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.

## Principales modifications apportées à l’administration et la gestion du serveur de conversations permanentes

Dans Lync Server 2013, l’administration et la gestion du serveur de conversations permanentes sont facilitées grâce aux améliorations suivantes :

  - Administration et gestion unifiées. Lync Server 2013 fournit plusieurs outils, que les administrateurs Lync connaissent déjà, qui simplifient l’administration et la gestion du serveur de conversations permanentes. Le serveur de conversations permanentes comporte une nouvelle interface utilisateur d’administration, intégrée au Panneau de configuration Lync Server, qui résout les problèmes de performances rencontrés avec l’interface utilisateur des versions précédentes du serveur Group Chat. De plus, le serveur de conversations permanentes contient un ensemble d’applets de commande Windows PowerShell très utiles pour administrer et gérer les catégories du serveur de conversations permanentes, les salles du serveur de conversations permanentes (y compris pour supprimer des salles et le contenu obsolète) ainsi que les compléments.

  - Modèle d’administration simplifié. Dans Lync Server 2013, le modèle du serveur de conversations permanentes a été modifié et simplifié pour répondre aux demandes des utilisateurs suivantes :
    
      - Supprimer les hiérarchies imbriquées complexes d’étendues et de catégories.
    
      - Permettre la création de listes d’exclusion et de listes autorisées (étendues) pour les clients actuels de MindAlign qui planifient un transfert vers le serveur de conversations permanentes.

## Quelles sont les différences avec les rôles utilisateur des versions précédentes du serveur Group Chat ?

Lync Server 2010, conversation de groupe comportait un rôle Administrateur d’utilisateurs, un rôle Administrateur de salles de conversation et un rôle Administrateur Lync Server utilisés pour gérer les compléments. Le serveur de conversations permanentes fournit uniquement un rôle Administrateur de conversation permanente (similaire aux autres rôles Lync Server de contrôle d’accès en fonction du rôle). Tous les membres de ce rôle sont autorisés à gérer des salles de conversation, des compléments et des catégories (et donc à bénéficier d’un accès utilisateur à celles-ci), ainsi que les paramètres de configuration du pool de serveurs de conversations permanentes.

## Quelles sont les différences avec les catégories de salle de conversation des versions précédentes du serveur Group Chat ?

Les catégories de salle de conversation ne peuvent plus être imbriquées les unes aux autres, et la catégorie racine n’est plus modifiable. Les catégories AllowedMembers/DeniedMembers englobent la notion d’étendue qui était utilisée dans les versions héritées du serveur Group Chat (lesquelles toutefois ne prenaient pas en charge la création de liste d’exclusion). Les étendues ne peuvent plus être remplacées, car il n’y a plus de catégories imbriquées. Dans Lync Server 2013, un Administrateur de conversation permanente a la possibilité de créer et gérer des catégories de salle de conversation et, dans ce cadre, un Administrateur de conversation permanente peut configurer des principaux (utilisateurs/conteneurs/groupes Active Directory) autorisés à être ajoutés en tant que membres ou créateurs des salles de conversation appartenant à une catégorie spécifique. Un Administrateur de conversation permanente peut également ajouter des membres refusés (DeniedMembers) à une catégorie, qui font alors l’objet d’exclusions explicites à la liste autorisée. La catégorie DeniedMembers est prioritaire sur la catégorie AllowedMembers.

## Quelles sont les différences avec les propriétés de salle de conversation des versions précédentes du serveur Group Chat ?

Le serveur de conversations permanentesLync Server 2013 introduit le nouveau concept de salle de conversation ouverte. Tous les membres autorisés peuvent rejoindre la salle de conversation, sans appartenance exclusive.

Les propriétés de salle de conversation suivantes, qui figuraient dans les versions précédentes du serveur de conversations permanentes, ont été supprimées :

  - Rubrique : une salle ne comporte plus qu’une description.

  - Créer une liste de membres : sur le serveur de conversations permanentes, les salles de conversation ne contiennent initialement aucun membre (et ne peuvent pas contenir plus de membres que dans la liste des membres autorisés).

  - Téléchargement de fichiers : paramètre qui était défini au niveau de chaque salle de conversation pour activer ou désactiver le téléchargement des fichiers. Ce paramètre ne se définit plus maintenant qu’au niveau de la catégorie et s’applique à toutes les salles appartenant à cette catégorie.

  - Historique des conversations : paramètre qui était défini au niveau de chaque salle de conversation pour activer ou désactiver l’historique des conversations. Ce paramètre ne se définit plus maintenant qu’au niveau de la catégorie et s’applique à toutes les salles appartenant à cette catégorie.

  - Invitations : une salle hérite toujours du paramètre Invitations défini pour la catégorie, mais ce paramètre peut aussi être désactivé pour la salle. Le paramètre Invitations ne peut pas être activé pour une salle s’il a été désactivé pour la catégorie à laquelle la salle appartient.

## Quelles sont les différences avec les stratégies des versions précédentes du serveur Group Chat ?

Le serveur de conversations permanentes comporte une nouvelle stratégie Lync activée avec la fonctionnalité de conversation permanente par le biais des paramètres de niveau global, site, pool ou utilisateur. Sur le client Lync 2013, l’environnement de conversation permanente n’est disponible que pour les utilisateurs pour qui la stratégie de conversation permanente a été activée (soit directement, soit via les paramètres de niveau global, site ou pool).

Dans les versions précédentes du serveur Group Chat, aucune stratégie n’était intégrée aux stratégies Lync Server. Vous deviez utiliser la fonction utilisateur **Activer le téléchargement de fichiers** pour définir l’utilisateur, au niveau de l’utilisateur ou de la catégorie/salle, en tant qu’Administrateur d’utilisateurs ou Administrateur de salles de conversation, ou pour lui accorder ou non l’autorisation de télécharger des fichiers. La fonction **Téléchargement de fichiers** du serveur de conversations permanentes ne peut être utilisée qu’au niveau de la catégorie.

## Journalisation

La journalisation pour le serveur de conversations permanentes et System Center Operations Manager est intégrée à la journalisation du suivi de Lync Server 2013.

## Voir aussi

#### Autres ressources

[Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)

