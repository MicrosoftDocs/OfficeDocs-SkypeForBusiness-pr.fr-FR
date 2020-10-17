---
title: 'Lync Server 2013 : définition de la configuration requise pour l’archivage'
description: 'Lync Server 2013 : définition de la configuration requise pour l’archivage.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b9f3257c56241ce921a18e16932689053ef430
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545530"
---
# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Définition de la configuration requise pour l’archivage dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Si votre organisation doit respecter les réglementations en matière de conformité, vous pouvez déployer l’archivage pour activer la prise en charge de l’archivage pour la messagerie instantanée et les conférences Lync Server 2013. Pour plus d’informations sur le type de contenu qui peut être archivé, reportez-vous à la rubrique [vue d’ensemble de l’archivage dans Lync Server 2013](lync-server-2013-overview-of-archiving.md) dans la documentation de planification.

Pour implémenter l’archivage, vous devez d’abord décider comment répondre aux exigences de votre organisation pour l’archivage. Pour cela, vous devez déterminer les éléments suivants :

  - **Quand déployer l’archivage**. Vous pouvez déployer l’archivage dans le cadre de votre déploiement initial de Lync Server 2013, ou vous pouvez l’ajouter à un déploiement existant. Vous déployez l’archivage à l’aide du générateur de topologie pour l’ajouter à votre topologie, puis en publiant la topologie.

  - **S’il faut archiver les communications internes ou externes**. Vous pouvez activer l’archivage pour les communications internes (communications entre les utilisateurs internes), les communications externes (communications qui incluent au moins un utilisateur en dehors de votre réseau interne), ou les deux. Vous pouvez spécifier ces options pour l’ensemble de votre organisation ou vous pouvez les spécifier pour des sites et des pools spécifiques. Par défaut, aucune de ces options n’est activée.
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez l’intégration de Microsoft Exchange pour stocker des données archivées, vos paramètres Exchange contrôlent si les communications Lync sont archivées. Si votre déploiement inclut plusieurs forêts, vous devez synchroniser les paramètres entre Lync Server et Exchange. Le contrôle de l’archivage pour les communications internes ou externes n’est disponible que pour la stratégie Lync. Pour l’archivage intégré à Exchange, ces deux éléments seront archivés ou non archivés.

    
    </div>

  - **Pourquoi activer l’archivage**? Vous pouvez activer et désactiver l’archivage pour l’ensemble de votre déploiement au niveau global, et vous pouvez activer et désactiver l’archivage pour des sites et des utilisateurs spécifiques. À chacun de ces niveaux, vous spécifiez s’il faut activer l’archivage des sessions de messagerie instantanée (P2P), des conférences (réunions, qui sont des sessions à plusieurs) ou les deux. Par défaut, l’archivage est désactivé.

  - **La façon dont l’archivage est essentiel pour les utilisateurs de votre organisation**. Si l’archivage est essentiel au sein de votre organisation, vous pouvez spécifier que Lync Server 2013 s’exécute en mode critique, ce qui bloque les sessions de messagerie instantanée et de conférence en cas d’échec de l’archivage. Par exemple :
    
      - Si le service d’archivage ne peut temporairement pas envoyer un message à la file d’attente de la base de données ou insérer un message dans la base de données, les fonctionnalités de messagerie instantanée et de conférence sont bloquées dans le déploiement jusqu’à ce que la prise en charge de l’archivage soit restaurée.
    
      - Si un utilisateur de conférence télécharge un fichier, mais que le fichier ne peut pas être copié dans le magasin de fichiers d’archivage, la fonctionnalité de conférence est bloquée dans le déploiement jusqu’à ce que le problème soit résolu, mais la fonctionnalité de messagerie instantanée n’est pas bloquée.
    
    Vous pouvez configurer cette option au niveau global, au niveau du site et au niveau du pool. Par défaut, le mode Critical n’est pas activé.

  - **Utiliser l’intégration de Microsoft Exchange**. Cette option intègre le stockage d’archivage avec votre stockage Exchange 2013, afin que vos données archivées Lync Server et les données archivées Exchange 2013 soient stockées ensemble dans Exchange. Vous pouvez utiliser l’intégration Microsoft Exchange pour le stockage des données d’archivage pour les utilisateurs hébergés sur Exchange 2013, si leur boîte aux lettres a été mise en attente In-Place. Si vous ne disposez pas d’un déploiement d’Exchange 2013 ou si vous préférez ne pas l’intégrer ou si vous avez des utilisateurs Lync qui ne sont pas hébergés sur Exchange 2013, vous pouvez déployer des bases de données d’archivage distinctes à l’aide de SQL Server pour stocker les données archivées à partir de Lync communications. Vous pouvez configurer l’option intégration de Microsoft Exchange au niveau global, au niveau du site et au niveau du pool. Par défaut, l’intégration de Microsoft Exchange n’est pas activée.

  - **La manière dont les données archivées doivent être gérées**. La base de données d’archivage n’est pas destinée à la rétention à long terme et Lync Server 2013 ne fournit pas de solution e-Discovery (recherche) pour les données archivées, de sorte que les données doivent être déplacées vers un autre stockage. Lync Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées et qui crée des transcriptions pouvant faire l’objet d’une recherche des données archivées. Pour la stratégie globale, et pour chaque stratégie de site et utilisateur que vous créez, vous pouvez activer la purge des données et spécifier l’une des options suivantes :
    
      - Purger les données d’archivage exportées et les données d’archivage stockées après un nombre spécifique de jours. Le nombre minimal de jours que vous pouvez spécifier est d’un jour. Le nombre maximal de jours que vous pouvez spécifier est de 2562 jours.
    
      - Purger uniquement les données d’archivage exportées. Cette option purge tous les enregistrements qui ont été exportés et marqués comme étant sécurisés par l’outil d’exportation de session.
    
    Vous pouvez configurer cette option au niveau global, au niveau du site et au niveau du pool. Par défaut, le vidage n’est pas activé.

