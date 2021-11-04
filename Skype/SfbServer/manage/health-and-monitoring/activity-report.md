---
title: Rapport d’activité de conférence Skype Entreprise Server
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
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Résumé : Découvrez le rapport d’activité de conférence utilisé dans Skype Entreprise Server.'
ms.openlocfilehash: fcbe28d031abc7803cd8b84a67c3baeef42eff08
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774944"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Rapport d’activité de conférence Skype Entreprise Server
 
**Résumé :** Découvrez le rapport d’activité de conférence utilisé dans Skype Entreprise Server.
  
Le rapport des activités de conférence vous permet de répondre facilement à des questions telles que : combien y a-t-il de conférences organisées chaque jour et à quel moments ces conférences sont-elles organisées ? Ce genre d’information n’est pas seulement utile en tant que tel, il peut également permettre de résoudre des problèmes. Par exemple, imaginons que des utilisateurs se plaignent de la lenteur du réseau en milieu de journée. Un coup d’œil rapide aux rapports d’activité de conférence peut suggérer une raison possible : beaucoup plus de conférences sont prévues entre 10 h 00 et 14 h 00, puis à tout autre moment.
  
Si la lenteur du réseau engendre des problèmes, vous pouvez encourager les utilisateurs à replanifier certaines de leurs conférences à un moment de la journée où le trafic est moins important.
  
## <a name="accessing-the-conference-activity-report"></a>Accès au rapport des activités de conférence

Le rapport d’activité de conférence est accessible à partir du rapport de synthèse de conférence dans [Skype Entreprise Server](conference-summary-report.md) en cliquant sur l’une des mesures suivantes :
  
- Nombre total de conférences
    
- Nombre total de participants
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Utilisation optimale du rapport des activités de conférence

Par défaut, le rapport des activités de conférence indique le nombre total de conférences pour une période spécifiée (par exemple, le nombre total de conférences par jour ou le nombre total de conférences par heure pour une journée). Toutefois, vous pouvez choisir d’afficher également le nombre total de participants pour cette même période ou le nombre total de minutes de participant. Pour ce faire, cliquez sur le bouton Afficher/Masquer les paramètres pour afficher les options de filtrage, puis en sélectionner une dans la liste déroulante Établir un rapport par :
  
- Nombre de participants
    
- Minutes de participant
    
- Nombre de conférences
    
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport des activités de conférence.
  
**Filtres du rapport des activités de conférence**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Établir un rapport par** <br/> | Indique les valeurs qu’il convient d’utiliser dans le rapport. Vous pouvez sélectionner l’une des valeurs suivantes : <br/>  Nombre de participants <br/>  Minutes de participant <br/>  Nombre de conférences <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Mesure des conférences par pool

Le tableau qui suit répertorie les informations dans le rapport des activités de conférence pour chaque pool.
  
**Mesure des conférences par pool**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Pool** <br/> |Non  <br/> |Nom du pool de serveurs d’inscriptions ou du serveur Edge utilisés dans la conférence.  <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles la conférence s’est tenue.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de participants, nombre total de minutes par participant ou nombre total de conférences.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Mesure des conférences par type de serveur

Le tableau qui suit répertorie les informations dans le rapport des activités de conférence pour chaque type de serveur.
  
**Mesure des conférences par type de serveur**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type de serveur de conférence** <br/> |Non  <br/> | Type de serveur utilisé dans la conférence, généralement l’un des types suivants : <br/>  Serveur de conférence web <br/>  Service de conférence de messagerie instantanée <br/>  Service de téléconférence <br/>  Serveur de conférence A/V <br/>  Partage d’application <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles la conférence s’est tenue.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de participants, nombre total de minutes par participant ou nombre total de conférences.  <br/> |
   

