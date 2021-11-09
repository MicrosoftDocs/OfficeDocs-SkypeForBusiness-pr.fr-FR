---
title: Rapport de messagerie instantanée D’égal à égal dans Skype Entreprise Server
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
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 'Résumé : Découvrez le rapport de messagerie instantanée D’égal à égal dans Skype Entreprise Server.'
ms.openlocfilehash: f72200547ca8af3fa2ebde0e44c4707c82a1596b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834202"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Rapport de messagerie instantanée D’égal à égal dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de messagerie instantanée D’égal à égal dans Skype Entreprise Server.
  
Le rapport de messagerie instantanée D’égal à égal fournit des informations de tendance sur les sessions de messagerie instantanée d’égal à égal, décomposées par pool et par type d’authentification. Le rapport peut afficher le nombre total de sessions tenues pendant la période spécifiée (par exemple, jour par jour ou heure par heure), ou il peut afficher le nombre total de messages instantanés envoyés pendant cette période.
  
## <a name="accessing-the-peer-to-peer-im-report"></a>Accès au rapport de messagerie instantanée D’égal à égal

Vous pouvez accéder au rapport de messagerie instantanée D’égal à égal uniquement en ouvrant le rapport de synthèse des activités D’égal à égal dans [Skype Entreprise Server](peer-to-peer-activity-summary-report.md) puis en cliquant sur l’une des mesures suivantes :
  
- Nombre total de sessions de messagerie instantanée d’égal à égal
    
- Nombre total de messages de messagerie instantanée d’égal à égal
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Utilisation du rapport de messagerie instantanée D’égal à égal

Par défaut, le rapport de messagerie instantanée D’égal à égal affiche le nombre de messages par heure (ou jour, selon vos paramètres). Toutefois, vous pouvez également choisir d’afficher le jour par session par heure. Pour ce faire, cliquez sur **Masquer/Afficher** les paramètres dans le coin supérieur droit de la fenêtre Rapports, puis cliquez sur Nombre de **sessions** dans la liste Rapport **par.**
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de messagerie instantanée D’égal à égal.
  
**Filtres de rapport de messagerie instantanée D’égal à égal**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher par semaine ou par mois, entrez une date qui se situe n’importe où dans la semaine ou le mois (vous n’avez pas besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si les dates de début et de fin dépassent le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à partir de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Établir un rapport par** <br/> | Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes : <br/>  Nombre de sessions <br/>  Nombre de messages <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Mesures de la session de messagerie instantanée P2D par pool

Le tableau suivant répertorie les informations fournies dans le rapport de messagerie instantanée D’égal à égal.
  
**Mesures de la session de messagerie instantanée P2D par pool**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Pool** <br/> |Non  <br/> |Nom du pool de serveurs d’inscriptions ou du serveur Edge.  <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure des sessions.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Mesures de la session de messagerie instantanée P2D par type d’authentification

Le tableau suivant répertorie les informations fournies dans le rapport de messagerie instantanée D’égal à égal pour chaque type d’authentification utilisé par les participants dans une session d’égal à égal.
  
**Mesures de la session de messagerie instantanée P2D par type d’authentification**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’authentification type** <br/> |Non  <br/> | Type d’authentification utilisé par les participants à la session. Les valeurs correspondent généralement à l’une des options suivantes : <br/>  Entreprise <br/>  Fédéré <br/>  PIC <br/> |
|**Date/Heure** <br/> |Non  <br/> |Date et heure des sessions.  <br/> |
|**Total** <br/> |Non  <br/> |Nombre total de sessions ou de messages.  <br/> |
   

