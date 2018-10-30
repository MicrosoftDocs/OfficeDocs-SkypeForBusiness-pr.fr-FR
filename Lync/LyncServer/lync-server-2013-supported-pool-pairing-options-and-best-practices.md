---
title: "Opt. de couplage de pools et meill. pratiques prises en ch. pour LS 2013"
TOCTitle: Options de couplage de pools et meilleures pratiques prises en charge
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204697(v=OCS.15)
ms:contentKeyID: 49296339
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Options de couplage de pools et meilleures pratiques prises en charge pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-03-09_

La distance entre deux centres de données devant inclure des pools frontaux jumelés l’un à l’autre n’est pas soumise à des restrictions. Nous vous recommandons d’utiliser deux centres de données qui se trouvent dans la même région du monde, reliés par des connexions haut débit. Il est préférable que les deux centres de données soient assez éloignés pour ne pas subir en même temps une même défaillance.

Il est possible d’avoir deux centres de données situés dans des régions du monde différentes, mais cette situation peut entraîner une perte de données plus importante en raison de la latence de la réplication de données.

Quand vous préparez le jumelage des pools, gardez à l’esprit que seuls les jumelages suivants sont pris en charge :

  - Les pools Enterprise Edition peuvent uniquement être jumelés avec d’autres pools Enterprise Edition. De même, les pools Standard Edition peuvent uniquement être jumelés avec d’autres pools Standard Edition.

  - Les pools physiques peuvent uniquement être jumelés avec d’autres pools physiques. De même, les pools virtuels peuvent uniquement être jumelés avec d’autres pools virtuels.

Ni le générateur de topologie, ni la validation des topologies n’empêcheront le jumelage de deux pools qui ne suit pas ces recommandations. Par exemple, le générateur de topologie vous permet de jumeler un pool Enterprise Edition avec un pool Standard Edition. Cependant, ces types de jumelages ne sont pas pris en charge.

Chaque pool d’un jumelage doit être capable de traiter les demandes de tous les utilisateurs des deux pools en cas d’incident.

Si vous jumelez des pools Enterprise Edition, vous pouvez également implémenter une disponibilité importante sur les serveurs principaux, mais pour le jumelage des pools Standard Edition, seules les mesures de récupération d’urgence sont disponibles.

