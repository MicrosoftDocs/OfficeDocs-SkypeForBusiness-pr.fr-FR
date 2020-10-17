---
title: 'Lync Server 2013 : nouvelles fonctionnalités de serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd9288fea9105be27428ac94d992de6e147f4900
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534181"
---
# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Nouvelles fonctionnalités de serveur de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Lync Server 2013, serveur de conversation permanente vous permet de participer à des conversations en plusieurs rubriques, qui sont conservées au fil du temps. Le serveur de conversation permanente peut aider votre organisation à effectuer les opérations suivantes :

  - améliorer la communication entre les équipes géographiquement dispersées et multifonctionnelles ;

  - élargir la prise en compte des informations et la participation ;

  - améliorer la communication dans l’ensemble de votre organisation ;

  - réduire la surcharge d’informations ;

  - améliorer la prise en compte des informations ;

  - accroître la dissémination des connaissances et des informations importantes.

Lync Server 2013, le serveur de conversation permanente n’est pas disponible dans Microsoft 365 ou Office 365. Pour le moment, il n’est disponible que pour les clients Lync 2013 locaux.

Dans Lync 2013, la fonctionnalité de conversation permanente est intégrée au client Lync 2013. Par conséquent, les utilisateurs ont accès à la messagerie instantanée/présence, audio/vidéo, à la Conférence et à la conversation permanente dans le client Lync 2013. Pour plus d’informations sur le client Lync 2013, voir <https://go.microsoft.com/fwlink/p/?linkid=270877> .

Cette rubrique décrit les modifications apportées aux fonctionnalités entre la nouvelle version de Lync Server 2013, le serveur de conversation permanente et la version précédente (Microsoft Lync Server 2010, Group chat), notamment :

  - Fournir une expérience administrative dans le panneau de configuration Lync Server et éliminer l’outil d’administration de conversation de groupe

  - Intégrer les paramètres de configuration du serveur de conversation permanente dans le générateur de topologie en supprimant l’outil de configuration de conversation de groupe

  - Faciliter la migration et la mise à niveau à partir de versions précédentes du serveur de conversation permanente

  - Fournir des solutions de haute disponibilité et de récupération d’urgence

Pour plus d’informations sur la dernière version du serveur de conversation permanente, consultez les rubriques suivantes :

  - Aide de la conversation permanente, à partir <https://go.microsoft.com/fwlink/p/?linkid=270945> de laquelle fournit une liste détaillée des fonctionnalités de conversation permanente, de leur fonctionnement et de leur utilisation lors de l’exécution du serveur de conversation permanente.

  - [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) dans la documentation de déploiement, [migration de Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat to Lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) dans la documentation de migration et [Managing Lync Server 2013, persistent Server](managing-lync-server-2013-persistent-chat-server.md) dans la documentation des opérations, qui fournissent toutes des instructions sur la configuration du serveur de conversation permanente.

  - Le fichier de Documentation.msi du serveur de conversation permanente (fichier Windows Installer) permet aux utilisateurs d’accéder à une documentation hors connexion complète sur le serveur de conversation permanente.

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Modifications de la topologie de clés pour le serveur de conversation permanente

Voici les principales modifications apportées au serveur de conversation permanente :

Le serveur de conversation permanente est maintenant un rôle de serveur. Dans Microsoft Lync Server 2010, le serveur de conversation de groupe était une application tierce de confiance pour Microsoft Lync Server 2010. La conversation permanente peut être ajoutée à votre topologie Lync Server 2013 à l’aide du générateur de topologie. Dans Lync Server 2013, la fonctionnalité de serveur de conversation permanente est implémentée à l’aide de trois nouveaux rôles serveur :

  - **PersistentChatService :** Il s’agit du rôle frontal pour la conversation permanente. Dans les déploiements Standard Edition, le rôle de service serveur de conversation permanente est colocalisé sur le serveur Standard Edition déployé par le programme d’amorçage, comme n’importe quel autre rôle Lync Server. Dans les déploiements Enterprise Edition, le rôle service de conversation permanente est déployé sur des ordinateurs autonomes par le programme d’amorçage, comme n’importe quel autre rôle Lync Server.

  - **PersistentChatStore :** Serveur principal qui correspond à la base de données de contenu de conversation permanente, dans laquelle tout le contenu de conversation est stocké.

  - **PersistentChatComplianceStore :** Rôle de serveur principal qui correspond à la base de données de conformité de conversation permanente, dans laquelle tous les événements de conformité sont stockés.

Ces rôles de serveur de conversation permanente sont facultatifs et installés uniquement par les clients qui souhaitent bénéficier d’une fonctionnalité de serveur de conversation permanente complète. Le rôle **PersistentChatComplianceStore** est uniquement nécessaire si vous choisissez de déployer la conformité de la conversation permanente.

Le rôle **PersistentChatService** exécute deux services :

  - Service de conversation permanente

  - Service de conformité de conversation permanente

L’exécution de ces services sur chaque serveur de conversation permanente offre une haute disponibilité pour ces services dans un pool de serveurs de conversation permanente multiserveur.

