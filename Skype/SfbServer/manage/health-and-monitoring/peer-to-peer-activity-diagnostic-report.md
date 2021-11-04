---
title: Rapport de diagnostic des activités D’égal à égal dans Skype Entreprise Server
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
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Résumé : Découvrez le rapport de diagnostic des activités D’égal à égal dans Skype Entreprise Server.'
ms.openlocfilehash: 703592939b5f90311a4b9da551a6ebfe28989c31
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774834"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Rapport de diagnostic des activités D’égal à égal dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de diagnostic des activités D’égal à égal dans Skype Entreprise Server.
  
Le rapport de diagnostic des activités d’égal à égal fournit des informations sur la réussite ou l’échec des sessions de communication d’égal à égal. Notez que Skype Entreprise Server différents types d’échec :
  
- **Échec attendu**. Un échec attendu est en général un échec considéré comme strictement technique. Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit absente de son bureau et ne puisse donc répondre à votre appel. Étant donné que l’appel n’a pas été répondu, il est techniquement considéré comme un échec. En revanche, il s’agit d’un échec attendu : Skype Entreprise Server ne s’attend pas à ce que vous répondiez au téléphone si vous n’êtes pas disponible pour répondre au téléphone. De même, un échec attendu se produira si vous tentez d’envoyer un message instantané à un utilisateur qui est hors ligne ou qui est connecté à un téléphone qui ne prend pas les messages instantanés.
    
- **Échec inattendu**. Comme son nom l’indique, une erreur inattendue est une erreur que vous  n’attendiez pas selon les circonstances. Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit disponible pour répondre à l’appel ; toutefois, lorsque Skype Entreprise Server tente d’router votre appel vers la messagerie vocale, l’appel échoue en raison de la Exchange la messagerie unifiée a été perdue. Il s’agit d’une erreur inattendue : vous vous attendez à ce que les appels soient toujours acheminés vers la messagerie vocale. En règle générale, les échecs inattendus sont de vrais échecs : ce sont des problèmes auxquels il n’est pas possible de remédier en formant les utilisateurs ou à l’aide de mesures similaires.
    
Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions. Par exemple, l’illustration précédente indique les valeurs suivantes :
  
|**Réussites**|**Échecs attendus**|**Échecs inattendus**|**Nombre total de sessions**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Si vous additionnez 2024 + 469 + 16 vous obtenez un total de 2 509 sessions alors que la colonne du total des sessions indique 2 521 sessions. Les 12 sessions « manquantes » sont des sessions que le système n’est pas parvenu à classer comme des succès ou des échecs. Ce sera parfois le cas lorsqu’un produit tiers introduit un nouveau code de diagnostic qui n’est pas familier Skype Entreprise Server. Lorsque cela arrive, les appels effectués à l’aide de ce produit, et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Accès au rapport de diagnostic des activités d’égal à égal

Le rapport de diagnostic des activités d’égal à égal est accessible à partir de la page d’accueil des rapports de surveillance. Vous pouvez accéder au [rapport de répartition](failure-distribution-report.md) des défaillances dans Skype Entreprise Server en cliquant sur l’une des mesures suivantes :
  
- Volume d’échecs inattendus
    
- Volume d’échecs attendus
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Utilisation optimale du rapport de diagnostic des activités d’égal à égal

Il existe plusieurs manières de filtrer le rapport de diagnostic des activités d’égal à égal mais, par défaut, les options de filtrage sont masquées. Pour les afficher, cliquez sur le bouton Afficher/Masquer les paramètres dans le coin supérieur droit de la fenêtre des rapports. Les options de filtrage s’affichent alors.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de diagnostic des activités d’égal à égal vous permet de filtrer selon des éléments précis, tels que la modalité de session (à savoir messagerie instantanée, transfert de fichiers ou partage d’application). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic des activités d’égal à égal.
  
**Filtres du rapport de diagnostic des activités d’égal à égal**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Pool** <br/> |Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez soit sélectionner un pool individuel soit cliquer sur **[Tous]** pour afficher les données pour tous les pools. La liste déroulante est automatiquement renseignée en fonction des enregistrements de la base de données.<br/> |
|**Modalité** <br/> | Indique le type d’activité de communication qui a eu lieu. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Messagerie instantanée <br/>  Transfert de fichiers <br/>  Partage d’application <br/>  Audio <br/>  Vidéo <br/> |
   
## <a name="metrics-per-modality"></a>Mesures (par modalité)

Le tableau suivant dresse la liste des informations fournies dans le rapport de diagnostic des activités d’égal à égal pour chaque modalité.
  
**Mesures (par modalité)**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Volume d’opération réussie** <br/> |Non  <br/> |Nombre total des sessions d’égal à égal réussies.  <br/> |
|**Pourcentage d’opération réussie** <br/> |Non  <br/> |Pourcentage des sessions d’égal à égal qui se sont terminées avec des problèmes importants. Calculé en divisant le volume des opérations réussies par le nombre total de sessions.  <br/> |
|**Volume d’échec attendu** <br/> |Non  <br/> |Nombre total de sessions lors desquelles un « échec attendu » s’est produit.  <br/> Un échec attendu est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent.  <br/> |
|**Pourcentage d’échec attendu** <br/> |Non  <br/> |Pourcentage de sessions d’égal à égal lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.  <br/> |
|**Volume d’échec inattendu** <br/> |Non  <br/> |Nombre total de sessions où un « échec inattendu » s’est produit.  <br/> Un échec inattendu se produit dans un système sain. Par exemple, un appel ne doit pas se terminer si l’appelant l’a mis en attente. Le cas échéant, cela serait marqué comme un échec inattendu.  <br/> |
|**Pourcentage d’échec inattendu** <br/> |Non  <br/> |Pourcentage de sessions d’égal à égal lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.  <br/> |
|**Nombre total de sessions** <br/> |Non  <br/> |Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.  <br/> |
   

