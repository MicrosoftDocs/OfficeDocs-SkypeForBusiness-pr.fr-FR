---
title: 'Lync Server 2013 : Définition de la configuration requise pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75ed62d577cc6b382509f83e53088973e16b6827
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Définition de la configuration requise pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-09_

Si votre organisation doit suivre des règles de conformité, vous pouvez déployer l’archivage pour activer la prise en charge de l’archivage pour les conférences de messagerie instantanée et de conférence de Lync Server 2013. Pour plus d’informations sur le type de contenu qui peut être archivé, voir [vue d’ensemble de l’archivage dans Lync Server 2013](lync-server-2013-overview-of-archiving.md) dans la documentation de planification.

Pour implémenter l’archivage, vous devez d’abord décider comment répondre aux besoins de votre organisation en matière d’archivage. Pour cela, vous devez déterminer les éléments suivants:

  - **Moment du déploiement de l’archivage**. Vous pouvez déployer l’archivage dans le cadre de votre déploiement initial de Lync Server 2013 ou vous pouvez l’ajouter à un déploiement existant. Vous pouvez déployer l’archivage à l’aide du générateur de topologie pour l’ajouter à votre topologie, puis en publiant la topologie.

  - **Archivage des communications internes ou externes**. Vous pouvez activer l’archivage pour les communications internes (communications entre les utilisateurs internes) et/ou les communications externes (communications incluant au moins un utilisateur externe à votre réseau interne). Vous pouvez spécifier ces options pour l’ensemble de votre organisation, ou pour des sites et pools spécifiques. Par défaut, aucune des ces options n’est activée.
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez l’intégration de Microsoft Exchange pour stocker les données archivées, vos paramètres Exchange déterminent si les communications Lync sont archivées. Si votre déploiement inclut plusieurs forêts, vous devez synchroniser les paramètres entre Lync Server et Exchange. Le contrôle de l’archivage pour les communications internes ou externes n’est disponible que pour la stratégie Lync. Dans le cas d’un archivage intégré à Exchange, les deux peuvent être archivés ou ne sont pas archivés.

    
    </div>

  - **Avantages de l’archivage** Vous pouvez activer et désactiver l’archivage pour votre déploiement complet au niveau global, et vous pouvez activer et désactiver l’archivage pour des sites et des utilisateurs spécifiques. À chacun de ces niveaux, vous spécifiez si vous voulez activer l’archivage des sessions de messagerie instantanée (pair à pair), des conférences (réunions, des sessions multiparties), ou les deux. Par défaut, l’archivage est désactivé.

  - **La façon dont l’archivage est essentiel pour les utilisateurs de votre organisation**. Si l’archivage est essentiel pour votre organisation, vous pouvez spécifier que Lync Server 2013 s’exécute en mode critique, ce qui bloque les sessions de messagerie instantanée et de conférence en cas d’échec de l’archivage. Par exemple :
    
      - Si le service d’archivage ne parvient pas à envoyer de message à la file d’attente de base de données ou à insérer un message dans la base de données, les fonctionnalités de messagerie instantanée et de conférence sont bloquées dans le déploiement jusqu’à ce que la prise en charge de l’archivage soit restaurée.
    
      - Si un utilisateur de conférence télécharge un fichier, mais que le fichier ne peut pas être copié vers le magasin de fichiers d’archivage, la fonctionnalité de conférence est bloquée dans le déploiement tant que le problème n’est pas résolu, mais la fonctionnalité de messagerie instantanée n’est pas bloquée.
    
    Vous pouvez configurer cette option au niveau global, au niveau du site et au niveau du pool. Par défaut, le mode Critical n’est pas activé.

  - **Si vous souhaitez utiliser l’intégration de Microsoft Exchange**. Cette option intègre le stockage d’archivage auprès de votre espace de stockage 2013 Exchange, de sorte que vos données archivées Lync Server et les données archivées d’Exchange 2013 soient stockées conjointement dans Exchange. Vous pouvez utiliser l’intégration de Microsoft Exchange pour le stockage des données d’archivage pour les utilisateurs hébergés sur Exchange 2013, si leurs boîtes aux lettres ont été placées dans la conservation inaltérable. Si vous n’avez pas de déploiement Exchange 2013 ou si vous préférez ne pas l’intégrer, ou si vous avez des utilisateurs de Lync qui ne sont pas hébergés sur Exchange 2013, vous pouvez déployer des bases de données d’archivage distinctes en utilisant SQL Server pour stocker des données archivées à partir de Lync communications. Vous pouvez configurer l’option intégration de Microsoft Exchange au niveau global, au niveau du site et au niveau du pool. Par défaut, l’intégration de Microsoft Exchange n’est pas activée.

  - **Le mode de gestion des données archivées**; La base de données d’archivage n’est pas destinée à la conservation longue durée et Lync Server 2013 ne fournit pas de solution de découverte électronique pour les données archivées, de sorte que les données doivent être déplacées vers un autre stockage. Lync Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées et qui crée des transcriptions sur les données archivées. Pour la stratégie globale et pour chaque site et stratégie d’utilisateur que vous créez, vous pouvez activer la purge des données et spécifier l’une des options suivantes:
    
      - Purgez les données d’archivage exportées et les données d’archivage stockées après un nombre spécifique de jours. Le nombre de jours minimum que vous pouvez spécifier est d’un jour. Le nombre maximal de jours que vous pouvez spécifier est de 2562 jours.
    
      - Purger les données d’archivage exportées uniquement. Cette option permet de purger tous les enregistrements qui ont été exportés et marqués comme approuvés par l’outil d’exportation de session.
    
    Vous pouvez configurer cette option au niveau global, au niveau du site et au niveau du pool. Par défaut, la suppression définitive n’est pas activée.

