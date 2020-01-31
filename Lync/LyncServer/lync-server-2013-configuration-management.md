---
title: 'Lync Server 2013 : gestion de la configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb652485b03bcaee5e63bc4fc23d25fd5df958bd
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a>Gestion de la configuration dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-05-15_

La gestion de la configuration est le processus d’enregistrement et de suivi des ressources matérielles et logicielles, ainsi que des informations sur la configuration du système. Il est généralement utilisé pour effectuer le suivi des licences logicielles, de mettre à jour une build matérielle et logicielle standard pour les ordinateurs et serveurs clients et de définir des normes d’appellation pour les nouveaux ordinateurs. La gestion de la configuration couvre généralement les catégories suivantes :

  - **Matériel**   cette catégorie effectue le suivi des éléments d’un équipement dont dispose l’organisation informatique, l’emplacement de l’équipement et qui utilise des équipements. Grâce à ces informations, une organisation est en mesure de planifier et de budgétiser les mises à jour, de mettre à jour les builds matérielles standard, de signaler la valeur des ressources informatiques à des fins comptables et d’éviter le vol.

  - **Logiciel**   cette catégorie effectue le suivi des logiciels installés sur chaque ordinateur, des numéros de version et de l’emplacement des licences. Ces informations permettent de planifier les mises à niveau, de garantir que le logiciel est concédé sous licence et de détecter la présence de logiciels non autorisés (et sans licence).

  - **Builds standard cette**   catégorie effectue le suivi de la build standard actuelle pour les ordinateurs et serveurs clients, et si les ordinateurs et serveurs clients répondent à cette norme. La définition et l’application des builds standard permettent de soutenir le personnel, car le personnel est tenu de ne conserver qu’un nombre limité de versions de chaque logiciel.

  - **Mises à jour et Hotfix cumulés**   cette catégorie suit les service packs testés et approuvés pour une utilisation et les ordinateurs à mettre à jour. Ces informations sont importantes pour réduire le risque d’intrusion sur des ordinateurs et de détecter les utilisateurs qui ont installé des mises à jour non approuvées.

  - **Informations sur**   la configuration du système cette catégorie effectue le suivi de la fonction d’un système, l’interaction entre les éléments système et les processus qui dépendent d’un système qui s’exécute de façon fluide. Par exemple, un serveur proxy tiers est configuré sur un serveur unique. La dépendance du serveur proxy sur ce serveur doit être comprise et les plans d’urgence peuvent être requis en cas d’échec. Si le serveur proxy peut être configuré pour communiquer avec un autre serveur frontal, les dépendances et les plans d’urgence seront probablement modifiés.

<div>

## <a name="implementing-configuration-management"></a>Mise en œuvre de la gestion de la configuration

Lorsque vous déterminez les éléments qui doivent être gérés, implémentez la gestion de la configuration en collectant des données et en rapportant des données. Pour les petites entreprises, l’approche la plus simple consiste à collecter les données manuellement (nombre et modèle d’ordinateurs clients, de systèmes d’exploitation, de logiciels installés) et de les enregistrer dans un document Office Word ou Office Excel. Pour les systèmes plus volumineux, plus complexes et en perpétuelle évolution, la découverte des ressources et la collecte des informations détaillées doit être automatisée. Déterminez les informations pertinentes pour votre organisation et enregistrez-les dans une base de données.

La base de données de gestion de la configuration est un outil utile pour le personnel d’assistance et la gestion des domaines suivants :

  - **Audits de sécurité**   la base de données vous permet d’identifier les serveurs exécutant Lync Server et les systèmes d’ordinateur client pour lesquels des correctifs ont été appliqués ou qui n’ont pas pu installer un service pack ou les dernières mises à jour antivirus.

  - **L’installation**   logicielle identifiant les versions des logiciels clients et en assurer le suivi permettra aux administrateurs de planifier les mises à jour de la version ainsi que de nouvelles installations, et en vous aidant de la documentation et de la conformité.

  - **Informations de configuration**   si vous conservez une liste à jour de tous les paramètres qui ont été modifiés par défaut, vous serez en mesure de résoudre les problèmes de manière rapide et plus efficace.

  - **Planification des mises à jour**   si un avis de capacité révèle que de l’espace de stockage supplémentaire est requis sur les serveurs de base de données Lync, il est important de savoir si chaque serveur possède un contrôleur RAID interne. Si tel est le cas, sont-ils le même modèle ? Est-ce que le nombre de disques est déjà installé ? La base de données de gestion de la configuration indique le type de disque qui peut être installé, le numéro et le chemin de mise à niveau dans chaque cas.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Outils utilisés pour la gestion de la configuration

De nombreux outils permettent de détecter, d’auditer et de signaler des ressources. Certains de ces outils sont abordés dans cette section.

  - **Scripts automatisés**   vous pouvez écrire des scripts simples pour signaler des éléments tels que le système d’exploitation, le niveau du Service Pack et la présence de logiciels sur un ensemble spécifique d’ordinateurs. Vous pouvez écrire ces scripts dans la configuration requise exacte d’une organisation. Toutefois, le nombre requis de scripts et leur complexité peuvent compliquer la création et la gestion des scripts.

  - **Outils automatisés**   en fonction de la taille de votre entreprise et des besoins de votre organisation, vous pouvez envisager d’utiliser des outils automatisés. Les outils tels que Microsoft Endpoint Configuration Manager contiennent des modèles de rapports standard (par exemple, le niveau de Service Pack) et vous permettent également de créer des rapports personnalisés, par exemple pour une application personnalisée. Le gestionnaire de configuration de point de terminaison Microsoft peut également être utilisé pour signaler des configurations matérielle et logicielle.

</div>

<div>

## <a name="relationship-with-change-management"></a>Relation avec la gestion des modifications

La gestion de la configuration est étroitement liée à la gestion des modifications. La gestion de la configuration identifie le besoin de modifier et d’identifier les modifications apportées aux enregistrements. Par exemple, la base de données de gestion de la configuration peut être utilisée pour identifier les serveurs qui nécessitent un correctif. La gestion des modifications définit alors le processus d’application du correctif.

À l’inverse, si une nouvelle mise à jour cumulative est déployée, le processus de gestion des modifications doit fournir ces informations au système de gestion de la configuration. Il est probable que les outils de gestion de la configuration doivent être configurés pour identifier le nouveau logiciel de sorte qu’ils puissent détecter et suivre l’emplacement et le moment de déploiement du logiciel.

</div>

</div>

<span> </span>

</div>

</div>

</div>

