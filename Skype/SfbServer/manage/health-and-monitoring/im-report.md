---
title: Rapport de messagerie instantanée d’égal à égal dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 'Résumé : Découvrez l’état de la messagerie instantanée d’égal à égal dans Skype pour Business Server.'
ms.openlocfilehash: e7e65e11d6a8710c4a37fc3afe0a983d5ce9b14d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968613"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Rapport de messagerie instantanée d’égal à égal dans Skype pour Business Server
 
**Résumé :** Obtenir des informations sur l’état de la messagerie instantanée d’égal à égal dans Skype pour Business Server.
  
Le rapport de messagerie instantanée P2P fournit les tendances des sessions de messagerie instantanée P2P, par pool et par type d’authentification. Le rapport peut afficher le nombre total de sessions tenues pendant une période donnée (par exemple, jour par jour ou heure par heure) ou le nombre total de messages instantanés envoyés au cours de cette période.
  
## <a name="accessing-the-peer-to-peer-im-report"></a>Accès au rapport de messagerie instantanée P2P

Vous pouvez accéder à l’état de la messagerie instantanée d’égal à égal uniquement en ouvrant le [rapport de synthèse de l’activité d’égal à égal dans Skype pour Business Server](peer-to-peer-activity-summary-report.md) et puis en cliquant sur une des mesures suivantes :
  
- Nombre total de sessions de messagerie instantanée P2P
    
- Nombre total de messages de messagerie instantanée P2P
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Utilisation optimale du rapport de messagerie instantanée P2P

Par défaut, le rapport de messagerie instantanée P2P vous montre le nombre de messages par heure (ou par jour, selon vos paramètres). Vous pouvez toutefois également afficher le nombre de sessions par heure sur une journée. Pour ce faire, cliquez sur **Afficher/Masquer les paramètres** dans l’angle supérieur droit de la fenêtre Rapports, puis cliquez sur **Nombre de sessions** dans la liste **Établir un rapport par**.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau ci-dessous dresse la liste des filtres que vous pouvez utiliser avec le rapport de messagerie instantanée P2P.
  
**Filtres du rapport de messagerie instantanée P2P**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Établir un rapport par** <br/> | Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes : <br/>  Nombre de sessions <br/>  Nombre de messages <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Mesure d’une session de messagerie instantanée P2P par pool

Le tableau qui suit répertorie les informations fournies dans le rapport de messagerie instantanée P2P.
  
**Mesure d’une session de messagerie instantanée P2P par pool**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Pool** <br/> |Non  <br/> |Nom du pool de serveurs d’inscriptions ou du serveur Edge.  <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure des sessions.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Mesure d’une session de messagerie instantanée P2P par type d’authentification

Le tableau ci-dessous dresse la liste des informations fournies dans le rapport de messagerie instantanée P2P pour chaque type d’authentification utilisé par les participants dans une session P2P.
  
**Mesure d’une session de messagerie instantanée P2P par type d’authentification**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’authentification** <br/> |Non  <br/> | Type d’authentification utilisé par les participants de la session. Les valeurs sont généralement l’une des valeurs suivantes : <br/>  Enterprise <br/>  Federated <br/>  PIC <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure des sessions.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   

