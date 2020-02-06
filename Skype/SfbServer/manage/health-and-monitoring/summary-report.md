---
title: Rapport de synthèse des diagnostics de l’appel dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Résumé : en savoir plus sur le rapport synthèse des diagnostics de l’appel utilisé dans Skype entreprise Server.'
ms.openlocfilehash: 00925ca15ca053fc85ee5719c8154a92cfb35fb4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817663"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>Rapport de synthèse des diagnostics de l’appel dans Skype entreprise Server
 
**Résumé :** En savoir plus sur le rapport synthèse des diagnostics de diagnostic utilisé dans Skype entreprise Server.
  
Le rapport de synthèse de diagnostic des appels fournit une vue d’ensemble des sessions de conférence et des sessions P2P ayant échoué. Ce rapport comprend le taux d’échecs général pour ces deux types de sessions, et détaille les informations par type de modalité de session :
  
- Messagerie instantanée
    
- Partage d’application
    
- Transfert de fichiers
    
- Audio
    
- Vidéo
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Accès au rapport de synthèse de diagnostic des appels

Le rapport de synthèse de diagnostic des appels est accessible à partir de la page d’accueil Rapports de surveillance. Dans le rapport de synthèse des diagnostics d’appel, vous pouvez accéder au [rapport de diagnostic d’activité d’égal à égal dans Skype entreprise Server](peer-to-peer-activity-diagnostic-report.md) en cliquant sur la métrique du taux d’échec dans la section Résumé de la session d’égal à égal du rapport. Vous pouvez également accéder au [rapport de diagnostic de conférence dans Skype entreprise Server](conference-diagnostic-report.md) en cliquant sur l’une des mesures de conférence suivantes :
  
- Taux d’échec de session global
    
- Taux d’échec de focus
    
- Taux d’échec MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Utilisation efficace du rapport de synthèse de diagnostic des appels

Le rapport synthèse des diagnostics inclut des graphiques qui comparent les taux d’échec pour les différentes modalités d’utilisation dans Skype entreprise Server. Les colonnes de ces graphiques sont réellement des hyperliens. par exemple, si vous cliquez sur la colonne de messagerie instantanée pour les sessions d’égal à égal, vous découvrirez une instance du rapport de diagnostic de l' [activité P2P dans Skype entreprise Server](peer-to-peer-activity-diagnostic-report.md), un rapport contenant des informations supplémentaires sur l’ensemble des sessions de messagerie instantanée figurant dans le rapport synthèse des diagnostics d’appel.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de synthèse de diagnostic des appels vous permet de filtrer selon des éléments tels que le pool de serveurs d’inscriptions ou le serveur Edge utilisé dans la session. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de diagnostic des appels.
  
**Filtres de rapport de synthèse de diagnostic des appels**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions P2P

Le tableau ci-dessous décrit les informations fournies dans le rapport de synthèse de diagnostic des appels pour les sessions P2P (à savoir, celles qui n’impliquent que deux participants).
  
**Métriques pour les sessions d’égal à égal**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de sessions P2P ayant eu lieu.  <br/> |
|**Taux d’échec** <br/> |Non  <br/> |Pourcentage de sessions P2P ayant échoué. Lorsque vous cliquez sur cet élément, le rapport affiche le rapport de diagnostic des activités P2P, qui fournit des informations plus détaillées sur les sessions P2P ayant échoué.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau ci-dessous décrit les informations fournies dans le rapport de diagnostic des appels pour les sessions de conférence (à savoir, celles qui impliquent trois participants ou plus).
  
**Métriques pour les sessions de conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de conférences** <br/> |Non  <br/> |Nombre total de conférences ayant eu lieu.  <br/> |
|**Nombre total de sessions de conférence** <br/> |Non  <br/> |Nombre total de sessions de conférence ayant eu lieu.  <br/> |
|**Taux d’échec de session global** <br/> |Non  <br/> |Pourcentage du total de sessions de conférence ayant échoué.  <br/> |
|**Sessions Focus** <br/> |Non  <br/> |Nombre total de sessions de conférence de focus ayant échoué.  <br/> |
|**Taux d’échec de focus** <br/> |Non  <br/> |Pourcentage de sessions de conférence de focus ayant échoué.  <br/> |
|**Sessions MCU** <br/> |Non  <br/> |Nombre total de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.  <br/> |
|**Taux d’échec MCU** <br/> |Non  <br/> |Pourcentage de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.  <br/> |
   

