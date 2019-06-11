---
title: Options de jumelage et meilleures pratiques de Lync Server 2013 prises en charge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Options de jumelage de pool prises en charge et meilleures pratiques pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2017-03-09_

Il n’existe aucune restriction sur la distance entre deux centres de données qui doivent inclure des listes frontales couplées. Nous vous recommandons d’utiliser deux centres de données au sein d’une même région dans le monde, grâce à des liens haut débit. Il est préférable que les deux centres de données soient suffisamment séparés pour éviter une catastrophe unique, en même temps.

Il est possible d’avoir deux centres de données dans les différentes régions du monde, mais peut entraîner une plus grande perte de données en raison d’une latence dans la réplication des données.

Quand vous préparez le jumelage des pools, gardez à l’esprit que seuls les jumelages suivants sont pris en charge :

  - Les pools Enterprise Edition peuvent uniquement être jumelés avec d’autres pools Enterprise Edition. De même, les pools Standard Edition peuvent uniquement être jumelés avec d’autres pools Standard Edition.

  - Les pools physiques peuvent uniquement être jumelés avec d’autres pools physiques. De même, les pools virtuels peuvent uniquement être jumelés avec d’autres pools virtuels.

  - Les pools associés doivent exécuter le même système d’exploitation.

Ni le générateur de topologie, ni la validation des topologies n’empêcheront le jumelage de deux pools qui ne suit pas ces recommandations. Par exemple, le générateur de topologie vous permet de jumeler un pool Enterprise Edition avec un pool Standard Edition. Cependant, ces types de jumelages ne sont pas pris en charge.

Chaque pool d’une paire doit avoir la capacité de desservir tous les utilisateurs des deux pools en cas de sinistre.

Si vous jumelez les pools Enterprise Edition, vous pouvez également implémenter une haute disponibilité sur les serveurs dorsaux, mais pour les paires de pools Standard Edition, seules les mesures de reprise après sinistre sont disponibles.

</div>

<span> </span>

</div>

</div>

</div>

