---
title: Topologies prises en charge par Lync Server 2013
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
ms.openlocfilehash: 732b9a70ee61ce4ecdf19b3f668ba09a3416cca9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Topologies prises en charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-14_

Lync Server 2013 prend en charge le déploiement de sites sur site dans une organisation et l’intégration de déploiements sur site avec des déploiements Lync Online, qui est appelé déploiement hybride. Dans un déploiement hybride, certains utilisateurs sont hébergés localement et d’autres sont hébergés en ligne.

Pour les déploiements locaux, Lync Server 2013 prend en charge le déploiement d’un ou plusieurs sites qui peuvent être ajustés pour répondre aux exigences de haute disponibilité et d’emplacement. Vous pouvez structurer ces sites et leurs composants pour qu’ils répondent aux exigences de résistance et d’accès de votre organisation.

Un déploiement sur site de Lync Server 2013 se compose des éléments suivants :

  - Votre déploiement doit inclure au moins un site central (également appelé centre de données). Chaque site central doit comporter au moins un pool de serveurs frontaux Enterprise Edition ou un serveur Standard Edition. Cela consiste en les éléments suivants :
    
      - Un pool de serveurs frontaux Enterprise Edition, qui se compose d’un ou de plusieurs serveurs frontaux (généralement au moins deux serveurs frontaux, pour l’extensibilité) et d’un serveur principal distinct. Un pool frontal peut contenir un maximum de douze serveurs frontaux. L’équilibrage de charge est requis en cas de plusieurs serveurs frontaux. Nous conseillons l’équilibrage de la charge DNS pour le trafic SIP, mais l’équilibrage de la charge matérielle est également pris en charge. Si vous utilisez l’équilibrage de la charge DNS pour le trafic SIP, un équilibreur de la charge matérielle est tout de même nécessaire pour le trafic HTTP. Nous recommandons la mise en miroir SQL Server pour la haute disponibilité des bases de données. La base de données principale requiert une instance séparée, mais vous pouvez colocaliser les bases de données d’archivage, de surveillance, de conversation permanente et de conformité de la conversation permanente avec elle. Lync Server 2013 prend en charge l’utilisation d’un cluster partagé pour les partages de fichiers de votre déploiement. Pour plus d’informations sur les exigences de stockage des bases de données, voir [Database Software support in Lync Server 2013](lync-server-2013-database-software-support.md). Pour plus d’informations sur les exigences en matière de stockage de fichiers, voir [File Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        <div>
        

        > [!IMPORTANT]  
        > Si vous colocaliser des bases de données Lync Server, nous vous recommandons vivement d’évaluer tous les facteurs susceptibles d’affecter la disponibilité et les performances. Pour vérifier les capacités de basculement, il est recommandé de tester tous les scénarios de basculement.

        
        </div>
    
      - Le serveur Standard Edition, qui comporte une base de données SQL Server Express colocalisée.

  - Votre déploiement peut également inclure un ou plusieurs sites de succursale associés à un site central.

Cette section décrit les sites et les composants d’un déploiement Lync Server 2013. Pour plus d’informations sur le site, la topologie et la planification des composants de Lync Server 2013, voir concepts de base de la [topologie que vous devez connaître avant la planification de Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) et des [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification. Pour plus d’informations sur l’intégration des composants de versions précédentes, voir [prise en charge des chemins de migration et scénarios de coexistence dans Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour les rôles serveur frontal, serveur Edge, médiation et directeur.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>Topologies et composants de site central (localement)

Bien qu’une topologie de site central doive obligatoirement inclure un pool de serveurs frontaux ou un seul serveur Standard Edition, chaque site central peut héberger les éléments suivants :

  - Plusieurs pools de serveurs frontaux, qui peuvent résider dans le même domaine ou dans des domaines différents. Toutefois, tous les serveurs frontaux d’un pool et le serveur principal de ce même pool doivent résider dans le même domaine.

  - Plusieurs serveurs Standard Edition Server.

  - Office Web Apps Server, qui est utilisé avec les applications Office Web dans Lync Server 2013 pour gérer le partage et le rendu des présentations Microsoft PowerPoint.

  - Serveur Edge ou pool de serveurs Edge dans votre réseau de périmètre, si vous souhaitez que votre déploiement prenne en charge les partenaires fédérés, la connectivité PIC, une passerelle XMPP (extensible Messaging and Presence Protocol), l’accès des utilisateurs distants, la participation des utilisateurs anonymes aux réunions ; ou la messagerie unifiée Exchange. Vous ne pouvez pas colocaliser d’autres rôles serveur avec le serveur Edge. Nous recommandons l’équilibrage de la charge DNS, lorsqu’il est approprié, mais l’équilibrage de la charge matérielle est également pris en charge. Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur l’une des interfaces Edge et l’équilibrage de la charge matérielle sur l’autre. Pour plus d’informations sur les exigences et la prise en charge de l’équilibrage de charge, voir [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

  - Serveur de médiation ou pool, si vous souhaitez prendre en charge voix entreprise ou conférence rendez-vous dans un pool frontal sur le site central. En fonction de la façon dont vous déployez la prise en charge voix entreprise, vous pouvez colocaliser le serveur de médiation dans un pool frontal (valeur par défaut) ou déployer un serveur de médiation ou un pool autonome. Vous pouvez utiliser DNS, le matériel ou l’équilibrage de charge d’application (le cas échéant) pour distribuer le trafic à partir de l’homologue de passerelle d’un pool de serveurs de médiation, y compris une passerelle RTC, un système IP-PBX ou un contrôle de frontière de session de jonction SIP. Pour plus d’informations sur la planification de la topologie de serveur de médiation appropriée, voir [Deployment Guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) dans la documentation de planification.

  - Serveur de conversation permanente : Si vous souhaitez que les utilisateurs puissent participer à des conversations en plusieurs rubriques basées sur des sujets qui persistent dans le temps. Pour augmenter la capacité et la fiabilité, votre topologie peut inclure plusieurs ordinateurs exécutant un serveur de conversation permanente. Vous ne pouvez pas colocaliser le serveur de conversation permanente avec d’autres rôles serveur dans un pool d’entreprise. Toutefois, vous pouvez colocaliser le serveur de conversation permanente sur un serveur Standard Edition. La conversation permanente requiert une base de données et, si vous implémentez la conformité de conversation permanente, une base de données de conformité de conversation permanente, mais ces bases de données peuvent être colocalisées avec les bases de données d’archivage, de surveillance ou sur le server principal d’un pool de serveurs frontaux Enterprise Edition. Pour plus d’informations sur la planification de la topologie de serveur de conversation permanente appropriée, voir [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

  - Une surveillance, si vous voulez prendre en charge la collecte des données pour la qualité de l’expérience (QoE) audio/vidéo et l’enregistrement des détails des appels (CDR) pour les conférences Voix Entreprise et A/V de votre déploiement. Vous pouvez également installer Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager), qui utilise la surveillance des données de type CDR et QoE pour générer des alertes quasi en temps réel qui indiquent l’intégrité de la fiabilité des appels et de la qualité des médias. La surveillance, lorsqu’elle est déployée, est colocalisée sur des serveurs frontaux ou un serveur Standard Edition. La surveillance requiert une base de données, mais celle-ci peut être colocalisée avec les bases de données d’archivage, de conversation permanente, de conformité de conversation permanente ou sur le serveur principal d’un pool de serveurs frontaux Enterprise Edition.

  - L’archivage, si vous voulez archiver les communications de messagerie instantanée et le contenu des réunions (pour des raisons de conformité) dans votre déploiement. L’archivage, lorsqu’il est déployé, est colocalisé sur des serveurs frontaux ou un serveur Standard Edition. Le stockage d’archivage nécessite le déploiement d’une base de données d’archivage ou l’intégration avec le stockage Exchange 2013. Si vous utilisez les deux, appelé *mode mixte*, le stockage Exchange 2013 est utilisé pour stocker les données d’archivage des utilisateurs hébergés sur Exchange 2013, et la base de données d’archivage est utilisée pour archiver les données pour tous les autres utilisateurs de votre déploiement. Si vous avez besoin d’une base de données d’archivage, elle peut être colocalisée avec les bases de données de surveillance, de conversation permanente, de conformité de conversation permanente ou sur le serveur principal d’un pool de serveurs frontaux. Pour plus d’informations sur la planification de la topologie d’archivage appropriée, voir [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.

  - Directeur ou pool Directeur, si vous souhaitez faciliter la résistance et la redirection des demandes utilisateur Lync Server 2013 vers le pool d’accueil de l’utilisateur, qui peut être un pool frontal Enterprise Edition ou un serveur Standard Edition. Nous vous recommandons de déployer un directeur ou un pool directeur dans chaque site central prenant en charge l’accès des utilisateurs externes et dans chaque site central dans lequel vous déployez un ou plusieurs pools de serveurs frontaux. Chaque pool directeur peut contenir jusqu’à dix directeurs. Un directeur ne peut pas être colocalisé avec un autre rôle serveur. Pour plus d’informations sur la planification de la topologie de directeur appropriée, reportez-vous à la rubrique [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

  - Proxy inverse, qui n’est pas un composant Lync Server 2013, mais qui est nécessaire si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés ou pour prendre en charge le trafic de mobilité. Vous ne pouvez pas colocaliser un serveur proxy inverse avec un rôle serveur Lync Server 2013, mais vous pouvez implémenter la prise en charge du proxy inverse pour un déploiement Lync Server 2013 en configurant la prise en charge sur un serveur proxy inverse existant de votre organisation qui est utilisé pour d’autres programmes. Pour plus d’informations sur les serveurs proxy inverses, voir [Setting up Reverse Proxy Servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) dans la documentation de déploiement.

<div>


> [!NOTE]  
> Dans Lync Server 2013, la conférence A/V, la surveillance et l’archivage s’exécutent sur les serveurs frontaux et ne sont plus des rôles serveur distincts.



</div>

Tous les pools frontaux et les serveurs Standard Edition Server que vous déployez sur un site central partagent tout ou partie des éléments suivants sur le site central :

  - Directeur ou pool directeur

  - Serveur ou pool de serveurs de médiation autonome

  - Office Web Apps Server

  - Serveur ou pool de serveurs Edge

  - Pool ou serveur de conversations permanentes

  - Surveillance

  - Archivage

<div>


> [!NOTE]  
> Un serveur de messagerie unifiée Exchange peut être implémenté avec votre déploiement Lync Server 2013 si vous souhaitez prendre en charge l’intégration de la messagerie unifiée Exchange 2013, mais il ne s’agit pas d’un composant du site Lync Server 2013.



</div>

Plusieurs sites centraux peuvent partager tout ou partie des éléments suivants déployés sur le site central :

  - Serveur ou pool de serveurs de médiation autonome

  - Serveur ou pool de serveurs Edge

  - Pool ou serveur de conversations permanentes

  - Archivage

  - Surveillance

<div>


> [!NOTE]  
> Un serveur de messagerie unifiée Exchange peut être implémenté avec votre déploiement Lync Server 2013 et partagé par plusieurs sites centraux, mais il ne s’agit pas d’un composant du site Lync Server 2013.



</div>

Pour plus d’informations sur les rôles serveur et les fonctionnalités de Lync Server 2013, voir [rôles serveur dans Lync server 2013](lync-server-2013-server-roles.md) dans la documentation de planification.

Pour obtenir un résumé de la prise en charge de la colocalisation des serveurs Lync Server 2013, voir prise en charge de la [colocalisation 2013 de serveur](lync-server-2013-supported-server-collocation.md)

Outre les rôles serveur et les fonctionnalités abordés dans cette section, Lync Server 2013 comporte des composants et des options supplémentaires, qui peuvent inclure une partie ou l’ensemble des éléments suivants :

  - Pare-feu

  - Passerelles PSTN (si Voix Entreprise est déployé)

  - Serveur de messagerie unifiée Exchange

  - Équilibrage de charge DNS

  - Programmes d’équilibrage de la charge matérielle

  - Bases de données SQL Server

  - Partages de fichiers

Pour plus d’informations sur toutes les fonctionnalités, composants et options de Lync Server 2013, reportez-vous à la documentation de planification.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>Topologies et composants de sites de succursale (localement)

Un site de succursale est associé à un site central et chaque Survivable Branch Appliance d’un site de succursale est associé à un pool de serveurs frontaux Enterprise Edition ou à un serveur Standard Edition hébergé dans le site central associé. Les sites de succursale offrent des fonctionnalités différentes selon le site central auxquels ils sont associés. Pour cette raison, les sites de succursale ne comportent que les composants suivants :

  - Un Survivable Branch appliance, qui combine une passerelle RTC (réseau téléphonique commuté) avec certaines fonctionnalités Lync Server. Un serveur de médiation peut être colocalisé avec l’instance du serveur d’inscriptions sur le Survivable Branch appliance et vous pouvez déployer un serveur de médiation autonome ou un pool de serveurs de médiation.

  - Un serveur Survivable Branch Server, qui est un serveur exécutant Windows Server sur lequel le logiciel de serveur d’inscriptions et de médiation Lync Server 2013 est installé.

  - Une passerelle PSTN autonome (indépendante du Survivable Branch Appliance) et un serveur de médiation autonome.

La configuration requise pour les serveurs Survivable Branch Server est identique à celle requise pour tout rôle serveur Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