Vous contrôlez l’archivage à l’aide des méthodes suivantes :

  - Les **stratégies d’archivage**. Vous utilisez une ou plusieurs stratégies d’archivage pour activer et désactiver l’archivage des communications internes et externes. Par défaut, aucun archivage n’est activé. Vous activez ou désactivez l’archivage pour les communications internes, les communications externes ou les deux dans votre déploiement à l’aide de la stratégie globale par défaut. Il est impossible de supprimer la stratégie globale. Vous pouvez spécifier une ou plusieurs stratégies de site facultatives pour activer ou désactiver l’archivage des communications internes et externes pour des sites spécifiques. Vous pouvez également spécifier une ou plusieurs stratégies utilisateur pour activer ou désactiver l’archivage pour des utilisateurs et des groupes d’utilisateurs spécifiques. Les stratégies de niveau utilisateur remplacent les stratégies de site. Les stratégies au niveau du site remplacent les stratégies globales. Les stratégies au niveau de l’utilisateur sont implémentées uniquement pour les utilisateurs spécifiques qui sont configurés pour utiliser la stratégie. Les messages instantanés de groupe et les conférences sont archivés uniquement si une stratégie pour au moins un des participants est configurée pour activer l’archivage.
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez l’intégration de Microsoft Exchange, les stratégies Exchange 2013 remplacent les stratégies d’archivage de Lync Server pour tous les utilisateurs hébergés sur les serveurs Exchange 2013.

    
    </div>

  - **Configurations d’archivage**. Vous pouvez utiliser une ou plusieurs configurations d’archivage pour spécifier la plupart des options d’archivage décrites précédemment dans cette rubrique, à l’exception de l’activation de l’archivage des communications internes et externes (configurées à l’aide de stratégies d’archivage, comme décrit dans la puce précédente). Les configurations d’archivage incluent la configuration globale par défaut et les configurations facultatives de site et de pool. Vous ne pouvez pas supprimer la configuration globale. Les configurations au niveau du pool remplacent les configurations au niveau du site. Les configurations au niveau du site remplacent la configuration globale.

Dans le cadre de l’analyse de vos besoins, vous devez déterminer la configuration de la stratégie d’archivage globale et de la stratégie d’archivage globale. Vous devez également déterminer vos besoins pour toutes les configurations d’archivage au niveau du site, les configurations d’archivage au niveau du pool, les stratégies d’archivage au niveau du site et les stratégies d’archivage au niveau de l’utilisateur.

Si vous déployez l’archivage pour un pool frontal ou un serveur Standard Edition, vous devez l’activer pour tous les autres pools frontaux et serveurs Standard Edition de votre déploiement. Ces tâches sont nécessaires, car les utilisateurs dont les communications doivent être archivées peuvent être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool où la conversation ou la réunion est hébergée, toutes les données de conférence ne peuvent pas être archivées. L’archivage fonctionne toujours pour les utilisateurs activés pour l’archivage et tous les messages de messagerie instantanée, mais le contenu et les événements de conférence ne peuvent pas être archivés.

<div>


> [!NOTE]  
> Pour activer la délégation des tâches administratives tout en conservant les normes de sécurité de votre organisation, Lync Server 2013 &nbsp; utilise le contrôle d’accès basé sur un rôle (RBAC). Avec RBAC, les privilèges d’administrateur sont accordés en affectant des utilisateurs à des rôles d’administration prédéfinis. Pour configurer les stratégies d’archivage et les configurations d’archivage de Lync, l’utilisateur doit être affecté au rôle CsArchivingAdministrator (sauf si la configuration est réalisée directement sur le serveur sur lequel l’archivage est déployé, et non à distance à partir d’un autre ordinateur). Pour plus d’informations sur RBAC, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification. Pour obtenir la liste des droits, autorisations et rôles utilisateur requis pour le déploiement de l’archivage, voir <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment Checklist for Archiving in Lync Server 2013</A>, qui est disponible à la fois dans la documentation de planification et dans la documentation de déploiement.<BR>Si vous utilisez l’intégration de Microsoft Exchange, la configuration des stratégies Exchange requiert des droits et des autorisations d’administrateur appropriés. Pour plus d’informations, reportez-vous à la documentation Exchange 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

