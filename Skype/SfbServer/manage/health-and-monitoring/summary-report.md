---
title: Rapport de synthèse de Diagnostic des appels dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Résumé : Découvrez le rapport Diagnostic des appels résumé utilisé dans Skype pour Business Server.'
ms.openlocfilehash: 6d4db52f266e9c7387662563a8640cfaeab56ca8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976820"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>Rapport de synthèse de Diagnostic des appels dans Skype pour Business Server
 
**Résumé :** Découvrez le rapport Diagnostic des appels résumé utilisé dans Skype pour Business Server.
  
Le rapport de synthèse de diagnostic des appels fournit une vue d’ensemble des sessions de conférence et des sessions P2P ayant échoué. Ce rapport comprend le taux d’échecs général pour ces deux types de sessions, et détaille les informations par type de modalité de session :
  
- Messagerie instantanée
    
- Partage d’application
    
- Transfert de fichiers
    
- Audio
    
- Vidéo
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Accès au rapport de synthèse de diagnostic des appels

Le rapport de synthèse de diagnostic des appels est accessible à partir de la page d’accueil Rapports de surveillance. Dans le rapport de synthèse Diagnostic des appels, vous pouvez accéder le [rapport Diagnostic des activités d’égal à égal dans Skype pour Business Server](peer-to-peer-activity-diagnostic-report.md) en cliquant sur la mesure de taux d’échec sous la section Résumé de la Session d’égal à égal du rapport. Vous pouvez également accéder le [Rapport de Diagnostic de conférence dans Skype pour Business Server](conference-diagnostic-report.md) en cliquant sur une des mesures de conférence suivantes :
  
- Taux d’échec de session global
    
- Taux d’échec de focus
    
- Taux d’échec MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Utilisation efficace du rapport de synthèse de diagnostic des appels

Le rapport de synthèse Diagnostic des appels comprend des graphiques qui permettent de comparer le taux d’échec pour les modalités diverses utilisées dans Skype pour Business Server. Les colonnes de ces graphiques sont réellement lien direct ; par exemple, si vous cliquez sur la colonne de messagerie instantanée pour les sessions d’égal à égal, vous allez accéder à une instance du [rapport Diagnostic des activités d’égal à égal dans Skype pour Business Server](peer-to-peer-activity-diagnostic-report.md), un rapport qui fournit des détails supplémentaires sur tous les inclus dans le rapport de synthèse Diagnostic des appels des sessions de messagerie instantanée.
  
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
  
**Mesures pour les sessions P2P**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de sessions P2P ayant eu lieu.  <br/> |
|**Taux d’échec** <br/> |Non  <br/> |Pourcentage de sessions P2P ayant échoué. Lorsque vous cliquez sur cet élément, le rapport affiche le rapport de diagnostic des activités P2P, qui fournit des informations plus détaillées sur les sessions P2P ayant échoué.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau ci-dessous décrit les informations fournies dans le rapport de diagnostic des appels pour les sessions de conférence (à savoir, celles qui impliquent trois participants ou plus).
  
**Mesures pour les sessions de conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de conférences** <br/> |Non  <br/> |Nombre total de conférences ayant eu lieu.  <br/> |
|**Nombre total de sessions de conférence** <br/> |Non  <br/> |Nombre total de sessions de conférence ayant eu lieu.  <br/> |
|**Taux d’échec de session global** <br/> |Non  <br/> |Pourcentage du total de sessions de conférence ayant échoué.  <br/> |
|**Sessions Focus** <br/> |Non  <br/> |Nombre total de sessions de conférence de focus ayant échoué.  <br/> |
|**Taux d’échec de focus** <br/> |Non  <br/> |Pourcentage de sessions de conférence de focus ayant échoué.  <br/> |
|**Sessions MCU** <br/> |Non  <br/> |Nombre total de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.  <br/> |
|**Taux d’échec MCU** <br/> |Non  <br/> |Pourcentage de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.  <br/> |
   

