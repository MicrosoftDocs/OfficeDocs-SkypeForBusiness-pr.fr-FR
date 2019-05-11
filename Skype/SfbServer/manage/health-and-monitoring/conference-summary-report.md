---
title: Rapport de synthèse conférence dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Résumé : Découvrez le rapport de synthèse de conférence dans Skype pour Business Server.'
ms.openlocfilehash: 8e584b8ca8a7ca08fe0de23d21d4a5608c1f828c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926654"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Rapport de synthèse conférence dans Skype pour Business Server
 
**Résumé :** Obtenir des informations sur le rapport de synthèse de conférence dans Skype pour Business Server.
  
Le rapport de synthèse de conférence fournit une vue d’ensemble de vos sessions de conférence en ligne. En général, une conférence implique plus de 2 les utilisateurs et requiert l’utilisation des services de conférence. Par comparaison, une session d’égal à égal implique simplement 2 les utilisateurs en général et ne nécessite pas l’utilisation de Skype pour les services de conférence Business Server. Activités d’égal à égal sont signalées dans le [rapport de synthèse de l’activité d’égal à égal dans Skype pour Business Server](peer-to-peer-activity-summary-report.md).
  
Le rapport de synthèse de conférence non seulement vous indique le nombre de conférences organisée pendant une période donnée (toutes les heures, tous les jours, toutes les semaines, tous les mois), mais vous indique également le nombre total de personnes qui a participé à ces conférences et le nombre total de conférence uniques organisateurs.
  
Un organisateur « unique » est toute personne qui planifie une conférence au moins un. Par exemple, si Pilar Ackerman planifie une conférence, elle compte comme un organisateur unique. Si Ken Myer planifie 148 conférences, il compte aussi comme un organisateur unique. Le tableau suivant répertorie 8 conférences planifiées, mais avec seulement trois organisateurs uniques (Ken Myer, Pilar Ackerman et David Ahs).
  
|**Organisateur de la conférence**|**Date de la conférence**|
|:-----|:-----|
|Ken Myer  <br/> |07/07/2015 10:00  <br/> |
|David Ahs  <br/> |07/07/2015 10:00  <br/> |
|Ken Myer  <br/> |07/07/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 11:00  <br/> |
|Ken Myer  <br/> |07/07/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 14:00  <br/> |
|Ken Myer  <br/> |02/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |02/07/2015 10:00  <br/> |
   
Le rapport de synthèse de conférence indique également le nombre de conférences incluant l’audio et/ou la vidéo.
  
## <a name="accessing-the-conference-summary-report"></a>Accès au rapport de synthèse de conférence

Le rapport de synthèse de conférence est accessible depuis la page d’accueil Rapports de surveillance. Vous pouvez accéder au rapport des activités de conférence en cliquant sur l’une ou l’autre des mesures suivantes :
  
- Nombre total de conférences
    
- Nombre total de participants
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Exploiter au mieux le rapport de synthèse de conférence

Vous trouverez les valeurs totales pour la plupart des mesures utilisés dans le rapport de synthèse de conférence au bas du rapport ; Faites défiler jusqu'à voir valeurs telles que le nombre total de conférences organisées pendant la période spécifiée et le nombre total de personnes ayant participé à celles-ci. Une mesure qui n’est pas total en bas de l’état est organisateurs de conférence uniques Total. Pourquoi ? Voici une raison. Supposons que vous cherchez à la valeur d’un mois de données. Le jour 1, vous avez 34 organisateurs de conférence uniques ; le jour 2, vous avez 27 organisateurs de conférence uniques. Que signifie que vous aviez 61 organisateurs de conférence uniques pour ces deux jours ? Pas nécessairement. Après tout, toutes les 27 personnes qui a organisé conférences jour 2 peuvent être entre les 34 personnes qui a organisé conférences le jour 1. Par exemple, dans ce rapport simple, notez que Ken Myer et Pilar Ackerman planifiées conférences à la fois sur 7/7/2015 et sur 7/2/2015 :
  
|**Organisateur de la conférence**|**Date de la conférence**|
|:-----|:-----|
|Ken Myer  <br/> |07/07/2015 10:00  <br/> |
|David Ahs  <br/> |07/07/2015 10:00  <br/> |
|Ken Myer  <br/> |07/07/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 11:00  <br/> |
|Ken Myer  <br/> |07/07/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 14:00  <br/> |
|Ken Myer  <br/> |02/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |02/07/2015 10:00  <br/> |
   
Pour vous faire une meilleure idée du nombre total d’utilisateurs uniques qui ont organisé des conférences, modifiez votre intervalle de temps. Par exemple, au lieu d’examiner les données par mois, examinez-les par jour.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le Rapport de synthèse de conférence vous permet de choisir le type de groupement des données. Dans le cas présent, les conférences sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de conférence.
  
**Filtres du rapport de synthèse de conférence**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau ci-dessous contient les informations fournies par le rapport de synthèse de conférence.
  
**Mesures du rapport de synthèse de conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Jour** <br/> **Toutes les semaines** <br/> **Mois** <br/> |Non  <br/> |Indique l’intervalle de temps sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07/07/2015, vous disposez de l’affichage heure par heure de l’activité d’inscription de l’utilisateur à cette date.  <br/> |
|**Nombre total de conférences** <br/> |Non  <br/> |Nombre total de conférences (de quelque type que ce soit) qui se sont tenues. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport des activités de conférence pour la période sélectionnée.  <br/> |
|**Nombre total de participants** <br/> |Non  <br/> |Nombre total de personnes ayant participé aux conférences. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport des activités de conférence pour la période sélectionnée.  <br/> |
|**Nombre moyen de participants par conférence** <br/> |Non  <br/> |Nombre moyen de personnes ayant assisté à une conférence donnée. Valeur obtenue en divisant le nombre total de conférences par le nombre total de participants.  <br/> |
|**Nombre total de conférences A/V** <br/> |Non  <br/> |Nombre total de conférences ayant fait usage de son ou de vidéo.  <br/> |
|**Nombre total de minutes par conférence A/V** <br/> |Non  <br/> |Nombre total de minutes consacrées à la conférence audio/vidéo.  <br/> A Total / mesure minutes de conférence V répertorie tous les types de conférence audio/vidéo, notamment : A / vidéoconférences ; Conférences par messagerie instantanée ; application partage des conférences ; conférences de données ; et de conférences PSTN.  <br/> |
|**Nombre total de minutes par participant à la conférence A/V** <br/> |Non  <br/> |Nombre total de minutes consacrées par les participants à la conférence audio/vidéo. Supposons par exemple, qu’un utilisateur passe 5 minutes dans une conférence audio/vidéo et qu’un deuxième utilisateur y passe 3 minutes, nous obtenons un total de 8 minutes de participant.  <br/> |
|**Nombre moyen de minutes par conférence A/V** <br/> |Non  <br/> |Nombre de minutes moyen par conférence audio/vidéo.  <br/> |
|**Nombre total d’organisateurs uniques de conférences** <br/> |Non  <br/> |Nombre total d’utilisateurs ayant organisé au moins une conférence. Les utilisateurs ayant organisé plusieurs conférences sont comptabilisés comme des organisateurs uniques, à l’instar de ceux qui n’en ont organisées qu’une seule.  <br/> |
|**Nombre total de messages de conférence** <br/> |Non  <br/> |Nombre total de messages instantanés envoyés au cours des conférences.  <br/> |
   

