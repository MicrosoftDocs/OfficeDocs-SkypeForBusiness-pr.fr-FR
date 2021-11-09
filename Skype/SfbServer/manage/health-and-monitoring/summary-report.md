---
title: Rapport de synthèse de diagnostic des appels dans Skype Entreprise Server
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
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Résumé : Découvrez le rapport de synthèse de diagnostic des appels utilisé dans Skype Entreprise Server.'
ms.openlocfilehash: ef50ecde07fdd7354bd97c40bddfe4fb5e762d08
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827567"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>Rapport de synthèse de diagnostic des appels dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de synthèse de diagnostic des appels utilisé dans Skype Entreprise Server.
  
Le rapport de synthèse de diagnostic des appels fournit une vue d’ensemble des sessions de conférence et des sessions d’égal à égal ayant échoué. Ce rapport comprend le taux d’échecs général pour ces deux types de sessions, et détaille les informations par type de modalité de session :
  
- Messagerie instantanée
    
- Partage d’application
    
- Transfert de fichiers
    
- Audio
    
- Vidéo
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Accès au rapport de synthèse de diagnostic des appels

Le rapport de synthèse de diagnostic des appels est accessible à partir de la page d’accueil Rapports de surveillance. À partir du rapport de synthèse de diagnostic des appels, vous pouvez accéder au rapport de diagnostic des activités P2E dans [Skype Entreprise Server](peer-to-peer-activity-diagnostic-report.md) en cliquant sur la mesure Taux d’échec sous la section Synthèse de session P2E du rapport. Vous pouvez également accéder au rapport de diagnostic de conférence [dans Skype Entreprise Server](conference-diagnostic-report.md) en cliquant sur l’une des mesures de conférence suivantes :
  
- Taux d’échec de session global
    
- Taux d’échec de focus
    
- Taux d’échec MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Utilisation efficace du rapport de synthèse de diagnostic des appels

Le rapport de synthèse de diagnostic des appels inclut des graphiques qui comparent les taux d’échec pour les différentes modalités utilisées dans Skype Entreprise Server. Les colonnes de ces graphiques sont en fait des liens à chaud ; Par exemple, si vous cliquez sur la colonne messagerie instantanée pour les sessions D’égal à égal, vous allez consulter une instance du rapport de diagnostic des activités P2E dans [Skype Entreprise Server](peer-to-peer-activity-diagnostic-report.md), un rapport qui fournit des détails supplémentaires sur toutes les sessions de messagerie instantanée incluses dans le rapport de synthèse de diagnostic des appels.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de synthèse de diagnostic des appels vous permet de filtrer selon des éléments tels que le pool de serveurs d’inscriptions ou le serveur Edge utilisé dans la session. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de diagnostic des appels.
  
**Filtres de rapport de synthèse de diagnostic des appels**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool spécifique ou cliquer sur **[Tout]** pour afficher des données pour tous les pools. Cette liste déroulante est remplie automatiquement pour vous en fonction des enregistrements de la base de données.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions d’égal à égal

Le tableau suivant décrit les informations fournies dans le rapport de synthèse de diagnostic des appels pour les sessions d’égal à égal (à savoir, celles qui n’impliquent que deux participants).
  
**Mesures pour les sessions d’égal à égal**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de sessions d’égal à égal ayant eu lieu.  <br/> |
|**Taux d’échec** <br/> |Non  <br/> |Pourcentage de sessions d’égal à égal ayant échoué. Lorsque vous cliquez sur cet élément, le rapport affiche le rapport de diagnostic des activités d’égal à égal, qui fournit des informations plus détaillées sur les sessions d’égal à égal ayant échoué.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau suivant décrit les informations fournies dans le rapport de diagnostic des appels pour les sessions de conférence (à savoir, celles qui impliquent trois participants ou plus).
  
**Mesures pour les sessions de conférence**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre total de conférences** <br/> |Non  <br/> |Nombre total de conférences ayant eu lieu.  <br/> |
|**Nombre total de sessions de conférence** <br/> |Non  <br/> |Nombre total de sessions de conférence ayant eu lieu.  <br/> |
|**Taux d’échec de session global** <br/> |Non  <br/> |Pourcentage du total de sessions de conférence ayant échoué.  <br/> |
|**Sessions Focus** <br/> |Non  <br/> |Nombre total de sessions de conférence de focus ayant échoué.  <br/> |
|**Taux d’échec de focus** <br/> |Non  <br/> |Pourcentage de sessions de conférence de focus ayant échoué.  <br/> |
|**Sessions MCU** <br/> |Non  <br/> |Nombre total de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.  <br/> |
|**Taux d’échec MCU** <br/> |Non  <br/> |Pourcentage de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.  <br/> |
   

