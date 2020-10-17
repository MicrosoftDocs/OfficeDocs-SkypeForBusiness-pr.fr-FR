---
title: 'Lync Server 2013 : gestion de la configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de390f21c76a9636fc9ba2d6a7d3ee017681b6ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507831"
---
# <a name="configuration-management-in-lync-server-2013"></a>Gestion de la configuration dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-05-15_

La gestion de la configuration est le processus d’enregistrement et de suivi des ressources matérielles et logicielles, ainsi que des informations de configuration système. Il est généralement utilisé pour effectuer le suivi des licences logicielles, maintenir une version matérielle et logicielle standard pour les ordinateurs clients et les serveurs, et définir des normes d’attribution de noms pour les nouveaux ordinateurs. La gestion de la configuration couvre généralement les catégories suivantes :

  - **Matériel**     Cette catégorie effectue le suivi des éléments d’équipement dont l’organisation informatique est propriétaire, où se trouve l’équipement et qui utilise l’équipement. Ces informations permettent à une organisation de planifier et de budgétiser les mises à niveau, de tenir des builds matérielles standard, de générer des rapports sur la valeur des ressources informatiques à des fins de comptabilité et d’empêcher le vol.

  - **Logiciels**     Cette catégorie effectue le suivi des logiciels installés sur chaque ordinateur, des numéros de version et de l’emplacement de stockage des licences. Ces informations permettent de planifier les mises à niveau, de s’assurer que les logiciels sont sous licence et de détecter la présence de logiciels non autorisés (et sans licence).

  - **Builds standard**     Cette catégorie effectue le suivi de la version standard actuelle pour les serveurs et les ordinateurs clients, et indique si les ordinateurs clients et les serveurs satisfont à cette norme. La définition et l’application des builds standard permettent au personnel de prendre en charge, car le personnel est tenu de ne conserver qu’un nombre limité de versions de chaque logiciel.

  - **Mises à jour cumulatives et correctifs**     Cette catégorie effectue le suivi des service packs testés et approuvés pour une utilisation et des ordinateurs mis à jour. Ces informations sont importantes pour réduire le risque de compromission des ordinateurs et pour détecter les utilisateurs qui ont installé des mises à jour non approuvées.

  - **Informations sur**     la configuration du système Cette catégorie effectue le suivi de la fonction d’un système, de l’interaction entre les éléments du système et des processus qui dépendent d’un système qui s’exécute sans problème. Par exemple, un serveur proxy tiers peut être configuré sur un seul serveur. La dépendance du serveur proxy sur ce serveur doit être comprise et les plans d’intervention peuvent être nécessaires en cas de défaillance. Si le serveur proxy peut être configuré pour communiquer également avec un autre serveur frontal, les dépendances et plans d’urgence changent probablement.

<div>

## <a name="implementing-configuration-management"></a>Implémentation de la gestion de la configuration

Une fois que vous avez déterminé les éléments nécessaires à la gestion, implémentez la gestion de la configuration en recueillant les données et les données de rapports. L’approche la plus simple pour les petites organisations est de collecter les données manuellement (nombre et modèle d’ordinateurs clients, de systèmes d’exploitation, de logiciels installés) et de les enregistrer dans un document Office Word ou Office Excel. Pour les systèmes plus volumineux, plus complexes et en constante évolution, la découverte des biens et la collecte d’informations détaillées doivent être automatisées. Déterminez les informations pertinentes pour votre organisation et enregistrez-la dans une base de données.

La base de données de gestion de la configuration est un outil utile pour le personnel de support et la gestion dans les domaines suivants :

  - **Audits**     de sécurité La base de données vous permet d’identifier les serveurs qui exécutent Lync Server et les systèmes d’ordinateurs clients sur lesquels des correctifs logiciels doivent être appliqués ou qui ont manqué l’installation d’un service pack ou les dernières mises à jour antivirus.

  - **Installation**     de logiciels L’identification des versions du logiciel client et leur suivi aideront les administrateurs à planifier les mises à jour de version et les nouvelles installations, ainsi qu’en aidant la documentation et la conformité des licences.

  - **Informations**     de configuration Si vous conservez une liste à jour de tous les paramètres qui ont été modifiés par rapport à leur valeur par défaut, vous pourrez résoudre les problèmes rapidement et plus efficacement.

  - **Planification des mises à niveau**     Si un examen de capacité révèle que de l’espace de stockage supplémentaire est requis sur vos serveurs de bases de données Lync, il est important de savoir si chaque serveur possède un contrôleur RAID interne. Si c’est le cas, est-ce le même modèle ? Ont-ils le même nombre de disques installés ? La base de données de gestion de la configuration indique le type de disque qui peut être installé, le numéro et le chemin de mise à niveau dans chaque cas.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Outils utilisés pour la gestion de la configuration

Il existe de nombreux outils permettant de découvrir, d’auditer et de présenter des biens. Certains de ces outils sont présentés dans cette section.

  - **Scripts**     automatisés Vous pouvez écrire des scripts simples pour signaler des éléments tels que le système d’exploitation, le niveau de Service Pack et indiquer si le logiciel existe sur un ensemble spécifique d’ordinateurs. Vous pouvez écrire ces scripts aux exigences d’une organisation. Toutefois, le nombre requis de scripts et leur complexité peuvent rendre les scripts chers à créer et à gérer.

  - **Outils**     automatisés En fonction de la taille de votre entreprise et des besoins de votre organisation, vous pouvez envisager d’utiliser des outils automatisés. Des outils tels que le gestionnaire de configuration de point de terminaison Microsoft incorporent des modèles de rapport standard (tels que le niveau de Service Pack) et vous permettent également de créer des rapports personnalisés, par exemple, pour une application personnalisée. Le gestionnaire de configuration de point de terminaison Microsoft peut également être utilisé pour signaler les configurations matérielles et logicielles.

</div>

<div>

## <a name="relationship-with-change-management"></a>Relation avec la gestion des modifications

La gestion de la configuration est étroitement liée à la gestion des modifications. La gestion de la configuration identifie le besoin de modification et identifie et enregistre qu’une modification a eu lieu. Par exemple, la base de données de gestion de la configuration peut être utilisée pour identifier les serveurs qui nécessitent un correctif. Gestion des modifications définit ensuite le processus d’application du correctif.

À l’inverse, si une nouvelle mise à jour cumulative est déployée, le processus de gestion des modifications doit fournir ces informations au système de gestion de la configuration. Les outils de gestion de la configuration devront probablement être configurés pour identifier le nouveau logiciel afin qu’ils puissent découvrir et suivre où et quand le logiciel est déployé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

