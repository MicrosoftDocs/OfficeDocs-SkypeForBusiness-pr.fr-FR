---
title: Rapport vocal et vidéo P2P dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Résumé : Découvrez les voix de Peer-to-Peer et le rapport vidéo dans Skype pour Business Server 2015.'
ms.openlocfilehash: 39b76b355addffb86954c302e9a8b7b0b7dde391
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server-2015"></a>Rapport vocal et vidéo P2P dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez la voix de Peer-to-Peer et rapport vidéo dans Skype pour Business Server 2015.
  
Le rapport vocal et vidéo d’égal-à-égal offre un examen détaillé de la distribution des appels vocaux et vidéo sur une période donnée (par exemple, les appels par heure ou par jour). Il vous offre également la possibilité de voir tous les appels vocaux et vidéo émis, ou de voir uniquement les appels ayant abouti ou échoué. Le rapport fournit les informations d’appels réparties dans les sections suivantes :
  
- Appels par pool
    
- Appels par type d’appel (par exemple, un Skype pour entreprise Skype pour appel d’entreprise et un Skype pour l’appel de métier à une personne sur le réseau PSTN)
    
- Appels par type d’accès (utilisateurs connectés au réseau interne par opposition aux utilisateurs connectés au réseau externe)
    
- Appels par serveur de médiation
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Pour accéder au rapport vocal et vidéo d’égal-à-égal

Vous pouvez accéder au rapport vocal et vidéo d’égal-à-égal en ouvrant simplement le rapport de synthèse d’activité d’égal-à-égal, puis en cliquant sur l’une des mesures suivantes :
  
- Nombre total de sessions audio P2P
    
- Nombre total de minutes audio d’égal-à-égal
    
- Nombre total de sessions vidéo P2P
    
- Nombre total de minutes vidéo d’égal-à-égal
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Pour une utilisation optimale du rapport vocal et vidéo d’égal-à-égal

Vous pouvez filtrer le rapport vocal et vidéo d’égal-à-égal de différentes manières. Cependant, ces options de filtre sont masquées par défaut. Pour afficher les options de filtre disponibles, cliquez sur le bouton **Afficher/Masquer les paramètres** dans le coin supérieur droit de la fenêtre du rapport.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport vocal et vidéo P2P.
  
**Voix de peer-to-peer et de filtres de rapport vidéo**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Type de média** <br/> | Indique le type de média utilisé dans la session. Sélectionnez l’une des options suivantes : <br/>  Les deux <br/>  Audio <br/>  Vidéo <br/> |
|**Distribution des appels** <br/> | Indique la réussite ou l’échec de la session. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Appels ayant abouti <br/>  Appels n’ayant pas abouti <br/> |
|**Établir un rapport par** <br/> | Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes : <br/>  Nombre de sessions <br/>  Minutes d’appel <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Mesures de l’activité vocale et vidéo P2P par pool

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo P2P pour chaque pool.
  
**Mesures des voix de peer-to-peer et l’activité vidéo par pool**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Pool** <br/> |Non  <br/> |Nom du pool de Registrar ou du serveur de transport Edge utilisés pour l’appel.  <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles l’appel s’est produit.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Mesures de l’activité vocale et vidéo P2P par type d’appel

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo P2P pour chaque type d’appel émis.
  
**Mesures des voix de peer-to-peer et l’activité vidéo par type d’appel**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’appel** <br/> |Non  <br/> | Indique le type d’appel émis. Les valeurs correspondent à l’une des options suivantes : <br/>  UC à UC <br/>  UC à RTC <br/>  RTC à UC <br/>  RTC à RTC <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles l’appel s’est produit.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Mesures de l’activité vocale et vidéo P2P par type d’accès

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo P2P pour chaque type d’accès réseau.
  
**Mesures des voix de peer-to-peer et l’activité vidéo par type d’accès**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’activité** <br/> |Non  <br/> | Indique si les clients étaient connectés au réseau interne ou au réseau externe au moment de passer l’appel. Les valeurs correspondent généralement à l’une des options suivantes : <br/>  Interne <br/>  Externe <br/>  Mixte <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles l’appel s’est produit.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Mesures de l’activité vocale et vidéo P2P par serveur de médiation

Le tableau suivant répertorie les informations fournies dans le rapport de la vidéo et de voix de Peer-to-Peer pour chaque serveur de médiation.
  
**Mesures des voix de peer-to-peer et l’activité vidéo par le serveur de médiation**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Serveur de médiation** <br/> |Non  <br/> |Nom du serveur de médiation.  <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure auxquelles l’appel s’est produit.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   

