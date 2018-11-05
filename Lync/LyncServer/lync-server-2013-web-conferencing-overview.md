---
title: Vue d’ensemble des conférences web dans Lync Server 2013
TOCTitle: Vue d’ensemble des conférences web dans Lync Server 2013
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425913(v=OCS.15)
ms:contentKeyID: 49297004
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble des conférences web dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-30_

La conférence web permet aux utilisateurs de partager des documents, tels que des présentations PowerPoint, et de collaborer dessus au cours de leurs conférences. En outre, les utilisateurs peuvent partager tout ou partie de leur Bureau en temps réel, comme si les participants à la conférence se trouvaient autour de la même table de réunion.

## Tableau blanc et annotations

Un tableau blanc est une surface vierge que vous pouvez utiliser à des fins de collaboration, avec du texte, de l’encre, des dessins et des images. Tous les participants à une réunion peuvent voir les annotations qui y sont ajoutées. La fonctionnalité de tableau blanc favorise la collaboration en permettant aux participants à une réunion d’échanger des idées, de débattre, de prendre des notes, etc.

## Interrogation

La fonctionnalité d’interrogation favorise la collaboration en permettant aux présentateurs de déterminer rapidement les préférences des participants. Au cours des réunions et des conversations en ligne, les présentateurs peuvent avoir recours à l’interrogation pour recueillir des réponses anonymes des participants. Tous les présentateurs peuvent voir les résultats et choisir soit de les montrer à tous les participants, soit de les masquer.

## Partage d’application et partage de Bureau

Au cours d’une conférence, vous pouvez décider de partager l’intégralité de votre Bureau, une application individuelle ou des moniteurs individuels dans un environnement constitué de plusieurs moniteurs. Outre la possibilité de consulter le contenu, les autres participants de la conférence peuvent aussi demander à prendre le contrôle de votre écran et, moyennant votre autorisation, d’interagir avec le contenu (défilement, modification, etc).

> [!NOTE]  
> Les participants qui agissent en tant que spectateurs de la conférence peuvent aussi décider de prendre le contrôle et de partager du contenu au cours de la réunion.

## Partage de PowerPoint

Dans Lync 2010, il existait deux modes de visualisation des présentations PowerPoint. Pour les utilisateurs qui exécutaient Lync 2010, les présentations PowerPoint étaient affichées au format PowerPoint 97-2003 et visualisées par le biais d’une copie incorporée de la Visionneuse PowerPoint. Pour les utilisateurs qui exécutaient Lync Web App, les présentations PowerPoint étaient d’abord converties en fichiers HTML dynamiques avant d’être affichées en utilisant conjointement ces fichiers DHTML et Silverlight. Bien que généralement efficace, cette approche présentait certaines limites :

  - La Visionneuse PowerPoint incorporée (qui assurait l’expérience de visualisation optimale) est disponible uniquement sur la plateforme Windows.

  - De nombreux appareils mobiles (dont certains téléphones mobiles parmi les plus populaires) ne prennent pas en charge Silverlight.

  - La Visionneuse PowerPoint et l’approche DHTML/Silverlight ne prennent pas en charge toutes les fonctionnalités (telles que les transitions de diapositives et la vidéo incorporée) offertes par les dernières éditions de PowerPoint.

Pour résoudre ces problèmes et améliorer l’expérience générale des utilisateurs présentant ou visionnant des présentations PowerPoint, Lync Server 2013 fait appel à Office Web Apps et à Office Web Apps Server pour gérer les présentations PowerPoint. Voici quelques-uns des avantages offerts par cette nouvelle approche :

  - Une résolution d’affichage supérieure et une meilleure prise en charge des fonctionnalités de PowerPoint, telles que les animations, les transitions de diapositives et la vidéo incorporée.

  - Des présentations accessibles à un plus grand nombre d’appareils mobiles. En effet, pour la diffusion des présentations PowerPoint, Lync Server 2013 a abandonné le DHTML personnalisé et Silverlight au profit des langages DHTML et JavaScript standard.

  - Possibilité pour les utilisateurs disposant des privilèges appropriés de parcourir librement une présentation PowerPoint pendant son exécution. Par exemple, pendant que Ken Myer présente son diaporama, Pilar Ackerman peut examiner la diapositive de son choix sans perturber la présentation de Ken.

