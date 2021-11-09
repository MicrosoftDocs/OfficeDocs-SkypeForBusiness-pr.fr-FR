---
title: Rapport de distribution des mesures de qualité des médias Skype Entreprise Server
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
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Résumé : Découvrez le rapport de distribution des mesures de qualité des médias dans Skype Entreprise Server.'
ms.openlocfilehash: 00899681190e532af971c719c2e81f655facf7ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862311"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>Rapport de distribution des mesures de qualité des médias Skype Entreprise Server 
 
**Résumé :** Découvrez le rapport de distribution des mesures de qualité des médias dans Skype Entreprise Server.
  
Le rapport de distribution des mesures de qualité des médias vous permet de voir un graphique qui affiche les valeurs de distribution d’une mesure de qualité de l’expérience telle que la gigue ou la perte de paquets. Par exemple, supposons que vos utilisateurs font un total de 10 appels téléphoniques ; Ces 10 appels indiquent les temps d’aller-retour suivants :
  
|**Numéro d’appel**|**Durée de l’aller-retour (millisecondes)**|
|:-----|:-----|
|1  <br/> |50  <br/> |
|2  <br/> |50  <br/> |
|3  <br/> |50  <br/> |
|4  <br/> |50  <br/> |
|5  <br/> |50  <br/> |
|6   <br/> |50  <br/> |
|7   <br/> |50  <br/> |
|8   <br/> |4550  <br/> |
|9   <br/> |50  <br/> |
|10  <br/> |50  <br/> |
   
La moyenne de ces allers-retours est de 500 millisecondes (5 000 divisé par 10). Cinq cent millisecondes est une durée d’aller-retour extrêmement longue . Par conséquent, vous pouvez penser que vous avez un sérieux problème de congestion du réseau. (Les temps d’aller-retour longs sont généralement le résultat de réseaux surchargés.)
  
En réalité, 90 % de vos appels ont connu d’excellents allers-retours . vous n’avez eu qu’un seul appel de mauvaise qualité qui a biaisé les résultats globaux. Si vous regardez uniquement la durée moyenne des allers-retours, vous risquez de tirer une conclusion très erronée.
  
Le rapport de distribution des mesures de qualité des médias vous permet d’éviter de tirer de mauvaises conclusions en vous présentant une distribution graphique d’une mesure spécifiée (par exemple, durée de l’aller-retour). Ces graphiques peuvent vous aider à comprendre que vous avez reçu neuf très bons appels et un appel très mauvais. Certes, il se peut que vous vouliez toujours examiner cet appel plus en détail . Toutefois, le fait que 9 des 10 appels ont été très bons suggère qu’il n’y a aucune raison d’apporter des modifications radicales à votre réseau, du moins pas à ce stade.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de distribution des mesures de qualité des médias.
  
**Filtres du rapport de distribution des mesures de qualité des médias**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Minimum dans l’axe x** <br/> |Valeur la plus faible à afficher sur l’axe X du graphique.  <br/> |
|**Maximum dans l’axe x** <br/> |Valeur la plus élevée à afficher sur l’axe X du graphique.  <br/> |
|**Type d’accès** <br/> | Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Interne <br/>  Externe <br/> |
|**VPN** <br/> | Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  VPN <br/>  Non VPN <br/> |
|**Type de réseau** <br/> | Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Fil de fer <br/>  Sans fil <br/> |
   