De plus, pour prendre en charge le téléchargement de fichiers et le téléchargement dans les salles de conversation permanente, le serveur de conversation permanente inclut un service Web. Auparavant, ce service était colocalisé sur le serveur de conversation permanente, le serveur frontal et les services IIS (Internet Information Services) requis à installer. Dans le serveur de conversation permanente Lync Server 2013, le service de téléchargement/téléchargement de fichiers est colocalisé avec le serveur frontal Lync Server 2013. En tant qu’effet secondaire, les services Internet (IIS) ne sont plus requis pour le serveur de conversation permanente. Le service Web de téléchargement/téléchargement de fichier est identifié comme **PersistentChat** dans le gestionnaire des services Internet (IIS).

<div>


> [!IMPORTANT]  
> Le rôle <STRONG>PersistentChatService</STRONG> peut s’exécuter sur le même serveur qu’un serveur frontal Lync Server 2013 &nbsp; uniquement si ce dernier est un serveur frontal Standard Edition &nbsp; . Le rôle <STRONG>PersistentChatService</STRONG> ne peut pas s’exécuter indépendamment d’un &nbsp; serveur frontal Lync Server 2013. Elle peut être installée uniquement dans le cadre d’un déploiement de Lync Server 2013.



</div>

Dans le serveur de conversation permanente, le service de recherche a été supprimé. Dans Lync Server 2010, Group chat, le service de recherche s’est exécuté sur chaque serveur frontal de serveur de conversation de groupe et a effectué le routage vers l’un des serveurs de canal. Lync Server 2013 repose sur le routage à l’aide des objets contact, où chaque pool de serveur de conversation permanente est représenté par un objet contact qui est utilisé par les serveurs frontaux Lync Server pour identifier et acheminer les demandes vers un pool de serveurs de conversation permanente approprié, et vers l’un des ordinateurs exécutant le serveur de conversation permanente dans le pool.

Dans Lync Server 2013, il existe des modifications de service de conformité :

  - Dans Lync Server 2010, le service de conformité s’est exécuté en mode autonome (non colocalisé) et uniquement sur un seul serveur. Le service de conformité s’exécute désormais sur tous les serveurs frontaux de serveur de conversation permanente, ainsi que le service de conversation permanente, et fournit ainsi une haute disponibilité dans un pool de serveurs de conversation permanente multiserveur. Un adaptateur de conformité unique peut être configuré pour extraire les données de la base de données de conformité et de l’un des autres systèmes (fichier XML, Archives hébergées par Exchange, etc.). Le serveur de conversation permanente inclut un adaptateur XML.

  - La file d’attente Message Queuing (également appelée MSMQ) qui est partagée par le service de conversation permanente et le service de conformité sur chaque serveur frontal de serveur de conversation permanente est désormais une file d’attente privée partagée uniquement par les deux services. Tous les services de conformité écrivent dans la même base de données principale de conformité. Ils sont également lus à partir de cette base de données, afin d’envoyer les données à leur instance de l’adaptateur. Le serveur principal de conformité est représenté sous la forme d’un nouveau rôle de serveur principal.
    
    <div>
    

    > [!IMPORTANT]  
    > Comme dans les versions précédentes, toutes les données de conformité ne sont traitées qu’une seule fois. Les données peuvent être traitées par n’importe quelle instance d’adaptateur appelée par le service de conformité exécuté sur les différents serveurs Lync Server 2013, persistent chat. Dans le cas d’un serveur de conversation permanente, l’une des instances de carte peut traiter les données.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur l’installation de Message Queuing, voir <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">installer des systèmes d’exploitation et des logiciels prérequis sur les serveurs pour Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

Dans Lync Server 2013, il existe des améliorations en matière de haute disponibilité et de récupération d’urgence :

  - Améliorations de la haute disponibilité : la mise en miroir SQL Server est utilisée pour fournir une haute disponibilité pour la base de données de contenu du serveur de conversation permanente et la base de données de conformité de conversation permanente dans un centre de données (sur site).

  - Améliorations de la récupération d’urgence : le serveur de conversation permanente prend en charge une architecture de pool étirée qui permet à un seul pool de serveurs de conversation permanente d’être étiré entre deux sites (c’est-à-dire un pool logique unique dans la topologie, avec des serveurs du pool physiquement situés sur deux sites). La copie des journaux de transaction SQL Server est utilisée pour la récupération d’urgence intersite.

