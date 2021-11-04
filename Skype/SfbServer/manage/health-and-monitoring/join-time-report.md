---
title: Rapport de temps d’adhésion aux conférences Skype Entreprise Server
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
ms.assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
description: 'Résumé : Découvrez le rapport de synthèse des heures de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: b1208802aa82bfe93951919403882477aa608889
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740520"
---
# <a name="conference-join-time-report-in-skype-for-business-server"></a>Rapport de temps d’adhésion aux conférences Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de synthèse des heures de conférence dans Skype Entreprise Server.
  
Le résumé des heures d؊’arrivée aux conférences vous permet de déterminer le temps nécessaire à vos utilisateurs pour rejoindre une conférence. Le rapport indique le temps nécessaire moyen (en millisecondes) et fournit également une répartition montrant combien d’utilisateurs ont pu rejoindre la conférence en 2 secondes ou moins, combien ont nécessité entre 2 et 5 secondes, etc.
  
## <a name="accessing-the-conference-join-time-report"></a>Accès au rapport des heures d’arrivée aux conférences

Le rapport des heures d’arrivée aux conférences est accessible à partir de la page d’accueil des Rapports de suivi.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport du temps de participation aux conférences.
  
**Filtres du rapport des heures d’arrivée aux conférences**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
|**Sessions de conférence** <br/> | Type de session. Les valeurs autorisées sont les suivantes : <br/>  [Tous] <br/>  Sessions Focus (focus est la stratégie centrale et le gestionnaire d’état pour les réunions en ligne et coordonne tous les aspects d’une conférence) <br/>  Partage d’application <br/>  Conférence A/V <br/>  Si vous sélectionnez [Tout], total des heures d’arrivée aux conférences s’affiche en haut du rapport. Notez que ces totaux ne concernent que les conférences planifiées à l’aide de Microsoft Exchange ou Microsoft Outlook. <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau suivant répertorie les informations fournies dans le rapport des heures d’arrivée aux conférences.
  
**Mesures du rapport des heures d’arrivée aux conférences**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Date** <br/> Le titre réel de cette mesure varie en fonction de l’intervalle sélectionné.  <br/> |Non  <br/> |Date et heure des conférences.  <br/> |
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de sessions qui comprend les sessions ayant abouti, les sessions ayant échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.  <br/> |
|**Moyenne (ms)** <br/> |Non  <br/> |Temps moyen (en millisecondes) nécessaire aux participants pour rejoindre la conférence.  <br/> |
|**Sessions \< 2 seconds, Volume** <br/> |Non  <br/> |Nombre de participants ayant pu rejoindre la conférence en moins de 2 secondes.  <br/> |
|**Sessions \< 2 seconds, Percentage** <br/> |Non  <br/> ||
|**Sessions 2-5 secondes, Volume** <br/> |Non  <br/> |Nombre de participants ayant nécessité entre 2 et 5 secondes pour rejoindre la conférence.  <br/> |
|**Sessions 2-5 secondes, Pourcentage** <br/> |Non  <br/> |Pourcentage du total des participants à l’appel ayant nécessité entre 2 et 5 secondes pour rejoindre la conférence.  <br/> |
|**Sessions 5-10 secondes, Volume** <br/> |Non  <br/> |Nombre de participants ayant nécessité entre 5 et 10 secondes pour rejoindre la conférence.  <br/> |
|**Sessions 5-10 secondes, Pourcentage** <br/> |Non  <br/> |Pourcentage du total des participants à l’appel ayant nécessité entre 5 et 10 secondes pour rejoindre la conférence.  <br/> |
|**Sessions \> 10 secondes, Volume** <br/> |Non  <br/> |Nombre de participants ayant nécessité plus de 10 secondes pour rejoindre la conférence.  <br/> |
|**Sessions \> 10 secondes, Pourcentage** <br/> |Non  <br/> |Pourcentage du total des participants à l’appel ayant nécessité plus de 10 secondes pour rejoindre la conférence.  <br/> |
   

