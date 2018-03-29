---
title: Rapport de tendance de la qualité des médias serveur dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
description: 'Résumé : Découvrez le serveur média qualité rapport tendances dans Skype pour Business Server 2015.'
ms.openlocfilehash: e257243eed1934cecc39f1feec26b3d83862e8c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="server-media-quality-trend-report-in-skype-for-business-server-2015"></a>Rapport de tendance de la qualité des médias serveur dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur le serveur média qualité rapport tendances dans Skype pour Business Server 2015.
  
Le rapport de tendance générale de la qualité des médias serveur vous permet de comparer de façon graphique la qualité de l’expérience sur 5 serveurs maximum, par exemple le volume d’appel, le pourcentage d’appels médiocres, la perte de paquet et la gigue. Cela permet d’identifier plus facilement les serveurs dont les performances sont médiocres, les serveurs qui sont sous-utilisés ou sur-utilisés.
  
## <a name="accessing-the-server-media-quality-trend-report"></a>Accès au rapport de tendance générale de la qualité des médias serveur

Le rapport de tendance générale de la qualité des médias serveur est accessible à partir de l’un des rapports suivants :
  
- [Rapport de performances du serveur dans Skype pour Business Server 2015](server-performance.md) (en cliquant sur la mesure de tendance)
    
- [Appelez le rapport détaillé dans Skype pour Business Server 2015](call-detail-report.md) (en cliquant sur le A / V edge métrique du serveur. Si l’appelant ou l’appelé est un serveur, vous pouvez également accéder au rapport de tendance de la qualité des médias serveur en cliquant sur le nom du point de terminaison.)
    
## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Utilisation efficace du rapport de tendance de la qualité des médias serveur

Lorsque vous cliquez sur la mesure de l’évolution sur le [Rapport de performances de serveur dans Skype pour Business Server 2015](server-performance.md) pour un serveur spécifique, le rapport de tendances de qualité Media Server s’ouvre. Cependant, vous obtenez une instance vide de ce rapport ; le serveur que vous sélectionnez ne sera pas affiché à l’écran. Vous devez sélectionner ce serveur dans la liste déroulante Serveurs. Notez que la liste déroulante Serveurs propose une option Tout sélectionner. Cette option ne sera pas disponible si vous avez plus de 5 serveurs, en effet le rapport de tendance de la qualité des médias serveur ne peut afficher que 5 serveurs à la fois.
  
Sur les graphiques affichés par le rapport de tendances de qualité Media Server, les points intitulée appeler un Volume et une faible pourcentage d’appel sont lien direct ; cliquer sur un point sur le graphique ouvre une instance de l' [Appel de rapport liste dans Skype pour Business Server 2015](call-list-report-0.md) affichant le nombre total d’appels (appels faibles ou) pour la période spécifiée.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de tendance de la qualité des médias serveur.
  
**Filtres de rapport de tendance serveur média qualité**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Intervalle** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 07/08/2015 et une date de fin le 28/09/2015, les données s’affichent pour les jours compris entre le 07/08/2015 12:00 AM et le 07/09/2015 12:00 AM (c’est-à-dire, un total de 31 jours de données). <br/> |
|**Type de serveur** <br/> | Type de serveur de l’appel. Les valeurs autorisées sont les suivantes : <br/>  Serveur de médiation <br/>  Serveur de conférence A/V <br/>  Serveur Edge A/V <br/>  Passerelle (serveur de médiation) <br/>  Passerelle (contournement du serveur de médiation) <br/>  Serveur de conférence AS <br/> |
|**Serveurs** <br/> |Nom du serveur de la session ; cette liste déroulante est automatiquement remplie en fonction de la valeur du filtre Type de serveur. Vous pouvez sélectionner jusqu’à 5 serveurs différents lors de la création d’un rapport.  <br/> |
|**Type d’accès** <br/> | Indique si le participant était connecté au réseau interne ou à partir d’un réseau externe. Les valeurs autorisées sont les suivantes : <br/>  [Tous] <br/>  Interne <br/>  Externe <br/> |
|**Type de réseau** <br/> | Indique le type de réseau auquel le participant était connecté. Les valeurs autorisées sont les suivantes : <br/>  [Tous] <br/>  Câblé <br/>  Sans fil <br/> |
|**VPN** <br/> | Indique si un participant externe utilisait une connexion VPN lors de la session. Les valeurs autorisées sont les suivantes : <br/>  [Tous] <br/>  VPN <br/>  Non-VPN <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de tendance de la qualité des médias serveur.
  
**Mesures de rapport serveur média qualité tendance**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Volume d’appels** <br/> |Non  <br/> |Nombre total d’appels.  <br/> |
|**Dégradation (MOS)** <br/> |Non  <br/> |Taux moyen de dégradation de la note MOS (note moyenne d’opinion) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée) ; une valeur inférieure ou égale à 0,5 indique une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion étaient calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Skype pour Business Server utilise un ensemble d’algorithmes à prévoir la manière dont les utilisateurs aurait été attribué un appel.  <br/> Les valeurs de dégradation élevées peuvent avoir plusieurs causes : une congestion, un dépassement de la bande passante disponible, une congestion/interférence dans la liaison sans fil ou bien la surcharge d’un serveur multimédia ou d’un système d’extrémité. Ces valeurs se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Non  <br/> |Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Boucle (ms)** <br/> |Non  <br/> |Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un point de terminaison. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**Perte de paquets** <br/> |Non  <br/> |Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Gigue (ms)** <br/> |Non  <br/> |Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Taux de masquage de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Taux d’étirement de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.  <br/> |
|**Taux de compression de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.  <br/> |
   

