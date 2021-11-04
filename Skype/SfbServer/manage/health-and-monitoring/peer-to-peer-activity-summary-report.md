---
title: Rapport de synthèse des activités D’égal à égal dans Skype Entreprise Server
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
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Résumé : Découvrez le rapport de synthèse des activités D’égal à égal dans Skype Entreprise Server.'
ms.openlocfilehash: 0614e113ad258bd66f436d0dc74106ddd35a26cd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774824"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Rapport de synthèse des activités D’égal à égal dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de synthèse des activités D’égal à égal dans Skype Entreprise Server.
  
Le rapport de synthèse des activités d’égal à égal fournit un aperçu de vos sessions de communication d؊’égal à égal. Une session d’égal à égal n’implique généralement que deux utilisateurs et ne nécessite pas l’utilisation des services Skype Entreprise Server conférence. En comparaison, une conférence implique généralement plus de deux utilisateurs et nécessite l’utilisation Skype Entreprise Server services de conférence. L’activité de conférence est reportée sur le rapport de synthèse de conférence.
  
Le rapport de synthèse des activités d’égal à égal vous aide à répondre à des questions telles que :
  
- Combien de messages instantanés d’égal à égal mes utilisateurs envoient-ils généralement par jour ?
    
- Mes utilisateurs tirez-ils réellement parti des fonctionnalités Skype Entreprise Server partage d’application et de transfert de fichiers ?
    
- Les utilisateurs ont signalé que le réseau semblait lent à certains moments de la journée. Combien de minutes sont consacrées à des sessions audio et vidéo d’égal à égal durant ces périodes ?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Accès au rapport de synthèse des activités d’égal à égal

Vous pouvez accéder au rapport de synthèse des activités d’égal à égal à partir de la page d’accueil des rapports de surveillance. Vous ouvrez [le rapport de messagerie](im-report.md) instantanée D’égal à égal dans Skype Entreprise Server en cliquant sur l’une des mesures suivantes :
  
- Nombre total de sessions de messagerie instantanée d’égal à égal
    
- Nombre total de messages de messagerie instantanée d’égal à égal
    
De même, vous pouvez ouvrir le rapport vocal et vidéo d’égal à égal en cliquant sur l’une de ces mesures :
  
- Nombre total de sessions d’égal à égal
    
- Nombre total de minutes par session audio d’égal à égal
    
- Nombre total de sessions audio d’égal à égal
    
- Nombre total de minutes par session audio d’égal à égal
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Utilisation optimale du rapport de synthèse des activités d’égal à égal

En bas du rapport de synthèse des activités d’égal à égal, vous trouverez les totaux des mesures telles que le Nombre total de sessions de messagerie instantanée d’égal à égal et le Nombre total de messages de messagerie instantanée d’égal à égal. Vous obtenez ainsi un rapide résumé des informations détaillées contenues dans le corps du rapport.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de synthèse des activités d’égal à égal vous permet de choisir le mode de groupement des données. Dans ce cas, les activités sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des activités d’égal à égal.
  
**Filtres du rapport de synthèse des activités d’égal à égal**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :  <br/> 17/07/12015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/17/12015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/13/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 17/07/12015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/17/12015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/13/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, Si vous sélectionnez l’intervalle Tous les jours avec une date de début du 17/07/12015 et une date de fin du 28/02/2015, les données s’affichent pour les jours 8/7/12015 12:00 au 07/09/12015 12:00 (autrement dit, un total de 31 jours de données). <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des activités d’égal à égal.
  
**Mesures du rapport de synthèse des activités d’égal à égal**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Tous les jours** <br/> **Toutes les semaines** <br/> **Mensuelle** <br/> |Non  <br/> |Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 17/07/12015, vous voyez une répartition horaire de l’activité d’inscription de l’utilisateur pour cette date.  <br/> |
|**Nombre total de sessions d’égal à égal** <br/> |Non  <br/> |Nombre total de sessions d’égal à égal menées, quel qu’en soit le type.  <br/> |
|**Nombre total de sessions de messagerie instantanée d’égal à égal** <br/> |Non  <br/> |Nombre total de sessions de messagerie instantanée (IM) d’égal à égal. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée d’égal à égal pour la période sélectionnée.  <br/> |
|**Nombre total de messages de messagerie instantanée d’égal à égal** <br/> |Non  <br/> |Nombre total de messages instantanés envoyés lors des sessions d’égal à égal. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée d’égal à égal pour la période sélectionnée.  <br/> |
|**Nombre total de sessions audio d’égal à égal** <br/> |Non  <br/> |Nombre total d’appels audio d’égal à égal. Lorsque vous cliquez sur ce champ, le rapport vous présente le rapport vocal et vidéo d’égal à égal pour la période sélectionnée.  <br/> |
|**Nombre total de minutes par session audio d’égal à égal** <br/> |Non  <br/> |Temps total passé dans les sessions audio d’égal à égal. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo d’égal à égal pour la période sélectionnée.  <br/> |
|**Nombre moyen de minutes par session audio d’égal à égal** <br/> |Non  <br/> |Temps moyen passé dans les sessions audio d’égal à égal. Calculé en divisant le temps total des sessions audio par le nombre total de sessions audio.  <br/> |
|**Nombre total de sessions vidéo d’égal à égal** <br/> |Non  <br/> |Nombre total d’appels vidéo d’égal à égal. Notez que les sessions vidéo sont également comptées comme des sessions audio : chaque session vidéo est comptée comme une seule session vidéo et une seule session audio. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo d’égal à égal pour la période sélectionnée.  <br/> |
|**Nombre total de minutes par session vidéo d’égal à égal** <br/> |Non  <br/> |Temps total passé dans les sessions vidéo d’égal à égal. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo d’égal à égal pour la période sélectionnée.  <br/> |
|**Nombre moyen de minutes par session vidéo d’égal à égal** <br/> |Non  <br/> |Temps moyen passé dans les sessions vidéo d’égal à égal. Calculé en divisant le temps total des sessions vidéo par le nombre total de sessions vidéo.  <br/> |
|**Nombre total de sessions de transfert de fichiers d’égal à égal** <br/> |Non  <br/> |Nombre total de sessions d’égal à égal qui ont inclus des transferts de fichiers.  <br/> |
|**Nombre total de sessions de partage d’application d’égal à égal** <br/> |Non  <br/> |Nombre total de sessions d’égal à égal qui ont inclus un partage d’application.  <br/> |
   

