---
title: Test de l’évolutivité de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b23bd731e123c8dba78c3919f9f2a1ff1a6fd1cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Test de l’extensibilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Lync Server 2013 fournit l’infrastructure de serveur pour toutes les communications Lync Server en temps réel, y compris la messagerie instantanée et la présence, les conférences et voix entreprise. Cela inclut toutes les fonctionnalités qui utilisent les ressources matérielles d’un pool Lync Server 2013 et, par conséquent, influent sur les performances et l’envergure. Selon les organisations, les fonctionnalités ne sont pas toutes utilisées de la même façon.

À titre d’exemple, certaines organisations ont très souvent recours à la vidéo lors des conférences alors que d’autres l’utilisent peu ou pas du tout. De la même façon, certaines organisations préfèrent le partage de présentations PowerPoint au partage d’application (ou inversement). Les organisations qui déploient voix entreprise peuvent ou non utiliser l’application Response Group de manière intensive. La plupart des organisations déploient des serveurs de surveillance, mais pas un grand nombre d’entre elles déploient des serveurs d’archivage. Par ailleurs, toutes les organisations ne disposent pas d’infrastructures identiques, tant sur le plan des capacités matérielles ou réseau que du nombre et de la taille des pools déployés. La diversité des fonctionnalités et infrastructures déployées complique les tests d’extensibilité, car il est impossible de simuler toutes les combinaisons possibles de fonctionnalités et d’infrastructures.

Pour déterminer la prise en charge de l’extensibilité pour Lync Server, nous procédons à des tests à l’aide de toutes les fonctionnalités Lync Server simultanément, en fonction d’un modèle d’utilisation moyen (modèle utilisateur). Pour déterminer le modèle utilisateur approprié pour les charges de travail Lync Server, nous analysons de nombreux points de données, notamment les enquêtes des clients, les commentaires du programme d’amélioration de l’expérience utilisateur de Microsoft, les données d’utilisation de Lync Server du service informatique interne de Microsoft, et les données extraites de notre service Live Meeting. Dans de nombreux cas, le modèle utilisateur prévoit des charges de travail plus lourdes afin de laisser une marge de manœuvre confortable pour l’organisation.

Dans nos tests d’évolutivité, nous avons configuré les pools Lync Server 2013 conformément aux spécifications matérielles et logicielles recommandées, notamment les composants d’infrastructure, tels que les services de domaine Active Directory, les programmes d’équilibrage de la charge matérielle et les pare-feu. Nous configurerons les environnements Lync Server aussi étroitement que possible dans des environnements réels standard. Nous utilisons ensuite l’outil stress and performance de Lync Server 2013 pour simuler le chargement de Lync Server 2013 (en fonction de notre modèle utilisateur). .

Nous effectuons plusieurs phases de tests d’extensibilité (sur plusieurs cycles de test de trois semaines chacun). Nous nous appuyons sur les résultats de l’ensemble des tests pour mieux régler les performances et vérifier la prise en charge des valeurs d’extensibilité dans notre modèle utilisateur.

</div>

<span> </span>

</div>

</div>

</div>

