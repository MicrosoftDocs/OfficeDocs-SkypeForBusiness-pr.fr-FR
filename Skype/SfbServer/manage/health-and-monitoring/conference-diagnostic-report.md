---
title: Rapport de Diagnostic conférence dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
description: 'Résumé : Découvrez le rapport de Diagnostic de conférence utilisés dans Skype pour Business Server.'
ms.openlocfilehash: eb7fde75050b6d97172986aef6429cdc19216f59
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197617"
---
# <a name="conference-diagnostic-report-in-skype-for-business-server"></a>Rapport de Diagnostic conférence dans Skype pour Business Server
 
**Résumé :** Obtenir des informations sur le rapport de Diagnostic de conférence utilisés dans Skype pour Business Server.
  
Le rapport de diagnostic de conférence fournit des informations sur la réussite ou l’échec de toutes les sessions de conférence. Notez que Skype pour Business Server fait la distinction entre les différents types de défaillance :
  
- **échec attendu**. Un échec attendu est généralement une erreur au sens technique seulement. Par exemple, supposons que quelqu’un démarre une conférence, mais raccroche avant que des personnes puissent participer. Techniquement, c’est une erreur : la conférence a été lancée, mais n’a pas été achevée. Cependant, il s’agit d’une erreur à laquelle on peut s’attendre : si l’organisateur annule la conférence avant que des personnes puissent participer, on ne s’attend pas à ce que cette conférence soit achevée.
    
- **échec inattendu**. Un échec inattendu constitue exactement ce que son nom indique : une erreur à laquelle on ne s’attend pas, compte tenu des circonstances. Par exemple, supposons qu’une conférence ne puisse pas avoir lieu parce que la stratégie de réunion de l’organisateur n’a pas pu être récupérée. Il s’agit d’une erreur inattendue : la stratégie de réunion d’un utilisateur doit toujours pouvoir être récupérée.
    
Notez que les mesures de Réussite, d’Échec attendu et d’Échec inattendu peuvent ne pas être comptabilisées dans la mesure Nombre total de sessions. Par exemple, vous pouvez voir les valeurs suivantes dans le rapport :
  
|**Réussites**|**Échecs attendus**|**Échecs inattendus**|**Nombre total de sessions**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Si vous ajoutez 2 024 + 469 + 16, vous obtenez un total de 2 509 sessions alors que la colonne Nombre total de sessions indique 2 521 sessions. Les 12 sessions « manquantes » sont celles que le système n’a pas pu catégoriser comme réussies ou non. Qui sera parfois le cas lorsqu’un produit tiers introduit un nouveau code de diagnostic est inconnu au serveur de surveillance. Dans ce cas, les appels effectués à l’aide de ce produit et reportant ce code de diagnostic ne peuvent pas toujours être catégorisés en tant que réussite, échec attendu ou échec inattendu.
  
## <a name="accessing-the-conference-diagnostic-report"></a>Accès au rapport de diagnostic de conférence

Le rapport des de diagnostic de conférence est accessible à partir de la page d’accueil des Rapports de suivi. Vous pouvez accéder au [Rapport de répartition dans Skype pour Business Server](failure-distribution-report.md) en cliquant sur une des mesures suivantes :
  
- Nombre d’échecs inattendus
    
- Nombre d’échecs attendus
    
## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Utilisation optimale du rapport de diagnostic de conférence

Le rapport de diagnostic de conférence inclut une série de graphiques. Chaque colonne de graphique constitue un lien hypertexte. Si vous cliquez sur une colonne, vous allez consulter le [Rapport de répartition dans Skype pour Business Server](failure-distribution-report.md) pour cette période et ce type de conférence.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de diagnostic de conférence vous permet de filtrer les éléments tels que le type de conférence mené (par exemple, une conférence Focus) pour le serveur Edge utilisé dans la conférence. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic de conférence.
  
**Filtres du rapport de diagnostic de conférence**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
|**Sessions de conférence** <br/> | Indique le type de session de conférence. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Sessions Focus <br/>  Toutes les sessions MCU <br/>  Conférence par messagerie instantanée <br/>  Partage d’application <br/>  Conférence A/V <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de diagnostic de conférence pour chaque type de session de conférence.
  
**Mesures du rapport de diagnostic de conférence**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Nombre de réussites** <br/> |Non  <br/> |Nombre total de conférences réussies.  <br/> |
|**Pourcentage de réussite** <br/> |Non  <br/> |Pourcentage de conférences qui se sont déroulées sans problème majeur. Calculé en divisant le nombre de réussites par le nombre total de sessions.  <br/> |
|**Nombre d’échecs attendus** <br/> |Non  <br/> |Nombre total de conférences pour lesquelles un « échec attendu » s’est produit.  <br/> Un échec attendu est un échec auquel il faut s’attendre. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, il faut s’attendre à ce que tout appel émis vers cet utilisateur échoue.  <br/> |
|**Pourcentage d’échec attendu** <br/> |Non  <br/> |Pourcentage de conférences qui ont rencontré une erreur attendue. Calculé en divisant le nombre d’échecs attendus par le nombre total de sessions.  <br/> |
|**Nombre d’échecs inattendus** <br/> |Non  <br/> |Nombre total de conférences pour lesquelles un « échec inattendu » s’est produit.  <br/> Un échec inattendu est un échec qui se produit alors que le système semble intègre. Par exemple, un appel ne doit pas être coupé si l’appelant est mis en attente. Dans le cas contraire, ce problème est considéré comme un échec inattendu.  <br/> |
|**Pourcentage d’échec inattendu** <br/> |Non  <br/> |Pourcentage de conférences qui ont rencontré une erreur inattendue. Calculé en divisant le nombre d’échecs inattendus par le nombre total de sessions.  <br/> |
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de conférences, incluant les conférences qui ont réussi et celles qui ont échoué (à la fois les échecs attendus et les échecs inattendus), ainsi que les conférences qui n’appartiennent à aucune catégorie.  <br/> |
   

