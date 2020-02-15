---
title: 'Lync Server 2013 : validation de la normalisation et du routage des numéros vocaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbc15dc47a7eeee0b7fb4bd49ba5ea2584e94fe7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Validation de la normalisation et du routage des numéros vocaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-19_

La normalisation des numéros et le routage sont très importants pour l’environnement voix entreprise fonctionnel. En particulier lors des migrations de PBX vers un environnement Lync Server autonome, l’une des clés de la migration est de révéler et de documenter toutes les règles de numérotation existantes, et de créer des règles de normalisation appropriées, des stratégies de voix utilisations et itinéraires téléphoniques.

La validation de la normalisation et du routage des nombres est importante non seulement pendant les migrations, mais aussi pendant une opération normale et stable du système.

Nous vous recommandons d’effectuer cette validation tous les jours à l’aide du panneau de configuration Lync Server, en commençant par le développement d’un ensemble robuste de cas de test par rapport à l’ensemble actuel de règles de normalisation publiées dans les paramètres globaux de Lync Server. Ces cas de test doivent être exécutés tous les jours pour mettre en évidence les modifications non souhaitées qui ont été apportées au plan de numérotation.

Le panneau de configuration Lync Server vous permet également de visualiser, de tester, de modifier, d’archiver et de partager des informations de configuration sur le routage des communications vocales et de modifier les règles de normalisation des numéros de voix de l’entreprise, les plans de numérotation, la stratégie de voix et les itinéraires. Il comporte des fonctionnalités supplémentaires permettant d’effectuer les opérations suivantes :

  - L’exportation et l’importation de données de routage des communications vocales entre les systèmes ;

  - Test des modifications de configuration avant leur téléchargement vers un système actif.

  - La création et l’exécution de cas de test de configuration pour garantir la convivialité des données de routage après les avoir modifiées, mais avant de les soumettre à un système déployé.

  - Création et modification des règles de normalisation des numéros, des profils d’emplacement, de la stratégie de voix et des données de routage sans avoir à écrire les expressions régulières nécessaires.

  - Analyse d’un profil d’emplacement pour la compatibilité avec Lync Server Phone Edition.

  - Vous trouverez plus d’informations sur les tests de routage des communications vocales [dans test de routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

<div>

## <a name="see-also"></a>Voir aussi


[Tester le routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

