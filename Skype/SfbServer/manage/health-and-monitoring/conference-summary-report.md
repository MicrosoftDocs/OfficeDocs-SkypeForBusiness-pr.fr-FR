---
title: Rapport de synthèse de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Résumé : Découvrez le rapport de synthèse de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 8ad8bc35a014efd1cb84979f7cc05d75c3691673
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751753"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Rapport de synthèse de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de synthèse de conférence dans Skype Entreprise Server.
  
Le rapport de synthèse de conférence fournit une vue d’ensemble de vos sessions de conférence en ligne. Une conférence implique généralement plus de 2 utilisateurs et nécessite l’utilisation des services de conférence. En comparaison, une session d’égal à égal n’implique généralement que 2 utilisateurs et ne nécessite pas l’utilisation Skype Entreprise Server services de conférence. Les activités d’égal à égal sont signalées dans le rapport de synthèse des activités P22 dans [Skype Entreprise Server](peer-to-peer-activity-summary-report.md).
  
Le rapport de synthèse de conférence vous indique non seulement le nombre de conférences qui ont eu lieu pendant une période donnée (toutes les heures, tous les jours, toutes les semaines, tous les mois), mais également le nombre total de personnes qui ont participé à ces conférences et le nombre total d’organisateurs de conférences uniques.
  
Un organisateur « unique » est toute personne qui planifiera au moins une conférence. Par exemple, si Pilar Ackerman planifie une conférence, elle compte comme un organisateur unique. Si Ken Myer planifie 148 conférences, il compte aussi comme un organisateur unique. Par exemple, le tableau suivant montre 8 conférences programmées, mais seulement trois organisateurs uniques (Ken Myer, Pilar Ackerman et David Ahs).
  
|**Organisateur de la conférence**|**Date de la conférence**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 10:00  <br/> |
|David Ahs  <br/> |7/7/2015 10:00  <br/> |
|Ken Myer  <br/> |7/7/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 11:00  <br/> |
|Ken Myer  <br/> |7/7/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 14:00  <br/> |
|Ken Myer  <br/> |2/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |2/07/2015 10:00  <br/> |
   
Le rapport de synthèse de conférence indique également le nombre de conférences incluant l’audio et/ou la vidéo.
  
## <a name="accessing-the-conference-summary-report"></a>Accès au rapport de synthèse de conférence

Le rapport de synthèse de conférence est accessible depuis la page d’accueil Rapports de surveillance. Vous pouvez accéder au rapport des activités de conférence en cliquant sur l’une ou l’autre des mesures suivantes :
  
- Nombre total de conférences
    
- Nombre total de participants
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Exploiter au mieux le rapport de synthèse de conférence

Les valeurs totales de la plupart des mesures utilisées dans le rapport de synthèse de conférence se trouvent en bas du rapport . faites défiler vers le bas pour voir des valeurs telles que le nombre total de conférences tenues pendant la période spécifiée et le nombre total de personnes qui ont participé à ces conférences. Une mesure qui n’est pas totalée en bas du rapport est le nombre total d’organisateurs de conférence uniques. Pourquoi ? Voici une raison. Supposons que vous regardiez la valeur d’un mois de données. Le jour 1, vous avez 34 organisateurs de conférence uniques ; le jour 2, vous avez eu 27 organisateurs de conférence uniques. Cela signifie-t-il que vous avez 61 organisateurs de conférence uniques pour ces deux jours ? Pas nécessairement. Après tout, les 27 personnes qui ont organisé des conférences le jour 2 peuvent faire partie des 34 personnes qui ont organisé des conférences le jour 1. Par exemple, dans ce rapport simple, notez que Ken Myer et Pilar Ackerman ont programmé des conférences à la fois le 07/07/2015 et le 02/07/2015 :
  
|**Organisateur de la conférence**|**Date de la conférence**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 10:00  <br/> |
|David Ahs  <br/> |7/7/2015 10:00  <br/> |
|Ken Myer  <br/> |7/7/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 11:00  <br/> |
|Ken Myer  <br/> |7/7/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 14:00  <br/> |
|Ken Myer  <br/> |2/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |2/07/2015 10:00  <br/> |
   
Pour vous faire une meilleure idée du nombre total d’utilisateurs uniques qui ont organisé des conférences, modifiez votre intervalle de temps. Par exemple, au lieu d’examiner les données par mois, examinez-les par jour.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le Rapport de synthèse de conférence vous permet de choisir le type de groupement des données. Dans le cas présent, les conférences sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de conférence.
  
**Filtres du rapport de synthèse de conférence**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau suivant contient les informations fournies par le rapport de synthèse de conférence.
  
**Mesures du rapport de synthèse de conférence**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Tous les jours** <br/> **Toutes les semaines** <br/> **Mensuelle** <br/> |Non  <br/> |Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07/07/2015, vous voyez une répartition horaire de l’activité d’inscription de l’utilisateur pour cette date.  <br/> |
|**Nombre total de conférences** <br/> |Non  <br/> |Nombre total de conférences (de quelque type que ce soit) qui se sont tenues. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport des activités de conférence pour la période sélectionnée.  <br/> |
|**Nombre total de participants** <br/> |Non  <br/> |Nombre total de personnes ayant participé aux conférences. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport des activités de conférence pour la période sélectionnée.  <br/> |
|**Nombre moyen de participants par conférence** <br/> |Non  <br/> |Nombre moyen de personnes ayant assisté à une conférence donnée. Valeur obtenue en divisant le nombre total de conférences par le nombre total de participants.  <br/> |
|**Nombre total de conférences A/V** <br/> |Non  <br/> |Nombre total de conférences ayant fait usage de son ou de vidéo.  <br/> |
|**Nombre total de minutes par conférence A/V** <br/> |Non  <br/> |Nombre total de minutes consacrées à la conférence audio/vidéo.  <br/> La mesure Nombre total de minutes de conférence A/V récapitule tous les types de conférence audio/vidéo, y compris les conférences A/V ; conférences de messagerie instantanée ; conférences de partage d’application ; conférences de données ; et conférences PSTN.  <br/> |
|**Nombre total de minutes par participant à la conférence A/V** <br/> |Non  <br/> |Nombre total de minutes consacrées par les participants à la conférence audio/vidéo. Supposons par exemple qu’un utilisateur passe 5 minutes dans une conférence audio/vidéo et qu’un deuxième utilisateur y passe 3 minutes, nous obtenons un total de 8 minutes de participant.  <br/> |
|**Nombre moyen de minutes par conférence A/V** <br/> |Non  <br/> |Nombre de minutes moyen par conférence audio/vidéo.  <br/> |
|**Nombre total d’organisateurs uniques de conférences** <br/> |Non  <br/> |Nombre total d’utilisateurs ayant organisé au moins une conférence. Les utilisateurs ayant organisé plusieurs conférences sont comptabilisés comme des organisateurs uniques, à l’instar de ceux qui n’en ont organisées qu’une seule.  <br/> |
|**Nombre total de messages de conférence** <br/> |Non  <br/> |Nombre total de messages instantanés envoyés au cours des conférences.  <br/> |
   

