---
title: Options de jumelage des pools et meilleures pratiques de Lync Server 2013 prises en charge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c73108f832aaa10b0539aa6fd56b4f4a7bb0cbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Options de jumelage des pools prises en charge et meilleures pratiques pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-03-09_

La distance entre deux centres de données devant inclure des pools frontaux jumelés l’un à l’autre n’est pas soumise à des restrictions. Nous vous recommandons d’utiliser deux centres de données qui se trouvent dans la même région du monde, reliés par des connexions haut débit. Il est préférable que les deux centres de données soient assez éloignés pour ne pas subir en même temps une même défaillance.

Il est possible d’avoir deux centres de données situés dans des régions du monde différentes, mais cette situation peut entraîner une perte de données plus importante en raison de la latence de la réplication de données.

Lorsque vous planifiez le jumelage des pools, gardez à l’esprit que seuls les jumelages suivants sont pris en charge :

  - Les pools Enterprise Edition peuvent uniquement être jumelés avec d’autres pools Enterprise Edition. De même, les pools Standard Edition peuvent uniquement être jumelés avec d’autres pools Standard Edition.

  - Les pools physiques peuvent uniquement être jumelés avec d’autres pools physiques. De même, les pools virtuels peuvent uniquement être jumelés avec d’autres pools virtuels.

  - Les pools associés doivent exécuter le même système d’exploitation.

Ni le Générateur de topologie, ni la validation des topologies n’empêcheront le jumelage de deux pools qui ne suit pas ces recommandations. Par exemple, le Générateur de topologie vous permet de jumeler un pool Enterprise Edition avec un pool Standard Edition. Toutefois, ces types de jumelage ne sont pas pris en charge.

Chaque pool d’un jumelage doit être capable de traiter les demandes de tous les utilisateurs des deux pools en cas d’incident.

Si vous jumelez des pools Enterprise Edition, vous pouvez également implémenter une disponibilité importante sur les serveurs principaux, mais pour le jumelage des pools Standard Edition, seules les mesures de récupération d’urgence sont disponibles.

</div>

<span> </span>

</div>

</div>

</div>

