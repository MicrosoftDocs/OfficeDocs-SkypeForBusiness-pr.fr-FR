---
title: Topologies prises en charge dans Lync Server 2013
TOCTitle: Topologies prises en charge
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425833(v=OCS.15)
ms:contentKeyID: 49296823
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologies prises en charge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-01-14_

Lync Server 2013 prend en charge le déploiement des sites locaux d’une organisation et l’intégration de ces déploiements locaux aux déploiements Skype Entreprise Online, connue sous le nom de déploiement hybride. Dans un déploiement hybride, certains utilisateurs sont hébergés localement et d’autres sont hébergés en ligne.

Pour les déploiements locaux, Lync Server 2013 prend en charge le déploiement d’un ou plusieurs sites qui peuvent évoluer selon vos besoins en matière de disponibilité et d’emplacements. Vous pouvez structurer ces sites et leurs composants pour qu’ils répondent aux exigences de résistance et d’accès de votre organisation.

Un déploiement Lync Server 2013 local doit suivre les spécifications suivantes :

  - Votre déploiement doit inclure au moins un site central (également appelé centre de données). Chaque site central doit comporter au moins un pool de serveurs frontaux Enterprise Edition ou un serveur Standard Edition. Cela consiste en les éléments suivants :
    
      - Un pool de serveurs frontaux Enterprise Edition, qui se compose d’un ou de plusieurs serveurs frontaux (généralement au moins deux serveurs frontaux, pour l’extensibilité) et d’un serveur principal distinct. Un pool de serveurs frontaux peut contenir au maximum douze serveurs frontaux. L’équilibrage de charge est requis en présence de plusieurs serveurs frontaux. Nous conseillons l’équilibrage de la charge DNS pour le trafic SIP, mais l’équilibrage de la charge matérielle est également pris en charge. Si vous utilisez l’équilibrage de la charge DNS pour le trafic SIP, un équilibreur de la charge matérielle est tout de même nécessaire pour le trafic HTTP. Nous vous conseillons d’utiliser la mise en miroir de SQL Server pour la haute disponibilité des bases de données. La base de données principale requiert une instance distincte, mais vous pouvez colocaliser les bases de données d’archivage, de surveillance, de conversation permanente et de conformité de la conversation permanente avec elle. Lync Server 2013 prend en charge l’utilisation d’un cluster partagé pour le partage de fichiers dans votre déploiement. Pour plus d’informations sur la configuration requise en termes de stockage de base de données, reportez-vous à [Prise en charge du logiciel de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md). Pour plus d’informations sur la configuration requise en termes de stockage de fichiers, reportez-vous à [Prise en charge du stockage des fichiers dans Lync Server 2013](lync-server-2013-file-storage-support.md).
        
        > [!IMPORTANT]  
        > Si vous colocalisez des bases de données Lync Server, il est fortement recommandé d’évaluer tous les facteurs susceptibles d’avoir des répercussions sur la disponibilité et les performances. Pour vérifier les capacités de basculement, il est recommandé de tester tous les scénarios de basculement.    
      - Le serveur Standard Edition, qui comporte une base de données SQL Server Express colocalisée.

  - Votre déploiement peut également inclure un ou plusieurs sites de succursale associés à un site central.

