---
title: Vue d’ensemble de la conférence Web Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6287b5edd711df845b862b49bc15adb8405e8587
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535361"
---
# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Vue d’ensemble de la conférence Web dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

La conférence web permet aux utilisateurs de partager des documents, tels que des présentations PowerPoint, et de collaborer dessus au cours de leurs conférences. En outre, les utilisateurs peuvent partager tout ou partie de leur Bureau en temps réel, comme si les participants à la conférence se trouvaient autour de la même table de réunion.

<div>

## <a name="whiteboard-and-annotations"></a>Tableau blanc et annotations

Un tableau blanc est une surface vierge que vous pouvez utiliser à des fins de collaboration, avec du texte, de l’encre, des dessins et des images. Tous les participants à une réunion peuvent voir les annotations qui y sont ajoutées. La fonctionnalité de tableau blanc favorise la collaboration en permettant aux participants à une réunion d’échanger des idées, de débattre, de prendre des notes, etc.

</div>

<div>

## <a name="polling"></a>Interrogation

La fonctionnalité d’interrogation favorise la collaboration en permettant aux présentateurs de déterminer rapidement les préférences des participants. Au cours des réunions et des conversations en ligne, les présentateurs peuvent avoir recours à l’interrogation pour recueillir des réponses anonymes des participants. Tous les présentateurs peuvent voir les résultats et choisir soit de les montrer à tous les participants, soit de les masquer.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Partage d’application et partage de Bureau

Au cours d’une conférence, vous pouvez partager votre ordinateur de bureau, une application individuelle ou des moniteurs individuels dans un environnement à plusieurs moniteurs. Outre la possibilité de consulter le contenu, les autres participants de la conférence peuvent aussi demander à prendre le contrôle de votre écran et, moyennant votre autorisation, d’interagir avec le contenu (défilement, modification, etc).

<div>


> [!NOTE]  
> Les participants qui agissent en tant que spectateurs de la conférence peuvent aussi décider de prendre le contrôle et de partager du contenu au cours de la réunion.



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>Partage de PowerPoint

Dans Lync 2010, les présentations PowerPoint ont été visualisées de deux manières. Pour les utilisateurs de Lync 2010, les présentations PowerPoint étaient affichées au format PowerPoint 97-2003 et affichaient une copie incorporée de la visionneuse PowerPoint. Pour les utilisateurs de Lync Web App, les présentations PowerPoint ont été converties en fichiers HTML dynamiques, puis visualisées à l’aide d’une combinaison de ces fichiers DHTML personnalisés et de Silverlight. Bien que cette approche s'avère généralement efficace, elle comporte certaines limitations :

  - La visionneuse PowerPoint incorporée (qui fournit l’expérience de visualisation optimale) n’est disponible que sur la plateforme Windows.

  - De nombreux appareils mobiles (y compris certains des téléphones mobiles les plus populaires) ne prennent pas en charge Silverlight.

  - La visionneuse PowerPoint et l’approche DHTML/Silverlight ne prennent pas en charge toutes les fonctionnalités (telles que les transitions de diapositives et la vidéo incorporée) qui se trouvent dans les dernières éditions de PowerPoint.

Pour vous aider à résoudre ces problèmes et à améliorer l’expérience globale des utilisateurs présentant ou affichant des présentations PowerPoint, Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer les présentations PowerPoint. Voici quelques-uns des avantages offerts par cette nouvelle approche :

  - Une résolution d’affichage supérieure et une meilleure prise en charge des fonctionnalités de PowerPoint, telles que les animations, les transitions de diapositives et la vidéo incorporée.

  - Des présentations accessibles à un plus grand nombre d’appareils mobiles. C’est parce que Lync Server 2013 utilise le DHTML et le JavaScript standard pour diffuser des présentations PowerPoint au lieu de DHTML et Silverlight personnalisés.

  - Possibilité pour les utilisateurs disposant des privilèges appropriés de parcourir librement une présentation PowerPoint pendant son exécution. Par exemple, pendant que Ken Myer présente son diaporama, Pilar Ackerman peut examiner la diapositive de son choix sans perturber la présentation de Ken.

</div>

</div>

<span> </span>

</div>

</div>

</div>

