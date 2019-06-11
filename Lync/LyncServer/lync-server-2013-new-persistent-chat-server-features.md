---
title: 'Lync Server 2013 : Nouvelles fonctionnalités du serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6d5cd0b8197b64abfc0761dfb333f338b507ff7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Nouvelles fonctionnalités du serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-29_

Lync Server 2013, Lync Chat Server vous permet de participer à des conversations à plusieurs sujets qui persistent dans le temps. Le serveur de chat permanent peut aider votre organisation à effectuer les opérations suivantes:

  - Amélioration de la communication entre les équipes géographiquement dispersées et celles à plusieurs fonctions

  - Élargissement de la sensibilisation et de la participation aux informations

  - Améliorer la communication avec votre organisation étendue

  - Réduire la surcharge d’information

  - Amélioration de la prise en charge des informations

  - Augmenter la dispersion des connaissances et informations importantes

Lync Server 2013, serveur de chat permanent, n’est pas disponible dans Microsoft Office 365. Pour le moment, il n’est disponible que pour les clients Lync 2013 locaux.

Dans Lync 2013, la fonctionnalité de chat permanent est intégrée au client 2013 de Lync. Par conséquent, les utilisateurs ont accès à la messagerie instantanée, à la présence, à l’audio/à la vidéo, aux conférences et aux discussions permanentes dans le client 2013 Lync. Pour plus d’informations sur le client 2013 Lync, <http://go.microsoft.com/fwlink/p/?linkid=270877>reportez-vous à la rubrique.

Cette rubrique décrit les modifications apportées aux fonctionnalités entre la nouvelle version de Lync Server 2013, le serveur de chat permanent et la version précédente (Microsoft Lync Server 2010, discussion de groupe), y compris:

  - Offrir une interface d’administration dans le panneau de configuration de Lync Server et éliminer l’outil d’administration de discussion de groupe

  - Intégrez les paramètres de configuration du serveur de chat permanent au générateur de topologie en éliminant l’outil de configuration des discussions de groupe.

  - Simplification de la migration et de la mise à niveau à partir de versions précédentes du serveur de chat permanent

  - Fournir des solutions de haute disponibilité et de reprise après sinistre

