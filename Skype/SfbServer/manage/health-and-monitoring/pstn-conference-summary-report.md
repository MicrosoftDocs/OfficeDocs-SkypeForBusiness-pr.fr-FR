---
title: Rapport de synthèse des conférences RTC dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Résumé : en savoir plus sur le rapport de synthèse des conférences RTC dans Skype entreprise Server.'
ms.openlocfilehash: c0ecb9ae2a5630a8d68b9d22892890617127826a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992159"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Rapport de synthèse des conférences RTC dans Skype entreprise Server
 
**Résumé :** En savoir plus sur le rapport synthèse des conférences RTC dans Skype entreprise Server.
  
Dans Skype entreprise Server, une conférence RTC est une conférence dans laquelle au moins un participant compose un numéro à l’aide d’un téléphone commuté (réseau téléphonique public commuté). (Un téléphone RTC est un téléphone mobile, un téléphone mobile ou un autre téléphone qui n’utilise pas le protocole voix sur IP.) Même s’il est appelé conférences RTC dans les rapports de surveillance, ces conférences peuvent être plus fréquemment appelées conférences rendez-vous.
  
Le rapport de synthèse de conférence RTC fournit des informations sur toutes les conférences RTC qui ont lieu au sein de votre organisation (c’est-à-dire, toutes les conférences comportant au moins un utilisateur connecté). Ce rapport comprend des informations sur le nombre total de conférences RTC, le nombre total de personnes ayant participé à ces conférences, et, peut-être plus important, le nombre total d’utilisateurs connectés (la mesure Nombre total de participants RTC).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Accès au rapport de synthèse de conférence RTC

Le rapport de synthèse de conférence RTC est accessible uniquement à partir de la page d’accueil Rapports de surveillance. Ce rapport n’est lié à aucun autre rapport. Vous ne pouvez pas obtenir d’informations détaillées sur les appels pour une conférence RTC, en partie parce que les points de terminaison individuels sont responsables de l’envoi de ces informations. Les téléphones RTC ne sont pas capables d’effectuer le suivi ou d’envoyer des informations détaillées sur les appels.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Utilisation efficace du rapport de synthèse de conférence RTC

Pour déterminer le pourcentage de toutes vos conférences qui incluent des utilisateurs rendez-vous, comparez la valeur de la métrique du total des conférences RTC à la métrique du total de conférences trouvée sur le [rapport synthèse de la Conférence dans Skype entreprise Server](conference-summary-report.md).
  
Si les conférences RTC que vous vous attendiez à voir ne s’affichent pas, n’oubliez pas que la possibilité d’organiser une conférence qui autorise les utilisateurs connectés dépend de la stratégie de conférence affectée à un utilisateur : si peu d’utilisateurs sont autorisés à organiser des conférences RTC, vous verrez peu de conférences RTC. Vous pouvez rapidement vérifier les stratégies de conférences (le cas échéant) permettre aux utilisateurs de planifier des conférences RTC en exécutant la commande suivante à partir de Skype entreprise Server Management Shell :
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Des données semblables à ceci sont renvoyées :
  
<pre>
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True
</pre>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de synthèse des conférences RTC vous permet de choisir la façon dont les données doivent être groupées. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des conférences RTC.
  
**Filtres du rapport de synthèse des conférences RTC**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des conférences RTC
  
**Mesures du rapport de synthèse des conférences RTC**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Jour** <br/> **Toutes les semaines** <br/> **Mois** <br/> |Non  <br/> |Indique l’intervalle de temps sélectionné. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07/07/2015, une répartition par jour de l’activité d’enregistrement utilisateur est affichée pour cette date.  <br/> |
|**Nombre total de conférences RTC** <br/> |Non  <br/> |Nombre total de conférences ayant autorisé l’accès de rendez-vous.  <br/> |
|**Nombre total de participants** <br/> |Non  <br/> |Nombre total de personnes ayant participé à des conférences ayant autorisé l’accès de rendez-vous.  <br/> |
|**Nombre total de minutes par conférence A/V** <br/> |Non  <br/> |Durée totale de conférence audio/vidéo.  <br/> |
|**Nombre total de minutes par participant à la conférence A/V** <br/> |Non  <br/> |Durée totale de participants audio/vidéo. Par exemple, si un participant a passé cinq minutes dans une conférence A/V et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants de conférences A/V sera de huit minutes.  <br/> |
|**Nombre total de participants RTC** <br/> |Non  <br/> |Nombre total d’utilisateurs qui se sont connectés à des conférences ayant autorisé l’accès de rendez-vous.  <br/> |
|**Nombre total de minutes par participant RTC** <br/> |Non  <br/> |Durée totale de conférence passée par les utilisateurs de rendez-vous. Par exemple, si un participant de rendez-vous a passé cinq minutes dans une conférence et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants RTC sera de huit minutes.  <br/> |
|**Organisateurs de conférence uniques** <br/> |Non  <br/> |Nombre total d’utilisateurs qui ont organisé au moins une conférence ayant autorisé l’accès de rendez-vous. Les utilisateurs qui ont organisé plusieurs conférences sont comptabilisés comme un organisateur unique, tout comme les utilisateurs ayant organisé une seule conférence.  <br/> |
   

