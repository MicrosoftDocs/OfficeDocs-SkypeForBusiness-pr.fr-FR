---
title: Rapport vocal et vidéo D’égal à égal dans Skype Entreprise Server
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
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Résumé : Découvrez le rapport vocal et vidéo D’égal à égal dans Skype Entreprise Server.'
ms.openlocfilehash: 61065578ea67ba3ec5004d517482c8c449216a0c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836326"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>Rapport vocal et vidéo D’égal à égal dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport vocal et vidéo d’égal à égal dans Skype Entreprise Server.
  
Le rapport vocal et vidéo d’égal-à-égal offre un examen détaillé de la distribution des appels vocaux et vidéo sur une période donnée (par exemple, les appels par heure ou par jour). Il vous offre également la possibilité de voir tous les appels vocaux et vidéo émis, ou de voir uniquement les appels ayant abouti ou échoué. Le rapport fournit les informations d’appels réparties dans les sections suivantes :
  
- Appels par pool
    
- Appels par type d’appel (par exemple, un appel Skype Entreprise un appel Skype Entreprise et un appel Skype Entreprise à une personne sur le réseau PSTN)
    
- Appels par type d’accès (utilisateurs connectés au réseau interne par opposition aux utilisateurs connectés au réseau externe)
    
- Appels par serveur de médiation
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Pour accéder au rapport vocal et vidéo d’égal-à-égal

Vous pouvez accéder au rapport vocal et vidéo d’égal-à-égal en ouvrant simplement le rapport de synthèse d’activité d’égal-à-égal, puis en cliquant sur l’une des mesures suivantes :
  
- Nombre total de sessions d’égal-à-égal
    
- Nombre total de minutes audio d’égal-à-égal
    
- Nombre total de sessions vidéo d’égal-à-égal
    
- Nombre total de minutes vidéo d’égal-à-égal
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Pour une utilisation optimale du rapport vocal et vidéo d’égal-à-égal

Vous pouvez filtrer le rapport vocal et vidéo d’égal-à-égal de différentes manières. Cependant, ces options de filtre sont masquées par défaut. Pour afficher les options de filtre disponibles, cliquez sur le bouton **Afficher/Masquer les paramètres** dans le coin supérieur droit de la fenêtre du rapport.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport vocal et vidéo d’égal à égal.
  
**Filtres du rapport vocal et vidéo d’égal-à-égal**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Type de média** <br/> | Indique le type de média utilisé dans la session. Sélectionnez l’une des options suivantes : <br/>  Les deux <br/>  Audio <br/>  Vidéo <br/> |
|**Distribution des appels** <br/> | Indique la réussite ou l’échec de la session. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Appels ayant abouti <br/>  Appels n’ayant pas abouti <br/> |
|**Établir un rapport par** <br/> | Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes : <br/>  Nombre de sessions <br/>  Minutes d’appel <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Mesures de l’activité vocale et vidéo d’égal à égal par pool

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque pool.
  
**Mesures de l’activité vocale et vidéo d’égal à égal par pool**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Pool** <br/> |Non  <br/> |Nom du pool de serveurs d’inscriptions ou du serveur Edge utilisé pour l’appel.  <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles l’appel s’est produit.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Mesures de l’activité vocale et vidéo d’égal à égal par type d’appel

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque type d’appel émis.
  
**Mesures de l’activité vocale et vidéo d’égal à égal par type d’appel**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’appel** <br/> |Non  <br/> | Indique le type d’appel émis. Les valeurs correspondent à l’une des options suivantes : <br/>  UC-à-UC <br/>  UC à PSTN <br/>  PSTN-à-UC <br/>  PSTN à PSTN <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles l’appel s’est produit.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Mesures de l’activité vocale et vidéo d’égal à égal par type d’accès

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque type d’accès réseau.
  
**Mesures de l’activité vocale et vidéo d’égal à égal par type d’accès**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’activité** <br/> |Non  <br/> | Indique si les clients étaient connectés au réseau interne ou au réseau externe au moment de passer l’appel. Les valeurs correspondent généralement à l’une des options suivantes : <br/>  Interne <br/>  Externe <br/>  Mixte <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles l’appel s’est produit.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Mesures de l’activité vocale et vidéo d’égal à égal par serveur de médiation

Le tableau suivant répertorie les informations fournies dans le rapport vocal et vidéo d’égal à égal pour chaque serveur de médiation.
  
**Mesures de l’activité vocale et vidéo d’égal à égal par serveur de médiation**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Serveur de médiation** <br/> |Non  <br/> |Nom du serveur de médiation.  <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles l’appel s’est produit.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   

