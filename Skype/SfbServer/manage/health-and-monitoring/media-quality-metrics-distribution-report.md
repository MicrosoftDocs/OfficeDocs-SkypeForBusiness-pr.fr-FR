---
title: Media Quality Metrics Distribution Report dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Résumé : Découvrez la qualité mesures du rapport de Distribution médias dans Skype pour Business Server.'
ms.openlocfilehash: 65fc10e1adaa32c2538f49d7c41fe6ee45a51c1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902270"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Media Quality Metrics Distribution Report dans Skype pour Business Server 
 
**Résumé :** Découvrez le Media qualité mesures du rapport de répartition dans Skype pour Business Server.
  
Le rapport de distribution des mesures de qualité des médias vous permet de consulter un graphique qui affiche les valeurs de distribution pour une mesure de la qualité de l’expérience, comme la gigue ou la perte de paquets. Par exemple, supposons que vos utilisateurs passent un total de 10 appels téléphoniques. Ces 10 appels présentent les délais d’aller-retour suivants :
  
|**Numéro de l’appel**|**Délai d’aller-retour (millisecondes)**|
|:-----|:-----|
|1  <br/> |50  <br/> |
|2  <br/> |50  <br/> |
|3  <br/> |50  <br/> |
|4  <br/> |50  <br/> |
|5  <br/> |50  <br/> |
|6  <br/> |50  <br/> |
|7  <br/> |50  <br/> |
|8  <br/> |4550.  <br/> |
|9  <br/> |50  <br/> |
|10  <br/> |50  <br/> |
   
Le délai d’aller-retour moyen est de 500 millisecondes (5 000 divisé par 10). Cinq cents millisecondes est un délai d’aller-retour extrêmement élevé. Par conséquent, vous pouvez penser que vous rencontrez un sérieux problème de surcharge du réseau. (Les délais d’aller-retour élevés sont généralement le résultat de surcharges au niveau du réseau.)
  
En réalité, 90 % de vos appels présentent d’excellents délais d’aller-retour. C’est à peine si vous avez passé un appel de mauvaise qualité qui a faussé les résultats globaux. Si vous tenez compte du délai d’aller-retour moyen, vous risquez de tirer une fausse conclusion.
  
Le rapport de distribution des mesures de qualité des médias vous permet de ne pas tirer de conclusions hâtives et erronées : il vous présente une répartition graphique d’une mesure précise (comme le délai d’aller-retour). Ces graphiques permettent de clarifier la situation, à savoir que vous avez passé neuf appels de très bonne qualité et un de mauvaise qualité. Vous souhaitez peut-être examiner plus en détail cet appel-ci. Cependant, le fait que 9 appels sur 10 étaient de bonne qualité semble indiquer qu’il n’existe aucune raison d’apporter des modifications radicales à votre réseau, au moins pas pour l’instant.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de distribution des mesures de qualité des médias.
  
**Filtres du rapport de distribution des mesures de qualité des médias**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Minimum sur l’axe x** <br/> |Plus petite valeur à afficher sur l’axe X du graphique.  <br/> |
|**Maximum sur l’axe x** <br/> |Plus grande valeur à afficher sur l’axe X du graphique.  <br/> |
|**Type d’accès** <br/> | Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Interne <br/>  Externe <br/> |
|**VPN** <br/> | Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  VPN <br/>  Non-VPN <br/> |
|**Type de réseau** <br/> | Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Câblé <br/>  Sans fil <br/> |
   

