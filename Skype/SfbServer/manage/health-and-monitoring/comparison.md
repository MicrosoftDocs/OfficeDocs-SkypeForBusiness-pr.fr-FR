---
title: Rapport comparatif de la qualité des médias dans Skype Entreprise Server
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
ms.assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
description: 'Résumé : Découvrez le rapport comparatif de la qualité des médias dans Skype Entreprise Server.'
ms.openlocfilehash: 7814075c59428da25bcdaf4f0f18b0240d63360a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773604"
---
# <a name="media-quality-comparison-report-in-skype-for-business-server"></a>Rapport comparatif de la qualité des médias dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport comparatif de la qualité des médias dans Skype Entreprise Server.
  
Le rapport comparatif de la qualité des médias vous permet de comparer les valeurs de qualité des appels pour différents types d’appels audio (par exemple, des appels passés sur un réseau sans fil par rapport à ceux effectués via une connexion câblée).
  
## <a name="accessing-the-media-quality-comparison-report"></a>Accès au rapport comparatif de la qualité des médias

Le rapport comparatif de la qualité des médias est accessible à partir de la page d’accueil des rapports de surveillance. 
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport comparatif de la qualité des médias.
  
**Filtres du rapport comparatif de la qualité des médias**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines commencent le dimanche et se terminent le samedi.  <br/> |
|**Appels** <br/> | Type d’appel à utiliser en tant que principal élément de comparaison. Les valeurs autorisées sont les suivantes : <br/>  [Tous] <br/>  Externe <br/>  Interne <br/>  VPN <br/>  Non VPN <br/>  Câblé <br/>  Sans fil <br/>  Externe et câblé <br/>  Externe et sans fil <br/>  Externe et VPN <br/>  Externe et non VPN <br/>  Interne et câblé <br/>  Interne et sans fil <br/> |
|**Comparer avec les appels** <br/> | Type d’appel à utiliser en tant qu’élément de comparaison secondaire. Les valeurs autorisées sont les suivantes : <br/>  [Tous] <br/>  Externe <br/>  Interne <br/>  VPN <br/>  Non VPN <br/>  Câblé <br/>  Sans fil <br/>  Externe et câblé <br/>  Externe et sans fil <br/>  Externe et VPN <br/>  Externe et non VPN <br/>  Interne et câblé <br/>  Interne et sans fil <br/> |
|**Interval** <br/> | Intervalle de temps. Sélectionnez l’une des options suivantes : <br/>  Toutes les heures (il est possible d’afficher un maximum de 25 heures) <br/>  Tous les jours (il est possible d’afficher un maximum de 31 jours) <br/>  Toutes les semaines (il est possible d’afficher un maximum de 12 semaines) <br/>  Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début du 7/07/2015 et une date de fin le 28/02/2015, les données s’affichent pour les jours 8/7/2015 de 12:00 au 07/09/2015 12:00 (c’est-à-dire, un total de 31 jours de données). <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport comparatif de la qualité des médias.
  
**Mesures du rapport comparatif de la qualité des médias**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Volume d’appels** <br/> |Non  <br/> |Nombre total d’appels.  <br/> |
|**Dégradation (MOS)** <br/> |Non  <br/> |Niveau moyen de dégradation de la note MOS (note moyenne d’opinion) au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée) ; une valeur inférieure ou égale à 0,5 indique une dégradation acceptable. Historiquement, les scores d’opinion moyennes ont été calculés en faisant évaluer la qualité d’un appel par les utilisateurs sur une échelle de 1 à 5. Skype Entreprise Server utilise un ensemble d’algorithmes pour prédire la façon dont les utilisateurs auraient évalué un appel.  <br/> Les valeurs de dégradation élevées peuvent avoir plusieurs causes : une congestion, un dépassement de la bande passante disponible, une congestion/interférence dans la liaison sans fil ou bien la surcharge d’un serveur multimédia ou d’un système d’extrémité. Ces valeurs se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Non  <br/> |Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Boucle (ms)** <br/> |Non  <br/> |Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**Perte de paquets** <br/> |Non  <br/> |Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Gigue (ms)** <br/> |Non  <br/> |Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Taux de masquage de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Taux d’étirement de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.  <br/> |
|**Taux de compression de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.  <br/> |
   

