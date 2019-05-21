---
title: Rapport de synthèse des activités d’égal à égal dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Résumé: en savoir plus sur le rapport de synthèse des activités d’égal à égal dans Skype entreprise Server.'
ms.openlocfilehash: dd11e5d998c8aef779b98cc0a74ba83a4dc70d84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279893"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Rapport de synthèse des activités d’égal à égal dans Skype entreprise Server
 
**Résumé:** En savoir plus sur le rapport de synthèse des activités d’égal à égal dans Skype entreprise Server.
  
Le rapport de synthèse des activités P2P fournit un aperçu de vos sessions de communication d?’P2P. Une session d’égal à égal implique généralement deux utilisateurs uniquement et ne nécessite pas l’utilisation des services de conférence Skype entreprise Server. En comparaison, une conférence implique généralement plus de deux utilisateurs et nécessite l’utilisation des services de conférence Skype entreprise Server. L’activité de conférence est reportée sur le rapport de synthèse de conférence.
  
Le rapport de synthèse des activités P2P vous aide à répondre à des questions telles que :
  
- Combien de messages instantanés P2P mes utilisateurs envoient-ils généralement par jour ?
    
- Certains de mes utilisateurs tirent-ils réellement parti du partage d’application et de la fonctionnalité de transfert de fichiers de Skype entreprise Server?
    
- Les utilisateurs ont signalé que le réseau semblait lent à certains moments de la journée. Combien de minutes sont consacrées à des sessions audio et vidéo P2P durant ces périodes ?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Accès au rapport de synthèse des activités P2P

Vous pouvez accéder au rapport de synthèse des activités P2P à partir de la page d’accueil des rapports de surveillance. Pour ouvrir le [rapport de messagerie instantanée d’égal à égal dans Skype entreprise Server](im-report.md) , cliquez sur l’une des mesures suivantes:
  
- Nombre total de sessions d'égal à égal de messagerie instantanée
    
- Nombre total de messages de messagerie instantanée P2P
    
De même, vous pouvez ouvrir le rapport vocal et vidéo P2P en cliquant sur l’une de ces mesures :
  
- Nombre total de sessions d'égal à égal audio
    
- Nombre total de minutes par session audio P2P
    
- Nombre total de sessions audio P2P
    
- Nombre total de minutes par session audio P2P
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Utilisation optimale du rapport de synthèse des activités P2P

En bas du rapport de synthèse des activités P2P, vous trouverez les totaux des mesures telles que le Nombre total de sessions de messagerie instantanée P2P et le Nombre total de messages de messagerie instantanée P2P. Vous obtenez ainsi un rapide résumé des informations détaillées contenues dans le corps du rapport.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de synthèse des activités P2P vous permet de choisir le mode de groupement des données. Dans ce cas, les activités sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des activités P2P.
  
**Filtres du rapport de synthèse des activités P2P**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 17/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 17/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 13/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 17/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 17/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 13/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Tous les mois (il est possible d’afficher un maximum de 12 mois) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/17/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des activités P2P.
  
**Mesures du rapport de synthèse des activités P2P**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Toutes les heures** <br/> **Jour** <br/> **Toutes les semaines** <br/> **Mois** <br/> |Non  <br/> |Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 17/07/2015, la répartition horaire des activités d’enregistrement de l’utilisateur s’affiche pour cette date.  <br/> |
|**Nombre total de sessions P2P** <br/> |Non  <br/> |Nombre total de sessions P2P menées, quel qu’en soit le type.  <br/> |
|**Nombre total de sessions de messagerie instantanée P2P** <br/> |Non  <br/> |Nombre total de sessions de messagerie instantanée (IM) P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée P2P pour la période sélectionnée.  <br/> |
|**Nombre total de messages de messagerie instantanée P2P** <br/> |Non  <br/> |Nombre total de messages instantanés envoyés lors des sessions P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée P2P pour la période sélectionnée.  <br/> |
|**Nombre total de sessions audio P2P** <br/> |Non  <br/> |Nombre total d’appels audio P2P. Lorsque vous cliquez sur ce champ, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.  <br/> |
|**Nombre total de minutes par session audio P2P** <br/> |Non  <br/> |Temps total passé dans les sessions audio P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.  <br/> |
|**Nombre moyen de minutes par session audio P2P** <br/> |Non  <br/> |Temps moyen passé dans les sessions audio P2P. Calculé en divisant le temps total des sessions audio par le nombre total de sessions audio.  <br/> |
|**Nombre total de sessions vidéo P2P** <br/> |Non  <br/> |Nombre total d’appels vidéo P2P. Notez que les sessions vidéo sont également comptées comme des sessions audio : chaque session vidéo est comptée comme une seule session vidéo et une seule session audio. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.  <br/> |
|**Nombre total de minutes par session vidéo P2P** <br/> |Non  <br/> |Temps total passé dans les sessions vidéo P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.  <br/> |
|**Nombre moyen de minutes par session vidéo P2P** <br/> |Non  <br/> |Temps moyen passé dans les sessions vidéo P2P. Calculé en divisant le temps total des sessions vidéo par le nombre total de sessions vidéo.  <br/> |
|**Nombre total de sessions de transfert de fichiers P2P** <br/> |Non  <br/> |Nombre total de sessions P2P qui ont inclus des transferts de fichiers.  <br/> |
|**Nombre total de sessions de partage d’application P2P** <br/> |Non  <br/> |Nombre total de sessions P2P qui ont inclus un partage d’application.  <br/> |
   

