---
title: Topologies prises en charge dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f200cde348d1fbdc931daa25abef28aec804a1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Topologies prises en charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-14_

Lync Server 2013 prend en charge le déploiement de sites en local au sein d’une organisation et l’intégration de déploiements sur site à des déploiements Lync Online, un déploiement hybride. Dans un déploiement hybride, certains utilisateurs sont hébergés sur site et certains utilisateurs sont hébergés en ligne.

Pour les déploiements sur site, Lync Server 2013 prend en charge le déploiement d’un ou de plusieurs sites qui peuvent être mis à l’échelle afin de répondre aux exigences d’emplacement et de haute disponibilité. Vous pouvez structurer ces sites et leurs composants conformément aux exigences d’accès et de résilience de votre organisation.

Un déploiement local de Lync Server 2013 se compose des éléments suivants :

  - Votre déploiement doit inclure au moins un site central (également appelé centre de données). Chaque site central doit contenir au moins un pool frontal Enterprise Edition ou un serveur Standard Edition Server. Il s’agit des éléments suivants :
    
      - Pool frontal Enterprise Edition, qui se compose d’un ou de plusieurs serveurs frontaux (en général, au moins deux serveurs frontaux pour l’évolutivité) et d’un serveur principal séparé. Un pool frontal peut contenir un maximum de 12 serveurs frontaux. L’équilibrage de charge est requis pour plusieurs serveurs front-end. Pour le trafic SIP, nous vous recommandons d’utiliser l’équilibrage de charge DNS, mais l’équilibrage de charge matérielle est également pris en charge. Si vous utilisez l’équilibrage de charge DNS pour le trafic SIP, vous avez encore besoin d’un équilibreur de charge matérielle pour le trafic HTTP. Nous recommandons la mise en miroir SQL Server pour une haute disponibilité des bases de données. La base de données principale nécessite une instance distincte, mais vous pouvez collocate la base de données d’archivage, la base de données de surveillance, la base de données de conversation permanente et la base de données de conformité aux conversations permanentes. Lync Server 2013 prend en charge l’utilisation d’un cluster partagé pour les partages de fichiers dans votre déploiement. Pour plus d’informations sur les exigences de stockage de base de données, voir [prise en charge de logiciels de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md). Pour plus d’informations sur les exigences en matière de stockage de fichiers, voir [prise en charge du stockage de fichiers dans Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Si vous collocate les bases de données Lync Server, nous vous conseillons vivement d’évaluer tous les facteurs susceptibles d’affecter la disponibilité et les performances. Pour vérifier les capacités de basculement, nous vous recommandons de tester tous les scénarios de basculement.

        
        </div>
    
      - Standard Edition Server, qui inclut une base de données SQL Server Express colocalisée.

  - Votre déploiement peut également avoir un ou plusieurs sites de succursale associés à un site central.

Cette section décrit les sites et composants d’un déploiement 2013 de Lync Server. Pour plus d’informations sur le site, la topologie et la planification des composants Lync Server 2013, voir [notions de base sur la topologie que vous devez connaître avant de planifier Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) et des [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification. Pour plus d’informations sur l’intégration des composants des versions précédentes, voir [les chemins de migration et les scénarios de coexistence pris en charge dans Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour les rôles serveur frontal, Edge, médiation et directeur.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topologies et composants de site central (en local)

Même si une topologie de site central doit inclure un pool frontal ou un serveur Standard Edition Server standard, chaque site central peut également contenir les éléments suivants :

  - Plusieurs listes frontales qui peuvent se trouver dans le même domaine ou dans des domaines différents. Toutefois, tous les serveurs frontaux dans une liste frontale et le serveur principal pour ce pool doivent se trouver dans le même domaine.

  - Plusieurs serveurs Standard Edition.

  - Office Web Apps Server, qui est utilisé avec les applications Office Web App dans Lync Server 2013 pour gérer le partage et le rendu des présentations Microsoft PowerPoint.

  - Serveur Edge ou pool Edge dans votre réseau de périmètre, si vous souhaitez que votre déploiement prenne en charge les partenaires fédérés, la connectivité PIC (Public IM Connectivity), une passerelle de messagerie instantanée ou Exchange Unified Messaging (UM). Vous ne pouvez pas collocate d’autres rôles de serveur avec un serveur Edge. Nous vous recommandons d’utiliser l’équilibrage de charge DNS, le cas échéant, mais l’équilibrage de charge matérielle est également pris en charge. L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge. Pour plus d’informations sur les exigences et la prise en charge de l’équilibrage de charge, voir [planification d’un accès utilisateur externe dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

  - Serveur de médiation ou pool, si vous souhaitez prendre en charge les conférences rendez-vous ou la Conférence rendez-vous dans un pool frontal sur le site central. En fonction du mode de déploiement de la prise en charge de voix entreprise, vous pouvez collocate le serveur de médiation dans un pool frontal (par défaut) ou déployer un serveur ou un pool de médiation autonome. Vous pouvez utiliser l’équilibrage de charge DNS, matériel ou de l’application (le cas échéant) pour distribuer le trafic à partir du poste de passerelle d’un pool de serveurs de médiation, y compris une passerelle RTC, un PBX IP ou un contrôle de bordure de session de type SIP Trunk (SBC). Pour plus d’informations sur la planification de la topologie du serveur de médiation appropriée, voir [recommandations de déploiement pour le serveur de médiation dans Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) dans la documentation de planification.

  - Serveur de chat permanent, si vous souhaitez que les utilisateurs puissent participer à des conversations à plusieurs sujets, qui persistent dans le temps. Pour offrir plus de capacité et une fiabilité accrue, votre topologie peut inclure plusieurs ordinateurs exécutant une conversation permanente sur le serveur. Vous ne pouvez pas collocate serveur Chat permanent avec d’autres rôles serveur dans un pool d’entreprise. Toutefois, vous pouvez collocate serveur de chat permanent sur un serveur Standard Edition Server. La conversation permanente nécessite une base de données et, si vous implémentez une mise en œuvre de la conversion persistante, une base de données de compatibilité des conversations permanentes, mais les bases de données peuvent être colocalisées avec la base de données d’archivage, la base de données de surveillance ou le serveur principal d’une édition Enterprise Pool frontal. Pour plus d’informations sur la planification de la topologie serveur de chat permanent appropriée, reportez-vous à la section [planification du serveur de chat permanent dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

  - Surveillance, si vous souhaitez prendre en charge la collecte de données pour l’audio et la vidéo de qualité d’appel (QoE) et l’enregistrement des détails des appels (CDR) pour les conférences voix et audiovisuelles dans votre déploiement. Le cas échéant, vous pouvez installer Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager), qui utilise la surveillance des données CDR et QoE pour générer des alertes en temps réel qui indiquent l’état de la fiabilité des appels et de la qualité des médias. Le contrôle, lors de son déploiement, est colocalisé sur des serveurs frontaux ou un serveur Standard Edition Server. Le contrôle nécessite une base de données, mais la base de données peut être colocalisée avec la base de données d’archivage, la base de données de chat permanent, la base de données de conformité des conversations permanentles ou sur le serveur principal d’une liste frontale Enterprise Edition.

  - Archivage, si vous voulez archiver les communications par messagerie instantanée et le contenu de la réunion (pour des raisons de conformité) dans votre déploiement. L’archivage, lors de son déploiement, est colocalisé sur des serveurs frontaux ou un serveur Standard Edition Server. Le stockage d’archivage nécessite soit le déploiement d’une base de données d’archivage, soit l’intégration avec le stockage 2013 Exchange. Si vous utilisez les deux, qui est connu sous le nom de *mode mixte*, le stockage Exchange 2013 est utilisé pour stocker les données d’archivage des utilisateurs hébergés sur Exchange 2013 et la base de données d’archivage est utilisée pour archiver des données pour tous les autres utilisateurs de votre déploiement. Si vous avez besoin d’une base de données d’archivage, la base de données peut être désactivée sur la base de données de surveillance, la base de données de chat permanent, la base de données de conformité des conversations permanentes ou sur le serveur principal d’un pool frontal. Pour plus d’informations sur la planification de la topologie de l’archivage appropriée, voir [planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.

  - Le réalisateur ou le pool de réalisateur, si vous voulez faciliter la résilience et la redirection des requêtes utilisateur de Lync Server 2013 vers le pool de famille de l’utilisateur, qui peut être un pool frontal Enterprise Edition ou un serveur Standard Edition Server. Nous vous recommandons de déployer un réalisateur ou un pool de réalisateurs dans chaque site central prenant en charge l’accès des utilisateurs externes et dans chaque site central dans lequel vous déployez une ou plusieurs listes frontales. Chaque pool de Directors peut contenir un maximum de dix directeurs. Un Director ne peut pas être colocalisé avec un autre rôle serveur. Pour plus d’informations sur la planification de la topologie de réalisateur appropriée, reportez-vous à [la rubrique scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

  - Le proxy inverse, qui n’est pas un composant Lync Server 2013, est requis si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés ou pour la prise en charge du trafic de mobilité. Vous ne pouvez pas collocate un serveur proxy inverse avec un rôle serveur Lync Server 2013, mais vous pouvez mettre en œuvre la prise en charge du proxy inverse pour un déploiement de Lync Server 2013 en configurant la prise en charge sur un serveur proxy inverse existant de votre organisation qui est utilisé pour les autres applications. Pour plus d’informations sur les serveurs proxy inverse, voir [configuration de serveurs proxy inverse pour Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) dans la documentation de déploiement.

<div>


> [!NOTE]  
> Dans Lync Server 2013, les conférences, la surveillance et l’archivage A/V s’exécutent sur des serveurs frontaux et ne sont plus des rôles de serveur distincts.



</div>

Toutes les listes frontales et les serveurs Standard Edition Server que vous déployez sur un site central partagent l’une des options suivantes :

  - Pool de directeurs ou de réalisateurs

  - Serveur de médiation autonome ou pool

  - Office Web Apps Server

  - Serveur Edge ou pool de bords

  - Serveur de conversation permanent ou pool

  - Surveillance

  - Archivage

<div>


> [!NOTE]  
> Il est possible d’implémenter un serveur de messagerie unifiée Exchange avec le déploiement de Lync Server 2013 si vous souhaitez prendre en charge l’intégration de la messagerie unifiée Exchange 2013, mais qu’il ne s’agit pas d’un composant du site Lync Server 2013.



</div>

Les sites centraux multiples peuvent également partager les éléments suivants du déploiement dans un site central :

  - Serveur de médiation autonome ou pool

  - Serveur Edge ou pool de bords

  - Serveur de conversation permanent ou pool

  - Archivage

  - Surveillance

<div>


> [!NOTE]  
> Il est possible d’implémenter un serveur de messagerie unifiée Exchange avec le déploiement de Lync Server 2013 et partagé par plusieurs sites centraux, mais il ne s’agit pas d’un composant du site 2013 du serveur Lync.



</div>

Pour plus d’informations sur les rôles et les fonctionnalités du serveur Lync Server 2013, voir [rôles de serveur dans Lync Server 2013](lync-server-2013-server-roles.md) dans la documentation de planification.

Pour obtenir un résumé de la prise en charge de la prise en charge des serveurs Lync Server 2013, voir [prise en charge des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md).

Outre les rôles de serveur et les fonctionnalités abordés dans cette section, Lync Server 2013 comporte des composants et des options supplémentaires, qui peuvent inclure tout ou partie des éléments suivants :

  - Pare-feu

  - Passerelles RTC (si vous déployez Enterprise Voice)

  - Serveur de messagerie unifiée Exchange

  - Équilibrage de charge DNS

  - Programmes d’équilibrage de la charge matérielle

  - Bases de données SQL Server

  - Partages de fichiers

Pour plus d’informations sur l’ensemble des fonctionnalités, composants et options de Lync Server 2013, voir la documentation de planification.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Composants et topologies de site de succursale (sur site)

Un site de filiale est associé à un site central et chaque application de succursale Survivable dans un site de filiale est associée à un pool frontal Enterprise Edition ou un serveur Standard Edition Server dans le site central associé. Les sites de succursale dépendent du site central pour la plupart de leurs fonctionnalités, de sorte que les composants d’un site de succursale contiennent uniquement les éléments suivants :

  - Une unité de branchement survivant qui combine une passerelle de réseau téléphonique commuté (PSTN) et certaines fonctionnalités de Lync Server. Un serveur de médiation peut être colocalisé avec l’instance du Bureau d’enregistrement sur l’appareil de succursale survivant et vous pouvez déployer un serveur de médiation autonome ou un pool de serveurs de médiation.

  - Un serveur de succursales survivant, qui est un serveur exécutant Windows Server sur lequel est installé le logiciel serveur d’inscriptions et de médiation Lync Server 2013.

  - Passerelle RTC autonome (non incluse dans l’appareil de branchement survivant) et serveur de médiation autonome.

La configuration requise pour les serveurs de succursales Survivables est la même que celle des rôles serveur Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