Cette section présente les sites et composants d’un déploiement de Lync Server 2013. Pour plus d’informations sur la planification des sites, de la topologie et des composants de Lync Server 2013, reportez-vous à [Tâches de topologie de base à connaître avant la planification pour Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) et [Topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification. Pour plus d’informations sur l’intégration de composants des versions précédentes, reportez-vous à [Chemins de migration et scénarios de coexistence pris en charge dans Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).

> [!NOTE]  
> Les pools étendus ne sont pas pris en charge pour les rôles serveur Serveur frontal, Serveur Edge, Serveur de médiation et Directeur.

## Topologies et composants de site central (localement)

Même si une topologie de site central doit obligatoirement inclure un pool de serveurs frontaux ou un seul serveur Standard Edition, chaque site central peut héberger les éléments suivants :

  - Plusieurs pools de serveurs frontaux, qui peuvent se trouver dans le même domaine ou dans des domaines différents. Cependant, tous les serveurs frontaux d’un pool et le serveur principal de ce même pool doivent se trouver dans le même domaine.

  - Plusieurs serveurs Standard Edition Server.

  - Office Web Apps Server, utilisé avec Office Web Apps dans Lync Server 2013 pour gérer le partage et le rendu des présentations Microsoft PowerPoint.

  - Un serveur Edge ou un pool de serveurs Edge de votre réseau de périmètre, si vous voulez que le déploiement prenne en charge les partenaires fédérés, la connectivité PIC, une passerelle XMPP (Extensible messaging and presence protocol), l’accès des utilisateurs distants, la participation des utilisateurs anonymes aux réunions ou la messagerie unifiée Exchange. Vous ne pouvez pas colocaliser d’autres rôles serveur avec le serveur Edge. Nous recommandons l’équilibrage de la charge DNS, lorsqu’il est approprié, mais l’équilibrage de la charge matérielle est également pris en charge. Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur l’une des interfaces Edge et l’équilibrage de la charge matérielle sur l’autre. Pour plus d’informations sur la configuration requise pour l’équilibrage de la charge et sa prise en charge, reportez-vous à [Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification et [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.

  - Un serveur ou un pool de serveurs de médiation, si vous voulez qu’un pool frontal prenne en charge Voix Entreprise ou les conférences rendez-vous au niveau du site central. En fonction du mode de déploiement de la prise en charge de Voix Entreprise, vous pouvez colocaliser le serveur de médiation dans un pool de serveurs frontaux (configuration par défaut) ou déployer un serveur ou pool de serveurs de médiation autonome. Vous pouvez utiliser l’équilibrage de la charge DNS, matérielle ou d’applications (le cas échéant) pour répartir le trafic provenant d’un homologue de passerelle du pool de serveurs de médiation, dont une passerelle RTC, un système PBX IP ou un contrôleur SBC de jonction SIP. Pour plus d’informations sur la planification de la topologie de serveur de médiation appropriée, reportez-vous à [Instructions de déploiement du serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) dans la documentation de planification.

  - Un serveur de conversations permanentes, si vous voulez que les utilisateurs puissent participer à des conversations persistantes au fil du temps, à plusieurs et basées sur un thème. Pour une capacité et une fiabilité accrues, votre topologie peut inclure plusieurs ordinateurs exécutant un serveur de conversations permanentes. Vous ne pouvez pas colocaliser un serveur de conversations permanentes avec d’autres rôles serveur dans un pool Enterprise. Cependant, vous pouvez colocaliser un serveur de conversations permanentes sur un serveur Standard Edition. La conversation permanente requiert une base de données et, si vous implémentez la conformité de conversation permanente, une base de données de conformité de conversation permanente, mais ces bases de données peuvent être colocalisées avec les bases de données d’archivage, de surveillance ou sur le server principal d’un pool de serveurs frontaux Enterprise Edition. Pour plus d’informations sur la planification de la topologie appropriée du serveur de conversations permanentes, reportez-vous à [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

  - Une surveillance, si vous voulez prendre en charge la collecte des données pour la qualité de l’expérience (QoE) audio/vidéo et l’enregistrement des détails des appels (CDR) pour les conférences Voix Entreprise et A/V de votre déploiement. Vous pouvez aussi installer Microsoft System Center Operations Manager (anciennement Microsoft Operations Manager), qui utilise des données QoE et CDR de surveillance pour générer presqu’en temps réel des alertes indiquant l’intégrité de la fiabilité des appels ainsi que la qualité multimédia. La surveillance, lorsqu’elle est déployée, est colocalisée sur des serveurs frontaux ou un serveur Standard Edition. La surveillance requiert une base de données, mais celle-ci peut être colocalisée avec les bases de données d’archivage, de conversation permanente, de conformité de conversation permanente ou sur le serveur principal d’un pool de serveurs frontaux Enterprise Edition.

  - L’archivage, si vous voulez archiver les communications de messagerie instantanée et le contenu des réunions (pour des raisons de conformité) dans votre déploiement. L’archivage, lorsqu’il est déployé, est colocalisé sur des serveurs frontaux ou un serveur Standard Edition. Le stockage de l’archivage requiert le déploiement d’une base de données d’archivage ou l’intégration au stockage Exchange 2013. Si vous utilisez les deux, connu sous le nom de *mode mixte* , le stockage Exchange 2013 est utilisé pour stocker des données d’archivage pour les utilisateurs hébergés sur Exchange 2013, et la base de données d’archivage est utilisée pour tous les autres utilisateurs de votre déploiement. Si vous avez besoin d’une base de données d’archivage, elle peut être colocalisée avec les bases de données de surveillance, de conversation permanente, de conformité de conversation permanente ou sur le serveur principal d’un pool de serveurs frontaux. Pour plus d’informations sur la planification de la topologie d’archivage appropriée, reportez-vous à [Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.

  - Un directeur ou un pool directeur, si vous voulez faciliter la résistance et la redirection des requêtes utilisateur de Lync Server 2013 vers le pool central de l’utilisateur, qui peut être soit un pool de serveurs frontaux Enterprise Edition, soit un serveur Standard Edition. Nous vous recommandons de déployer un directeur ou un pool directeur dans chaque site central prenant en charge l’accès des utilisateurs externes et dans chaque site central dans lequel vous déployez un ou plusieurs pools de serveurs frontaux. Chaque pool directeur peut contenir jusqu’à dix directeurs. Un directeur ne peut pas être colocalisé avec un autre rôle serveur. Pour plus d’informations sur la planification de la topologie appropriée du directeur, reportez-vous à [Scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.

  - Un proxy inverse, qui n’est pas un composant Lync Server 2013. Il est nécessaire pour prendre en charge le partage du contenu web des utilisateurs fédérés ou le trafic de mobilité. Vous ne pouvez pas colocaliser un serveur proxy inverse avec un rôle serveur Lync Server 2013, mais vous pouvez implémenter la prise en charge du proxy inverse pour un déploiement Lync Server 2013 en configurant la prise en charge sur un serveur proxy inverse existant dans votre organisation, utilisé pour d’autres applications. Pour des informations sur les serveurs proxy inverse, reportez-vous à [Configuration des serveurs proxy inverses pour Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) dans la documentation de déploiement.

> [!NOTE]  
> Dans Lync Server 2013, la conférence A/V, la surveillance et l’archivage s’exécutent sur les serveurs frontaux et ne sont plus distincts des rôles serveur.

Tous les pools frontaux et les serveurs Standard Edition Server que vous déployez sur un site central partagent tout ou partie des éléments suivants sur le site central :

  - Directeur ou pool directeur

  - Serveur ou pool de serveurs de médiation autonome

  - Office Web Apps Server

  - Serveur ou pool de serveurs Edge

  - Pool ou serveur de conversations permanentes

  - Analyse

  - Archivage

> [!NOTE]  
> Vous pouvez implémenter un serveur de messagerie unifiée Exchange au sein de votre déploiement Lync Server 2013 pour prendre en charge l’intégration de la messagerie unifiée Exchange 2013. Ce composant ne fait pas partie du site Lync Server 2013.

Plusieurs sites centraux peuvent partager tout ou partie des éléments suivants déployés sur le site central :

  - Serveur ou pool de serveurs de médiation autonome

  - Serveur ou pool de serveurs Edge

  - Pool ou serveur de conversations permanentes

  - Archivage

  - Analyse

> [!NOTE]  
> Vous pouvez implémenter un serveur de messagerie unifiée Exchange au sein de votre déploiement Lync Server 2013 et le partager entre plusieurs sites centraux. Ce composant ne fait pas partie du site Lync Server 2013.

Pour plus d’informations sur les rôles serveur Lync Server 2013, reportez-vous à [Rôles serveur dans Lync Server 2013](lync-server-2013-server-roles.md) dans la documentation de planification.

Pour obtenir un résumé de la prise en charge de la colocalisation du serveur Lync Server 2013, reportez-vous à [Colocalisation de serveur prise en charge dans Lync Server 2013](lync-server-2013-supported-server-collocation.md).

Outre les rôles serveur et fonctionnalités précédemment abordés dans cette section, Lync Server 2013 comporte des composants et options supplémentaires, notamment :

  - Pare-feu

  - Passerelles RTC (si Voix Entreprise est déployé)

  - Serveur de messagerie unifiée Exchange

  - Équilibrage de charge DNS

  - Programmes d’équilibrage de la charge matérielle

  - Bases de données SQL Server

  - Partages de fichiers

Pour plus d’informations sur toutes les fonctionnalités, composants et options de Lync Server 2013, reportez-vous à la documentation de planification.

## Topologies et composants de sites de succursale (localement)

Un site de succursale est associé à un site central et chaque Survivable Branch Appliance d’un site de succursale est associé à un pool de serveurs frontaux Enterprise Edition ou à un serveur Standard Edition hébergé dans le site central associé. Les sites de succursale offrent des fonctionnalités différentes selon le site central auxquels ils sont associés. Pour cette raison, les sites de succursale ne comportent que les composants suivants :

  - Un Survivable Branch Appliance, qui combine une passerelle RTC et des fonctionnalités de Lync Server. Vous pouvez colocaliser un serveur de médiation avec une instance du serveur d’inscriptions sur le Survivable Branch Appliance et vous pouvez déployer un serveur de médiation autonome ou un pool de serveurs de médiation.

  - Un Survivable Branch Server, qui est un serveur Windows exécutant Windows Server sur lequel le logiciel de serveurs d’inscriptions et de médiation Lync Server 2013 est installé.

  - Une passerelle RTC autonome (indépendante du Survivable Branch Appliance) et un serveur de médiation autonome.

La configuration requise par les serveurs Survivable Branch Server est la même que pour tout rôle serveur de Lync Server 2013.

