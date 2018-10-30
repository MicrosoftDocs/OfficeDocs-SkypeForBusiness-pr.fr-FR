---
title: "Coloc. de serv. Lync Server 2013 lors d’un dépl. de serv. Standard Edition"
TOCTitle: Colocalisation de serveur lors d’un déploiement de serveur Standard Edition
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398131(v=OCS.15)
ms:contentKeyID: 49296152
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Colocalisation de serveur lors d’un déploiement de serveur Standard Edition pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-01-20_

Cette section décrit les rôles serveur, les bases de données et les partages de fichiers que vous pouvez colocaliser dans un déploiement de serveur Standard Edition Lync Server 2013 .

## Rôles serveur

Dans Lync Server 2013, le service de conférence A/V, le service de médiation, la surveillance et l’archivage sont colocalisés sur le serveur Standard Edition, mais ils doivent être configurés pour être activés. Vous pouvez également choisir de déployer le service de médiation sur des serveurs distincts.

Vous pouvez colocaliser un serveur d’applications approuvées avec un serveur Standard Edition.

Les rôles serveur suivants doivent être individuellement déployés sur un ordinateur distinct :

  - directeur

  - serveur Edge

  - Serveur de médiation (s’il n’est pas colocalisé avec le serveur Standard Edition)

  - Office Web Apps Server

## Bases de données

Par défaut, la base de données principale SQL Server Express est colocalisée sur le serveur Standard Edition. Vous ne pouvez pas la déplacer sur un autre ordinateur. À une exception près, vous ne pouvez pas colocaliser d’autres bases de données sur le serveur Standard Edition. Si vous choisissez de déployer serveur de conversations permanentes sur un serveur Standard Edition, vous pouvez colocaliser la base de données de conversation permanente et la base de données de conformité de conversation permanente sur le même serveur Standard Edition.

Vous pouvez colocaliser chacune des bases de données suivantes sur un serveur de base de données unique :

  - base de données de surveillance

  - base de données d’archivage

  - Une base de données principale pour un pool frontal Enterprise Edition

Vous pouvez colocaliser une base de données ou l’ensemble de ces bases de données dans une instance SQL unique ou utiliser une instance SQL distincte pour chaque base de données, en tenant compte des limitations suivantes :

  - Chaque instance SQL peut ne contenir qu’une seule base de données principale (pour un pool frontal Enterprise Edition), une seule base de données de surveillance, une seule base de données d’archivage, une seule base de données de conversation permanente et une seule base de données de conformité de conversation permanente.

  - Le serveur de base de données ne peut pas prendre en charge plus d’un pool frontal Enterprise Edition, un serveur exécutant l’archivage, un serveur exécutant la surveillance, une base de données de conversation permanente unique et une base de données de conformité de conversation permanente mais il peut prendre en charge un de chaque, que les bases de données utilisent la même instance de SQL Server ou des instances de SQL Server distinctes

Vous pouvez colocaliser un partage de fichiers avec les bases de données, comme il est décrit dans la suite de cette section.

> [!NOTE]  
> Dans Lync Server 2013, vous pouvez intégrer le stockage de surveillance et d’archivage au stockage Exchange 2013 pour tout ou partie des utilisateurs de votre déploiement. En revanche, vous ne pouvez pas déployer des serveurs exécutant Lync Server, ni des composants sur les serveurs où se trouve le stockage Exchange.

> [!IMPORTANT]  
> Même si la colocation des bases de données est prise en charge, la taille des bases de données peut augmenter rapidement. Par exemple, lorsque vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données du serveur d’archivage peuvent devenir très importants. Pour cette raison, nous ne recommandons pas de colocaliser plusieurs bases de données, en particulier la base de données d’archivage, la base de données de conversation permanente et la base de données de conformité de conversation permanente avec la base de données principale d’un pool d’entreprise.

## Partages de fichiers

Le partage de fichier peut être un serveur distinct ou être colocalisé sur le même serveur que l’un ou l’ensemble des éléments suivants :

  - Serveur de base de données, dont le serveur principal d’un pool frontal Enterprise Edition

  - base de données d’archivage

  - base de données de surveillance

  - Base de données de conversation permanente

  - Base de données de conformité de conversation permanente

Un partage de fichiers unique peut être utilisé pour plusieurs pools frontaux et serveurs Standard Edition (sur le même site).

> [!NOTE]  
> Dans Lync Server 2013, la surveillance et l’archivage utilisent le partage de fichiers de Lync Server comme serveur Standard Edition.

## Autres composants

Vous ne pouvez pas colocaliser un serveur proxy inverse, qui n’est pas un composant Lync Server 2013. Ce serveur est cependant requis dans votre déploiement si vous souhaitez prendre en charge le partage d’un contenu web pour des utilisateurs fédérés avec n’importe quel rôle serveur Lync Server 2013. Vous pouvez cependant implémenter une prise en charge de proxy inverse pour un déploiement Lync Server 2013 en configurant la prise en charge sur un serveur proxy inverse existant de votre organisation utilisé pour d’autres applications.

Vous ne pouvez pas colocaliser un composant messagerie unifiée Exchange ou un composant SharePoint avec un rôle Lync Server 2013.