Pour plus d’informations sur la dernière version de chat permanent, voir les rubriques suivantes:

  - Dans <http://go.microsoft.com/fwlink/p/?linkid=270945> cette rubrique, l’aide de la messagerie instantanée, qui fournit une liste détaillée des fonctionnalités de chat permanent, leur fonctionnement et la façon de les utiliser lorsque vous exécutez le serveur de chat permanent.

  - [Planning pour le serveur de chat permanent dans Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, [déploiement du serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) dans la documentation de déploiement, [migration à partir de Lync Server 2010, discussion de groupe ou Office Conversation de groupe Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanent](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) dans la documentation de migration et [gestion de lync Server 2013, serveur de conversation permanent](managing-lync-server-2013-persistent-chat-server.md) dans la documentation des opérations, qui fournit les instructions pour configuration du serveur de chat permanent.

  - Le fichier persistent Chat Server Documentation. msi (fichier Windows Installer) permet aux utilisateurs d’accéder à la documentation détaillée hors connexion sur le serveur de chat permanent.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Changements de topologie clés pour le serveur de chat permanent

Les modifications suivantes ont été apportées au serveur Chat permanent:

Le serveur Chat permanent est désormais un rôle serveur. Dans Microsoft Lync Server 2010, le serveur de discussion de groupe était une application de confiance tierce pour Microsoft Lync Server 2010. La conversation permanente peut être ajoutée à votre topologie Lync Server 2013 à l’aide du générateur de topologie. Dans Lync Server 2013, la fonctionnalité de serveur Chat permanent est implémentée en utilisant trois nouveaux rôles de serveur:

  - **PersistentChatService:** C’est le rôle frontal d’une conversation permanente. Dans les déploiements Standard Edition, le rôle de service de chat permanent du serveur est colocalisé sur le serveur Standard Edition déployé par le programme de démarrage, comme tout autre rôle serveur Lync. Dans les déploiements Enterprise Edition, le rôle service de chat permanent est déployé sur des ordinateurs autonomes par le programme de démarrage, comme tout autre rôle serveur Lync.

  - **PersistentChatStore:** Serveur principal qui correspond à la base de données de contenu de conversation permanente, dans laquelle se trouve tout le contenu de la discussion.

  - **PersistentChatComplianceStore:** Le rôle serveur principal qui correspond à la base de données de compatibilité des conversations permanentes, qui stocke tous les événements de conformité.

Ces rôles serveur de chat permanent sont facultatifs et installés uniquement par les clients qui ont besoin des fonctionnalités complètes du serveur de chat permanent. Le rôle **PersistentChatComplianceStore** est requis uniquement si vous choisissez de déployer la conformité à la conversation persistante.

Le rôle **PersistentChatService** exécute deux services:

  - Service Chat permanent

  - Service de Compliance chat permanent

L’exécution de ces services sur chaque serveur de chat permanent fournit une disponibilité élevée pour ces services dans un pool de serveurs de chat permanent multiserveur.

Par ailleurs, pour prendre en charge le chargement et le téléchargement de fichiers dans des salles de conversation permanentes, le serveur Chat permanent inclut un service Web. Auparavant, ce service avait colocalisé sur le serveur de chat permanent, le serveur frontal et les services Internet (IIS) requis pour être installés comme condition préalable. Dans Lync Server 2013 persistent Chat Server, le service Web de chargement/téléchargement de fichiers est colocalisé avec le serveur frontal de Lync Server 2013. Comme un effet secondaire, Internet Information Services (IIS) n’est plus indispensable pour le serveur de chat permanent. Le service Web de chargement/téléchargement de fichier est identifié comme **PersistentChat** dans le gestionnaire des services Internet (IIS).

<div>


> [!IMPORTANT]  
> Le rôle <STRONG>PersistentChatService</STRONG> peut s’exécuter sur le même serveur qu’un serveur frontal&nbsp;Lync Server 2013 uniquement si ce serveur frontal est un serveur frontal standard&nbsp;Edition. Le rôle <STRONG>PersistentChatService</STRONG> ne peut pas s’exécuter indépendamment d’un&nbsp;serveur frontal Lync Server 2013. Elle peut être installée uniquement dans le cadre d’un déploiement de Lync Server 2013.



</div>

Dans serveur Chat permanent, le service de recherche a été supprimé. Dans Lync Server 2010, les discussions de groupe, le service de recherche s’exécutait sur chaque serveur frontal du serveur de messagerie de groupe et effectuait le routage vers l’un des serveurs de canaux. Lync Server 2013 repose sur le routage à l’aide d’objets de contact dans lesquels chaque pool de serveurs de chat permanent est représenté par un objet de contact utilisé par les serveurs frontaux de Lync Server pour identifier et acheminer les demandes vers un pool de serveurs de chat permanent approprié l’un des ordinateurs exécutant une conversation permanente sur le pool.

Dans Lync Server 2013, il existe des modifications du service de conformité:

  - Dans Lync Server 2010, le service de conformité s’est exécuté en mode autonome (non localisé), et sur un seul serveur. Le service de conformité est désormais exécuté sur tous les serveurs front-end serveur de chat permanent, en plus du service de chat permanent et fournit ainsi une haute disponibilité dans un pool de serveurs de chat permanent multiserveur. Un seul adaptateur de conformité peut être configuré pour extraire les données de la base de données de conformité et dans l’un des autres systèmes (fichier XML, Archives hébergées sur Exchange, etc.). Le serveur Chat permanent inclut un adaptateur XML.

  - La file d’attente Message Queuing (également appelée MSMQ) partagée par le service Chat permanent et le service de conformité sur chaque serveur frontal de Chat Server permanent est désormais une file d’attente privée uniquement partagée par les deux services. Tous les services de conformité écrivent dans la même base de données de fin de conformité. Ils sont également lus à partir de cette base de données afin d’envoyer les données à leur instance de la carte. Le serveur principal de conformité est représenté en tant que nouveau rôle serveur principal.
    
    <div>
    

    > [!IMPORTANT]  
    > Comme dans les versions précédentes, toutes les données de conformité sont traitées une seule fois. Les données sont traitées par l’une des instances d’adaptateur invoquées par le service de conformité exécuté sur les divers serveurs Lync Server 2013 et les ordinateurs serveur de chat permanent. Dans serveur Chat permanent, l’une des instances de carte peut traiter les données.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur l’installation de Message Queuing, voir <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">installation de systèmes d’exploitation et logiciels prérequis sur des serveurs pour Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

Dans Lync Server 2013, il existe de nouvelles améliorations en matière de haute disponibilité et de récupération d’urgence:

  - Améliorations de la haute disponibilité: la mise en miroir SQL Server est utilisée pour fournir une haute disponibilité pour la base de données de contenu du serveur de chat permanent et la base de données de conformité des conversations permanentes au sein d’un centre de données (sur site).

  - Amélioration de la reprise après sinistre: le serveur Chat permanent prend en charge une architecture de réserve étirée qui permet d’étendre un pool unique de serveurs de chat permanent sur deux sites (c’est-à-dire un pool logique unique dans la topologie, avec les serveurs du pool physiquement situés sur deux sites). L’expédition du journal SQL Server est utilisée pour une reprise après sinistre entre sites.

Pour plus d’informations sur la haute disponibilité et la reprise après sinistre, voir [configurer le serveur de chat permanent pour une haute disponibilité et une reprise après sinistre dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Modifications de l’administration et de la gestion des clés pour le serveur de chat permanent

Lync Server 2013 a facilité l’administration et la gestion du serveur de chat permanent grâce aux éléments suivants:

  - Administration et gestion unifiées. Lync Server 2013 simplifie la gestion et l’administration du serveur de chat permanent en utilisant des outils déjà familiers pour les administrateurs Lync. Le serveur Chat permanent inclut une interface utilisateur d’administration intégrée au panneau de configuration de Lync Server, qui permet de résoudre les problèmes de performances liés aux versions précédentes de l’interface utilisateur du serveur de conversation de groupe. Par ailleurs, le serveur Chat permanent inclut une collection d’applets de dialogue Windows PowerShell permettant d’administrer et de gérer les catégories serveur de chat permanent, des salles de conversation permanentes (y compris la suppression de salles et la suppression du contenu obsolète) et des compléments.

  - Modèle d’administration simplifié. Lync Server 2013 a changé et simplifié le modèle de serveur de chat permanent en répondant à la configuration requise pour les clients suivants:
    
      - Supprimez les hiérarchies imbriquées complexes d’étendues et de catégories.
    
      - La prise en charge de la définition de listes de refus ainsi que des listes autorisées (étendues) pour les clients MindAlign actuels qui envisagent de migrer vers un serveur de chat permanent.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>Quels sont les différences en ce qui concerne les rôles d’utilisateur dans les versions précédentes du serveur de discussion de groupe?

Lync Server 2010, une discussion de groupe possédant un rôle d’administrateur d’utilisateur, un rôle d’administrateur de salle de conversation et un rôle d’administrateur de Lync Server pouvant gérer les compléments. le serveur de conversation permanent fournit simplement un rôle d’administrateur de chat permanent (similaire à celui d’une autre Lync). Rôles de contrôle d’accès basés sur le rôle serveur (RBAC). Toute personne qui fait partie de ce rôle RBAC peut gérer des salles de conversation, des compléments et des catégories (et, par conséquent, bénéficier d’un accès utilisateur pour ces catégories) et configurer le pool de serveurs de chat permanent.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>Quels sont les différences en ce qui concerne les catégories de salle de conversation des versions précédentes du serveur de discussion de groupe?

Les catégories de salle de conversation ne peuvent plus être imbriquées et la catégorie racine ne peut plus être modifiée. AllowedMembers/DeniedMembers comprend ce qu’est une étendue utilisée dans les versions serveur de chat de groupe héritées (sauf qu’elle ne prend pas en charge la spécification d’une liste refusée). Les étendues ne peuvent pas être remplacées, car il n’y a pas de catégories imbriquées. Un administrateur de chat permanent dans Lync Server 2013 peut créer et gérer des catégories de salle de conversation. Dans le cadre de la création et de la gestion des catégories de salle de conversation, un administrateur de chat permanent peut configurer des principales (groupes Active Directory/conteneurs) qui peuvent être membres/créateurs de salles de conversation d’une catégorie spécifique. Un administrateur de chat permanent peut également ajouter des DeniedMembers à une catégorie, qui deviennent des exclusions explicites de la liste autorisée. Les éléments DeniedMembers remplacent les éléments AllowedMembers.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>Quels sont les différences en ce qui concerne les propriétés d’une salle de conversation dans les versions précédentes du serveur de discussion de groupe?

Un nouveau concept de salles de conversation ouvertes existe dans Lync Server 2013, serveur de chat permanent. Tous les membres autorisés peuvent rejoindre une salle de conversation sans être abonnés exclusifs.

Les propriétés de salle de conversation suivantes qui étaient incluses dans les versions précédentes de chat permanent du serveur ont été supprimées:

  - Sujet: une salle possède désormais une description.

  - Créer une liste de membres: dans le serveur de chat permanent, toutes les salles de conversation commencent par une appartenance vide (et permettent d’optimiser l’appartenance aux membres autorisés).

  - Chargement de fichier: permet de définir un paramètre par salle de conversation pour contrôler l’autorisation de chargement/téléchargement de fichiers. Il s’agit désormais de définir uniquement le niveau de catégorie et s’applique à toutes les salles de cette catégorie.

  - Historique des conversations: il s’agit d’un paramètre par salle de conversation pour contrôler si l’historique des discussions a été activé, mais qu’il n’est pas défini pour le niveau catégorie et qu’il s’applique également à toutes les salles de cette catégorie.

  - Invitations: une salle hérite toujours du paramètre d’invitations pour la catégorie; Il peut également être désactivé dans la salle. Une salle ne peut pas activer les invitations si la catégorie a été configurée pour invites.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>Quels sont les différences en ce qui concerne les stratégies des versions précédentes du serveur de discussion de groupe?

Le serveur Chat permanent possède une nouvelle stratégie Lync activée avec les discussions permanentes, par utilisateur/pool/site/paramètres globaux. Dans le client Lync 2013, l’environnement chat permanent est disponible uniquement pour les utilisateurs qui sont activés par la stratégie de conversation permanente (directement ou par le biais du pool/site/paramètre global).

Les versions précédentes de Server Chat Server n’avaient pas de stratégies intégrées aux stratégies du serveur Lync. Par utilisateur et par catégorie/par salle, en utilisant la fonctionnalité **peut télécharger des fichiers** par utilisateur, vous pouvez faire de l’utilisateur un administrateur d’utilisateur, un administrateur de salle de conversation ou configurer la capacité de télécharger des fichiers par l’utilisateur. La fonction de **chargement de fichiers** du serveur de chat permanent n’est qu’une par catégorie.

</div>

<div>

## <a name="logging"></a>Journalisation

La journalisation des conversations permanentes Server et System Center Operations Manager est intégrée à la journalisation de suivi de Lync Server 2013.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

