---
title: 'Lync Server 2013 : Ajout d’un serveur de conversation permanente à la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Ajout d’un serveur de conversation permanente à la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-06_

Pour pouvoir configurer votre déploiement pour la prise en charge de la messagerie instantanée, vous devez disposer de Lync Server 2013 et de la prise en charge du serveur de chat permanent dans votre topologie. Les informations fournies dans cette rubrique décrivent comment utiliser le générateur de topologie pour ajouter le support technique de chat permanent à votre topologie existante.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>Pour ajouter le serveur de chat permanent à une topologie

Suivez les étapes ci-dessous pour installer une seule liste de serveurs de chat permanent sans configuration de reprise après sinistre. Pour configurer un pool de serveurs de chat permanent étiré en vue d’une haute disponibilité et d’une reprise après sinistre, reportez-vous à la rubrique [configuration du serveur de chat permanent pour une haute disponibilité et une reprise après sinistre dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.

Pour déployer plusieurs pools de serveurs de chat permanent, répétez la même procédure pour chaque liste.

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie qui est requise pour l’installation d’un serveur Lync Server 2013, vous devez utiliser un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et de <STRONG>RTCUniversalS erverAdmins</STRONG> et qui dispose des autorisations de contrôle total (en lecture, écriture et modification) sur le magasin de fichiers que vous allez utiliser pour le stockage des fichiers du serveur de messagerie instantanée (c’est-à-dire que le générateur de topologie peut configurer les DACL requis) ou un compte droits équivalents.

    
    </div>

2.  Démarrer le générateur de topologie.

3.  Dans l’arborescence de la console, accédez au nœud Pools de **conversations permanentes** et développez-le pour sélectionner un pool de serveurs de chat permanent, ou cliquez avec le bouton droit sur le nœud et sélectionnez **nouvelle liste de conversations permanentes**. You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.
    
    Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur**. Choisissez le premier si vous envisagez de disposer de plusieurs serveurs front-end serveur de chat permanent dans votre pool de serveurs de chat permanent. Effectuez ce choix maintenant, ou ultérieurement, car une fois que vous aurez créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs. Si vous choisissez un pool d’ordinateurs multiples, entrez le nom de chaque serveur frontal de chat permanent qui comprend le pool.
    
    <div>
    

    > [!IMPORTANT]  
    > Si le rôle serveur Chat permanent est installé sur un serveur Lync Server 2013&nbsp;Standard Edition Server, le FQDN doit correspondre au nom de domaine complet (FQDN) du serveur Standard Edition Server.

    
    </div>

4.  Définissez un **nom complet** simple pour le pool de serveurs de chat permanent. Le nom d’affichage peut être utilisé par les clients personnalisés, en particulier lorsqu’il existe plusieurs pools de serveurs de chat permanent pour différencier des salles.

5.  Définissez le port utilisé par le serveur de chat permanent pour communiquer avec les serveurs front-end de Lync Server. Le port par défaut est 5041.

6.  Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité**. Le cas échéant, le service de conformité serveur Chat permanent est installé sur le même ordinateur que le serveur frontal de chat permanent du serveur. Vous êtes invité à sélectionner un serveur principal SQL Server pour la compatibilité avec le serveur Chat permanent plus tard.

7.  Attribuez une affinité de site pour le pool de serveurs de chat permanent. Activez la case à cocher **utiliser ce pool \<comme\> option par défaut pour le site SiteName** ou **Utilisez ce pool par défaut pour tous les sites** pour désigner ce pool de serveurs de chat permanent comme pool par défaut pour le site actuel ou pour tous les sites. Lorsque le client 2013 Lync est utilisé pour créer et gérer des salles, le pool par défaut associé au site de l’utilisateur est utilisé par l’interface de création et de gestion de la salle, afin de pouvoir diriger les opérations de création et de gestion de salle vers ce pool. Ce comportement s’applique uniquement lorsque vous avez déployé plusieurs pools de serveurs de chat permanent et que vous voulez utiliser les fonctionnalités de création et de gestion de la salle du serveur de chat permanent.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez personnaliser les fonctionnalités de création et de gestion d’une salle à l’aide du kit de développement logiciel (SDK) serveur Chat permanent.<BR>Pour plus d’informations sur la configuration des bases de données de sauvegarde SQL Server pour la récupération d’urgence, reportez-vous à la rubrique <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configuration d’un serveur de chat permanent pour une disponibilité élevée et une reprise après sinistre dans Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

8.  Définissez le **SQL Store pour le serveur de chat permanent (emplacement de stockage du contenu d’une salle de conversation)** en effectuant l’une des opérations suivantes:
    
      - Pour utiliser une base de données SQL Server existante, dans la liste déroulante, cliquez sur le nom de la base de données SQL Server que vous souhaitez utiliser.
    
      - Pour spécifier une nouvelle base de données SQL Server, cliquez sur **nouveau**, puis dans **définir un nouveau SQL Store**, procédez comme suit:
    
    <!-- end list -->
    
      - Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous voulez créer la nouvelle base de données SQL Server.
    
      - Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée**, et spécifiez l’instance que vous voulez utiliser.

9.  Définissez la base de données de conformité SQL Server si vous avez activé la conformité.
    
    <div>
    

    > [!IMPORTANT]  
    > Pour plus d’informations sur la configuration des miroirs SQL Server en vue de la disponibilité de la base de données serveur Chat permanent et de la base de données de conformité serveur Chat <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md"> Serveur 2013</A> dans la documentation de déploiement.

    
    </div>

10. Définissez le magasin de fichiers. Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation). Dans le cas d’une topologie de serveur de chat permanent multiserveur, il doit s’agir d’un chemin UNC (Universal Naming Convention); dans le cas d’une topologie de serveur de chat permanent d’un serveur unique, il peut s’agir d’un chemin d’accès de fichier local.
    
    Pour utiliser un magasin de fichiers existant, procédez ainsi :
    
      - Dans **nom de domaine complet du serveur de fichiers**, spécifiez le nom de domaine complet (FQDN) du magasin de fichiers sur lequel vous souhaitez créer le nouveau magasin de fichiers.
    
      - Dans **Partage de fichiers**, indiquez le magasin de fichiers à utiliser.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez définir le magasin de fichiers dans le générateur de topologie avant de créer le magasin de fichiers, mais vous devez créer le magasin de fichiers à l’emplacement défini que vous définissez avant de publier la topologie.

    
    </div>

11. Sélectionnez le pool de serveurs frontal à utiliser comme tronçon suivant pour ce pool de serveurs de chat permanent. Il s’agit du pool de serveurs frontal qui sera en mesure d’acheminer les demandes de serveur de chat permanent vers ce pool.

12. Pour enregistrer la configuration, cliquez sur **Terminer**. Le pool de serveurs de chat permanent apparaît dans le générateur de topologie accompagné de vos paramètres de réserve spécifiques.
    
    Pour maintenant publier votre topologie mise à jour sur laquelle vous avez permanent le serveur de conversation, voir [publier la topologie mise à jour dans Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) dans la documentation de déploiement.
    
    <div>
    

    > [!NOTE]  
    > Lorsque le générateur de topologie est déjà ouvert, vous pouvez passer à l’étape 3 de <A href="lync-server-2013-publish-the-updated-topology.md">la rubrique publier la topologie mise à jour dans Lync Server 2013</A> pour commencer à publier votre topologie mise à jour.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

