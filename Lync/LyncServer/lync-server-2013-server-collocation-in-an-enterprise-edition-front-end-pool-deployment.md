---
title: "Coloc. de serveur LS 2013 lors d’un dépl. de pool frontal Enterprise Edition"
TOCTitle: Colocalisation de serveur lors d’un déploiement de pool frontal Enterprise Edition
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398102(v=OCS.15)
ms:contentKeyID: 49296119
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Colocalisation de serveur lors d’un déploiement de pool frontal Enterprise Edition pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-11_

Cette section décrit les rôles serveur, les bases de données et les partages de fichiers que vous pouvez colocaliser dans un déploiement de pool frontal Lync Server 2013.

## Rôles serveur

Dans Lync Server 2013, le service de conférence A/V, le service de médiation, la surveillance et l’archivage sont colocalisés sur le serveur frontal, mais ils doivent être configurés pour être activés. Si vous ne souhaitez pas colocaliser le serveur de médiation avec le serveur frontal, vous pouvez le déployer en tant que serveur de médiation autonome sur un ordinateur distinct.

Vous pouvez colocaliser un serveur d’application approuvées avec le serveur frontal.

Les rôles serveur suivants doivent être individuellement déployés sur un ordinateur distinct :

  - Directeur

  - Serveur Edge

  - Serveur de médiation (s’il n’est pas colocalisé avec le serveur frontal).

  - Office Web Apps Server

Vous ne pouvez pas colocaliser un rôle serveur conversation permanente avec le serveur frontal.

## Bases de données

Vous pouvez colocaliser chacune des bases de données suivantes sur le même serveur de base de données :

  - Base de données principale

  - Base de données de surveillance

  - Base de données d’archivage

  - Base de données de conversation permanente

  - Base de données de conformité de conversation permanente

Vous pouvez colocaliser une base de données ou l’ensemble de ces bases de données dans une instance unique de SQL Server ou utiliser une instance distincte de SQL Server pour chaque base de données, en tenant compte des limitations suivantes :

  - Chaque instance de SQL Server ne peut contenir qu’une seule base de données principale, une seule base de données de surveillance, une seule base de données d’archivage, une seule base de données de conversation permanente et une seule base de données de conformité de conversation permanente.

  - Le serveur de base de données ne peut pas prendre en charge plus d’un pool frontal, un déploiement d’archivage et un déploiement de surveillance, mais il peut prendre en charge un de chaque, que les bases de données utilisent la même instance de SQL Server ou des instances de SQL Server distinctes.

Vous pouvez colocaliser un partage de fichiers avec les bases de données, comme il est décrit dans la suite de cette section.

> [!NOTE]  
> Dans Lync Server 2013, vous pouvez intégrer le stockage d’archivage au stockage Exchange 2013 pour tout ou partie des utilisateurs de votre déploiement. En revanche, vous ne pouvez pas déployer des serveurs exécutant Lync Server, ni des composants sur les serveurs où se trouve le stockage Exchange.

> [!IMPORTANT]  
> Même si la colocation des bases de données est prise en charge, la taille des bases de données peut augmenter rapidement. Par exemple, lorsque vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données du serveur d’archivage peuvent devenir très importants. Pour cette raison, nous ne recommandons pas de colocaliser plusieurs bases de données, en particulier la base de données d’archivage, la base de données de conversation permanente ou la base de données de conformité de conversation permanente avec la base de données principale.

## Partage de fichiers

Le partage de fichier peut être un serveur distinct ou être colocalisé sur le même serveur que l’un ou l’ensemble des éléments suivants :

  - Serveur de base de données, dont le serveur principal d’un pool frontal Enterprise Edition

  - Base de données d’archivage

  - Base de données de surveillance

  - Base de données de conversation permanente

  - Base de données de conformité de conversation permanente

Un partage de fichiers unique peut être utilisé pour plusieurs pools frontaux et serveurs Standard Edition (sur le même site).

> [!NOTE]  
> Dans Lync Server 2013, la surveillance et l’archivage utilisent le partage de fichiers de Lync Server comme serveur frontal.

## Autres composants

Vous ne pouvez pas colocaliser un serveur proxy inverse, qui n’est pas un composant Lync Server 2013. Ce serveur est cependant requis dans votre déploiement si vous souhaitez prendre en charge le partage d’un contenu web pour des utilisateurs fédérés avec n’importe quel rôle serveur Lync Server 2013. Vous pouvez cependant implémenter une prise en charge de proxy inverse pour un déploiement Lync Server 2013 en configurant la prise en charge sur un serveur proxy inverse existant de votre organisation utilisé pour d’autres applications.

Vous ne pouvez pas colocaliser un composant messagerie unifiée Exchange ou un composant SharePoint avec un rôle SharePoint Server.

