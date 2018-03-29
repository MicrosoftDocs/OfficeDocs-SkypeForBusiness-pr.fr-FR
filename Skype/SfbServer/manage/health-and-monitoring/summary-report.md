---
title: Rapport de synthèse de diagnostic des appels dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Résumé : Découvrez l’appeler Diagnostic rapport utilisé dans Skype pour Business Server 2015.'
ms.openlocfilehash: 8d040ab2d59fdbc822448de2d3c9918ec39ae289
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server-2015"></a>Rapport de synthèse de diagnostic des appels dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur le rapport de résumé du Diagnostic d’appeler utilisé dans Skype pour Business Server 2015.
  
Le rapport de synthèse de diagnostic des appels fournit une vue d’ensemble des sessions de conférence et des sessions P2P ayant échoué. Ce rapport comprend le taux d’échecs général pour ces deux types de sessions, et détaille les informations par type de modalité de session :
  
- Messagerie instantanée
    
- Partage d’application
    
- Transfert de fichiers
    
- Audio
    
- Vidéo
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Accès au rapport de synthèse de diagnostic des appels

Le rapport de synthèse de diagnostic des appels est accessible à partir de la page d’accueil Rapports de surveillance. À partir du rapport appeler Diagnostic résumé, vous pouvez accéder le [rapport de Diagnostic activité Peer-to-Peer dans Skype pour 2015 de serveur d’entreprise](peer-to-peer-activity-diagnostic-report.md) en cliquant sur la mesure de taux d’échec sous la section Résumé de la Session d’homologue à homologue de l’état. Le [Rapport de Diagnostics de conférence dans Skype pour Business Server 2015](conference-diagnostic-report.md) est également accessible en cliquant sur une des mesures suivantes de conférence :
  
- Taux d’échec de session global
    
- Taux d’échec de focus
    
- Taux d’échec MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Utilisation efficace du rapport de synthèse de diagnostic des appels

Le rapport de synthèse Diagnostic appeler comprend des graphiques qui permettent de comparer les taux d’échec pour les différentes modalités utilisées dans Skype pour Business Server 2015. Les colonnes de ces graphiques sont en fait de lien direct ; par exemple, si vous cliquez sur la colonne de messagerie instantanée pour les sessions d’homologue à homologue, vous allez accéder à une instance du [rapport de Diagnostic activité Peer-to-Peer dans Skype pour Business Server 2015](peer-to-peer-activity-diagnostic-report.md), un rapport qui fournit des détails supplémentaires sur l’ensemble du inclus dans le rapport de synthèse Diagnostic appeler des sessions de messagerie instantanée.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de synthèse de diagnostic des appels vous permet de filtrer selon des éléments tels que le pool de serveurs d’inscriptions ou le serveur Edge utilisé dans la session. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de diagnostic des appels.
  
**Appeler des filtres de rapport de synthèse de Diagnostic**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions P2P

Le tableau ci-dessous décrit les informations fournies dans le rapport de synthèse de diagnostic des appels pour les sessions P2P (à savoir, celles qui n’impliquent que deux participants).
  
**Mesures des Sessions d’homologue à homologue**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de sessions P2P ayant eu lieu.  <br/> |
|**Taux d’échec** <br/> |Non  <br/> |Pourcentage de sessions P2P ayant échoué. Lorsque vous cliquez sur cet élément, le rapport affiche le rapport de diagnostic des activités P2P, qui fournit des informations plus détaillées sur les sessions P2P ayant échoué.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau ci-dessous décrit les informations fournies dans le rapport de diagnostic des appels pour les sessions de conférence (à savoir, celles qui impliquent trois participants ou plus).
  
**Métrique pour les Sessions de conférence**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de conférences** <br/> |Non  <br/> |Nombre total de conférences ayant eu lieu.  <br/> |
|**Nombre total de sessions de conférence** <br/> |Non  <br/> |Nombre total de sessions de conférence ayant eu lieu.  <br/> |
|**Taux d’échec de session global** <br/> |Non  <br/> |Pourcentage du total de sessions de conférence ayant échoué.  <br/> |
|**Sessions Focus** <br/> |Non  <br/> |Nombre total de sessions de conférence de focus ayant échoué.  <br/> |
|**Taux d’échec de focus** <br/> |Non  <br/> |Pourcentage de sessions de conférence de focus ayant échoué.  <br/> |
|**Sessions MCU** <br/> |Non  <br/> |Nombre total de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.  <br/> |
|**Taux d’échec MCU** <br/> |Non  <br/> |Pourcentage de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.  <br/> |
   

