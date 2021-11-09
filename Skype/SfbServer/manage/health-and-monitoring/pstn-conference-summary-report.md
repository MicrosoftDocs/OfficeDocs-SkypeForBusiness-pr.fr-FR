---
title: Rapport de synthèse de conférence PSTN en Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Résumé : Découvrez le rapport de synthèse des conférences PSTN dans Skype Entreprise Server.'
ms.openlocfilehash: 19038b29f46e33026e3ef865226aa4d087b0a0da
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862291"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Rapport de synthèse de conférence PSTN en Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de synthèse de conférence PSTN dans Skype Entreprise Server.
  
Dans Skype Entreprise Server, une conférence PSTN est une conférence dans laquelle au moins un participant se compose de la partie audio à l’aide d’un téléphone PSTN (réseau téléphonique commuté). (Un téléphone PSTN est une « ligne fixe », un téléphone portable ou tout autre téléphone qui n’utilise pas Voice over IP.) Bien que appelées conférences PSTN dans les rapports de surveillance, ces conférences sont peut-être plus communément appelées conférences d’accès.
  
Le rapport de synthèse de conférence PSTN fournit des informations sur toutes les conférences PSTN qui ont lieu au sein de votre organisation (c’est-à-dire, toutes les conférences comportant au moins un utilisateur connecté). Ce rapport comprend des informations sur le nombre total de conférences PSTN, le nombre total de personnes ayant participé à ces conférences, et, peut-être plus important, le nombre total d’utilisateurs connectés (la mesure Nombre total de participants PSTN).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Accès au rapport de synthèse de conférence PSTN

Le rapport de synthèse de conférence PSTN est accessible uniquement à partir de la page d’accueil Rapports de surveillance. Ce rapport n’est lié à aucun autre rapport. Vous ne pouvez pas obtenir d’informations détaillées sur les appels pour une conférence PSTN, en partie parce que les points de terminaison individuels sont responsables de l’envoi de ces informations. Les téléphones PSTN ne sont pas capables d’effectuer le suivi ou d’envoyer des informations détaillées sur les appels.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Utilisation efficace du rapport de synthèse de conférence PSTN

Pour déterminer le pourcentage de toutes vos conférences qui incluent des utilisateurs de conférences, comparez la valeur de la mesure Nombre total de conférences PSTN à la mesure Nombre total de conférences trouvée dans le rapport de synthèse de conférence dans [Skype Entreprise Server](conference-summary-report.md).
  
Si les conférences PSTN que vous vous attendiez à voir ne s’affichent pas, n’oubliez pas que la possibilité d’organiser une conférence qui autorise les utilisateurs connectés dépend de la stratégie de conférence assignée à un utilisateur : si peu d’utilisateurs sont autorisés à organiser des conférences PSTN, vous verrez peu de conférences PSTN. Vous pouvez rapidement vérifier quelles stratégies de conférence autorisent les utilisateurs à planifier des conférences PSTN en exécutant la commande suivante à partir de l’environnement de ligne de commande Skype Entreprise Server Management Shell :
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Des données semblables à ceci sont alors retournées :
  
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

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de synthèse des conférences PSTN vous permet de choisir la façon dont les données doivent être groupées. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des conférences PSTN.
  
**Filtres du rapport de synthèse des conférences PSTN**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des conférences PSTN
  
**Mesures du rapport de synthèse des conférences PSTN**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Tous les jours** <br/> **Toutes les semaines** <br/> **Mensuelle** <br/> |Non  <br/> |Indique l’intervalle de temps sélectionné. Si applicable, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07/07/2015, vous voyez une répartition horaire de l’activité d’inscription de l’utilisateur pour cette date.  <br/> |
|**Nombre total de conférences PSTN** <br/> |Non  <br/> |Nombre total de conférences ayant autorisé l’accès de rendez-vous.  <br/> |
|**Nombre total de participants** <br/> |Non  <br/> |Nombre total de personnes ayant participé à des conférences ayant autorisé l’accès de rendez-vous.  <br/> |
|**Nombre total de minutes par conférence A/V** <br/> |Non  <br/> |Durée totale de conférence audio/vidéo.  <br/> |
|**Nombre total de minutes par participant à la conférence A/V** <br/> |Non  <br/> |Durée totale de participants audio/vidéo. Par exemple, si un participant a passé cinq minutes dans une conférence A/V et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants de conférences A/V sera de huit minutes.  <br/> |
|**Nombre total de participants PSTN** <br/> |Non  <br/> |Nombre total d’utilisateurs qui se sont connectés à des conférences ayant autorisé l’accès de rendez-vous.  <br/> |
|**Nombre total de minutes par participant PSTN** <br/> |Non  <br/> |Durée totale de conférence passée par les utilisateurs de rendez-vous. Par exemple, si un participant de rendez-vous a passé cinq minutes dans une conférence et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants PSTN sera de huit minutes.  <br/> |
|**Organisateurs de conférence uniques** <br/> |Non  <br/> |Nombre total d’utilisateurs qui ont organisé au moins une conférence ayant autorisé l’accès de rendez-vous. Les utilisateurs qui ont organisé plusieurs conférences sont comptabilisés comme un organisateur unique, tout comme les utilisateurs ayant organisé une seule conférence.  <br/> |
   

