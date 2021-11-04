---
title: Rapport de diagnostic de conférence en Skype Entreprise Server
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
ms.assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
description: 'Résumé : Découvrez le rapport de diagnostic de conférence utilisé dans Skype Entreprise Server.'
ms.openlocfilehash: c62a45c6bff7a91e6d0252ecc1a8010e5098f42b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773584"
---
# <a name="conference-diagnostic-report-in-skype-for-business-server"></a>Rapport de diagnostic de conférence en Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de diagnostic de conférence utilisé dans Skype Entreprise Server.
  
Le rapport de diagnostic de conférence fournit des informations sur la réussite et l’échec de toutes les sessions de conférence. Notez que Skype Entreprise Server différents types d’échec :
  
- **Échec attendu**. Un échec attendu est en général un échec considéré comme strictement technique. Par exemple, supposons que quelqu’un démarre une conférence mais raccroche avant que quelqu’un puisse participer. Techniquement, c’est un échec : la conférence a été initiée, mais pas terminée. Toutefois, il s’agit d’un échec qui devrait se produire : si l’organisateur annule la conférence avant que quelqu’un puisse participer, vous ne vous attendez pas à ce que la conférence soit terminée.
    
- **Échec inattendu**. Comme son nom l’indique, une erreur inattendue est une erreur que vous  n’attendiez pas selon les circonstances. Par exemple, supposons qu’une conférence n’a pas pu avoir lieu car la stratégie de réunion de l’organisateur n’a pas pu être récupérée. Il s’agit d’une erreur inattendue : après tout, vous devez toujours être en mesure de récupérer la stratégie de réunion d’un utilisateur.
    
Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions. Par exemple, vous pouvez voir les valeurs suivantes dans le rapport :
  
|**Réussites**|**Échecs attendus**|**Échecs inattendus**|**Nombre total de sessions**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Si vous ajoutez 2 024 + 469 + 16, vous obtenez un total de 2 509 sessions et, pour l’instant, la colonne Nombre total de sessions affiche un total de 2 521 sessions. Les 12 sessions « manquantes » sont des sessions que le système n’a pas pu catégoriser comme réussies ou infructueuses. Ce sera parfois le cas lorsqu’un produit tiers introduit un nouveau code de diagnostic qui n’est pas familier au serveur de surveillance. Lorsque cela arrive, les appels effectués à l’aide de ce produit, et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.
  
## <a name="accessing-the-conference-diagnostic-report"></a>Accès au rapport de diagnostic de conférence

Le rapport de diagnostic de conférence est accessible à partir de la page d’accueil Rapports de surveillance. Vous pouvez accéder au [rapport de répartition](failure-distribution-report.md) des défaillances dans Skype Entreprise Server en cliquant sur l’une des mesures suivantes :
  
- Volume d’échecs inattendus
    
- Volume d’échecs attendus
    
## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Utilisation du rapport de diagnostic de conférence

Le rapport de diagnostic de conférence inclut une série de graphiques. Chacune des colonnes affichées dans le graphique est en fait un lien hypertexte. Si vous cliquez sur une colonne, vous allez consulter le rapport de répartition des défaillances dans [Skype Entreprise Server](failure-distribution-report.md) pour cette période et ce type de conférence.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de diagnostic de conférence vous permet de filtrer sur des éléments tels que le type de conférence menée (par exemple, une conférence focus) ou par le serveur Edge utilisé dans la conférence. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.
  
Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de diagnostic de conférence.
  
**Filtres du rapport de diagnostic de conférence**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur **[Tous]** pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.<br/> |
|**Sessions de conférence** <br/> | Indique le type de session de conférence. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Sessions Focus <br/>  Toutes les sessions MCU <br/>  Conférence par messagerie instantanée <br/>  Partage d’application <br/>  Conférence A/V <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau suivant répertorie les informations fournies dans le rapport de diagnostic de conférence pour chaque type de session de conférence.
  
**Mesures du rapport de diagnostic de conférence**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Volume d’opération réussie** <br/> |Non  <br/> |Nombre total de conférences réussies.  <br/> |
|**Pourcentage d’opération réussie** <br/> |Non  <br/> |Pourcentage de conférences qui se sont terminées avec des problèmes importants. Calculé en divisant le volume des opérations réussies par le nombre total de sessions.  <br/> |
|**Volume d’échec attendu** <br/> |Non  <br/> |Nombre total de conférences où un « échec attendu » s’est produit.  <br/> Un échec attendu est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent.  <br/> |
|**Pourcentage d’échec attendu** <br/> |Non  <br/> |Pourcentage de conférences qui ont connu une erreur attendue. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.  <br/> |
|**Volume d’échec inattendu** <br/> |Non  <br/> |Nombre total de conférences où un « échec inattendu » s’est produit.  <br/> Un échec inattendu se produit dans un système sain. Par exemple, un appel ne doit pas se terminer si l’appelant l’a mis en attente. Le cas échéant, cela serait marqué comme un échec inattendu.  <br/> |
|**Pourcentage d’échec inattendu** <br/> |Non  <br/> |Pourcentage de conférences qui ont connu une erreur inattendue. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.  <br/> |
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de conférences, y compris les conférences réussies, les conférences qui ont échoué (échecs attendus et échecs inattendus) et les conférences non catégorisées.  <br/> |
   