Vous pouvez contrôler l’archivage en utilisant les méthodes suivantes:

  - **Stratégies**d’archivage. Pour activer et désactiver l’archivage des communications internes et externes, vous devez utiliser une ou plusieurs stratégies d’archivage. Par défaut, aucun archivage n’est activé. Vous pouvez activer ou désactiver l’archivage des communications internes, des communications externes ou les deux dans votre déploiement à l’aide de la stratégie globale par défaut. Vous ne pouvez pas supprimer la politique globale. Vous pouvez spécifier une ou plusieurs stratégies de site facultatives pour activer ou désactiver l’archivage des communications internes et externes pour des sites spécifiques. Vous pouvez également spécifier une ou plusieurs stratégies utilisateur pour activer ou désactiver l’archivage pour des utilisateurs spécifiques et des groupes d’utilisateurs. Les stratégies de niveau utilisateur remplacent les stratégies de site. Les stratégies de niveau de site remplacent les stratégies de niveau global. Les stratégies de niveau utilisateur sont implémentées uniquement pour les utilisateurs spécifiques qui sont configurés pour utiliser cette stratégie. Les messages instantanés et les conférences de groupe ne sont archivés que si une stratégie pour au moins l’un des participants est configurée pour activer l’archivage.
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez l’intégration de Microsoft Exchange, les stratégies Exchange 2013 remplacent les stratégies d’archivage de Lync Server pour tous les utilisateurs hébergés sur les serveurs Exchange 2013.

    
    </div>

  - **Configurations**d’archivage. Vous pouvez utiliser une ou plusieurs configurations d’archivage pour spécifier la plupart des options d’archivage décrites précédemment dans cette rubrique, à l’exception de l’archivage des communications internes et externes (configurées à l’aide de stratégies d’archivage, comme décrit dans la section puce précédente). La configuration de l’archivage inclut la configuration globale par défaut et les configurations de site et de pool facultatives. Vous ne pouvez pas supprimer la configuration globale. Les configurations au niveau du pool remplacent les configurations au niveau du site. Les configurations de niveau de site remplacent la configuration de niveau global.

Dans le cadre de votre analyse requise, vous devez déterminer la configuration de la configuration de l’archivage global et de la stratégie d’archivage globale. Vous devez également définir vos exigences pour toutes les configurations de l’archivage au niveau du site, les configurations d’archivage au niveau du groupe, les stratégies d’archivage au niveau du site et les stratégies d’archivage au niveau utilisateur.

Si vous déployez l’archivage pour une liste frontale ou un serveur Standard Edition Server, vous devez l’activer pour tous les autres pools front-end et serveurs Standard Edition dans votre déploiement. Pour cela, vous devez faire en sorte que les utilisateurs dont les communications doivent être archivées puissent être invités à une conversation de groupe par messagerie instantanée ou à une réunion hébergée sur un autre pool. Si l’archivage n’est pas activé sur le pool dans lequel la conversation ou la réunion est hébergée, il est possible que les données de la Conférence ne soient pas archivées. L’archivage fonctionne toujours pour l’archivage des utilisateurs activés et de tous les messages INSTANTANÉs, mais pas les contenus et événements de conférence.

<div>


> [!NOTE]  
> Pour permettre la délégation de tâches administratives tout en préservant les normes de sécurité de votre&nbsp;organisation, Lync Server 2013 utilise le contrôle d’accès basé sur les rôles (RBAC). Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis. Pour configurer des stratégies d’archivage et de configuration de l’archivage Lync, l’utilisateur doit être affecté au rôle CsArchivingAdministrator (à moins que la configuration ne soit réalisée directement sur le serveur où l’archivage est déployé, au lieu d’un autre ordinateur). Pour plus d’informations sur le contrôle RBAC, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</A> dans la documentation de planification. Pour obtenir la liste des droits d’utilisateur, autorisations et rôles requis pour le déploiement d’archivage, voir <A href="lync-server-2013-deployment-checklist-for-archiving.md">liste de vérification de déploiement pour l’archivage dans Lync Server 2013</A>, disponible dans la documentation de planification et la documentation de déploiement.<BR>Si vous utilisez l’intégration de Microsoft Exchange, la configuration des stratégies Exchange exige des droits et des autorisations d’administrateur appropriés. Pour plus d’informations, consultez la documentation Exchange 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

