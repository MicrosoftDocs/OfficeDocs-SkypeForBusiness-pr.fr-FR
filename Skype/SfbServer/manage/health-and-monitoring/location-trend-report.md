---
title: Rapport de tendance des emplacements dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
description: 'Résumé : En savoir plus sur le rapport de tendances d’emplacement dans Skype pour Business Server 2015.'
ms.openlocfilehash: c28a22fdf4122dde45b506e90cf752794deaf781
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="location-trend-report-in-skype-for-business-server-2015"></a>Rapport de tendance des emplacements dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur le rapport de tendances d’emplacement dans Skype pour Business Server 2015.
  
Le rapport de tendance générale des emplacements fournit des informations de tendance sur la qualité des appels pour les emplacements réseau.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, grâce au rapport de tendance générale des emplacements, vous pouvez filtrer les données retournées selon des éléments précis, tels que le type d’accès (à savoir « accès interne » par comparaison à « accès externe ») ou la connexion réseau câblée/sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour ou semaine.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de tendance générale des emplacements. 
  
**Filtres de rapport de tendance emplacement**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 01/01/2011 et une date de fin le 28/02/2011, les données s’affichent pour les jours compris entre le 01/08/2011 12:00 AM et le 01/09/2011 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Type d’accès** <br/> | Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Interne <br/>  Externe <br/> |
|**Type de réseau** <br/> | Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Câblé <br/>  Sans fil <br/> |
|**VPN** <br/> | Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  VPN <br/>  Non-VPN <br/> |
   