Pour plus d’informations sur la haute disponibilité et la récupération d’urgence, reportez-vous à la rubrique [configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Modifications de gestion et d’administration de clés pour le serveur de conversation permanente

Lync Server 2013 a facilité l’administration et la gestion du serveur de conversation permanente en fournissant les éléments suivants :

  - Administration et gestion unifiées. Lync Server 2013 facilite la gestion et l’administration du serveur de conversation permanente à l’aide d’outils déjà familiers aux administrateurs Lync. Le serveur de conversation permanente inclut une expérience d’interface utilisateur d’administration intégrée au panneau de configuration Lync Server, qui permet de résoudre les problèmes de performances liés aux versions précédentes de l’interface utilisateur du serveur de conversation de groupe. De même, le serveur de conversation permanente inclut une collection d’applets de commande Windows PowerShell pour administrer et gérer les catégories de serveur de conversation permanente, les salles de serveur de conversation permanente (y compris la suppression de salles et le contenu obsolète) et les compléments.

  - Modèle d’administration simplifié. Lync Server 2013 a modifié et simplifié le modèle de serveur de conversation permanente en abordant les principaux besoins des clients :
    
      - Supprimez les hiérarchies imbriquées complexes des étendues et des catégories.
    
      - Prise en charge pour définir des listes de refus, ainsi que des listes autorisées (étendues) pour les clients MindAlign actuels qui envisagent de migrer vers le serveur de conversation permanente.

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>Quelles sont les différences en ce qui concerne les rôles d’utilisateur des versions précédentes du serveur de conversation de groupe ?

Lync Server 2010, Group chat disposait d’un rôle d’administrateur d’utilisateurs, d’un rôle d’administrateur de salle de conversation et d’un rôle d’administrateur Lync Server pouvant gérer les compléments. Le serveur de conversation permanente fournit simplement un rôle d’administrateur de conversation permanente (semblable aux autres rôles de contrôle d’accès basé sur un rôle de Lync Server). Toute personne qui est membre de ce rôle RBAC peut gérer les salles de conversation, les compléments et les catégories (et ainsi obtenir l’accès des utilisateurs pour ces catégories), ainsi que la configuration du pool de serveurs de conversation permanente.

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>Différences par rapport aux catégories de salles de conversation des versions précédentes du serveur de conversation de groupe

Les catégories de salle de conversation ne peuvent plus être imbriquées et la catégorie racine ne peut plus être modifiée. AllowedMembers/membres refusés comprend ce qu’est une étendue utilisée dans les versions des serveurs de conversation de groupe héritées (sauf qu’elle n’a pas pris en charge la spécification d’une liste refusée). Les étendues ne peuvent plus être remplacées, car il n’y a pas de catégories imbriquées. Un administrateur de conversation permanente dans Lync Server 2013 peut créer et gérer des catégories de salles de conversation. Dans le cadre de la création et de la gestion des catégories de salles de conversation, un administrateur de conversation permanente peut configurer des principaux (groupes Active Directory/conteneurs/utilisateurs) qui ont accès à des membres/créateurs de salles de conversation d’une catégorie particulière. Un administrateur de conversation permanente peut également ajouter membres refusés à une catégorie, et ces exclusions deviennent des exclusions explicites de la liste autorisée. Membres refusés remplacer ce qui se trouve dans AllowedMembers.

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>Quelles sont les différences entre les propriétés de salle de conversation des versions précédentes du serveur de conversation de groupe ?

Un nouveau concept de salles de conversation ouvertes existe dans Lync Server 2013, serveur de conversation permanente. Tous les membres autorisés peuvent rejoindre la salle de conversation, sans membre exclusif.

Les propriétés de salle de conversation suivantes qui ont été incluses dans les versions précédentes du serveur de conversation permanente ont été éliminées :

  - Rubrique : une salle dispose désormais uniquement d’une description.

  - Créer une liste de membres : dans le serveur de conversation permanente, toutes les salles de conversation commencent par une appartenance vide (et peuvent augmenter jusqu’à une appartenance égal aux membres autorisés).

  - Chargement de fichiers : permet de définir un paramètre par salle de conversation afin de contrôler si les téléchargements de fichiers/téléchargements ont été autorisés. Il définit à présent uniquement le niveau de catégorie et s’applique à toutes les salles de cette catégorie.

  - Historique de la conversation : permet de définir un paramètre par salle de conversation afin de contrôler si l’historique de conversation a été activé, mais qui n’est défini qu’au niveau de la catégorie et s’applique à toutes les salles de cette catégorie.

  - Invitations : une salle hérite toujours du paramètre des invitations pour la catégorie ; ou elle peut être désactivée sur la salle. Une salle ne peut pas activer les invitations si la catégorie a été définie précédemment sur invitations.

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>Quelles sont les différences par rapport aux stratégies des versions précédentes du serveur de conversation de groupe ?

Le serveur de conversation permanente a une nouvelle stratégie Lync activée avec la conversation permanente, par utilisateur/pool/site/paramètres globaux. Dans le client Lync 2013, l’environnement de conversation permanente est disponible uniquement pour les utilisateurs qui sont activés par la stratégie pour la conversation permanente (directement ou par le biais du paramètre pool/site/global).

Les versions précédentes du serveur de conversation de groupe n’ont pas de stratégies intégrées dans les stratégies Lync Server. Pour chaque utilisateur et par catégorie/salle, à l’aide de la fonctionnalité de **téléchargement de fichiers** par utilisateur, vous pouvez faire de l’utilisateur un administrateur d’utilisateur, un administrateur de salle de conversation ou configurer la capacité de téléchargement des fichiers par l’utilisateur. La fonctionnalité de **téléchargement de fichiers** du serveur de conversation permanente est une seule par catégorie.

</div>

<div>

## <a name="logging"></a>Logging

La journalisation du serveur de conversation permanente et de System Center Operations Manager est intégrée à la journalisation du suivi de Lync Server 2013.

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
