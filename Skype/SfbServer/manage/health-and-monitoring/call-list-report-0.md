---
title: Rapport de liste des appels dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Résumé : Découvrez le rapport liste des appels utilisés dans Skype pour Business Server.'
ms.openlocfilehash: 3e9b115edc92c911029570c6b69d589db64533af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902761"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Rapport de liste des appels dans Skype pour Business Server
 
**Résumé :** Découvrez le rapport liste des appels utilisés dans Skype pour Business Server.
  
Le rapport Liste des appels fournit des métriques de Qualité de l’expérience pour chaque appel émis et reçu dans votre organisation. Notez que les mesures réelles indiquées dépendent de la façon dont vous accédez au rapport Liste des appels. Par exemple, si vous ouvrez le rapport à partir du [Rapport de périphérique dans Skype pour Business Server](device-report.md), vous verrez des mesures telles que la suivante, les mesures qui figurent également dans le rapport de périphérique :
  
- Microphone de l’appelant
    
- Haut-parleur de l’appelant
    
- Microphone de l’appelé
    
- Haut-parleur de l’appelé
    
- Ratio de la durée du basculement vocal 
    
Toutefois, si vous ouvrez le rapport liste des appels à partir du [Rapport d’emplacement dans Skype pour Business Server](location-report.md), vous ne verrez aucune de ces mesures ; au lieu de cela, vous verrez des mesures telles que les :
  
- Boucle (ms)
    
- Dégradation (MOS)
    
- Perte de paquets
    
- Gigue (ms)
    
Il s’agit des mesures signalées dans le Rapport d’emplacement. Cependant, dans le rapport Liste des appels, vous pouvez toujours cliquer sur la mesure Détail pour fournir des informations de qualité de l’expérience complète pour n’importe quel appel.
  
## <a name="accessing-the-call-list-report"></a>Accès au rapport Liste des appels

Le rapport Liste des appels est accessible à partir des rapports suivants :
  
- Le [Rapport d’emplacement dans Skype pour Business Server](location-report.md) (en cliquant sur le volume d’appels ou la mesure de pourcentage d’appels médiocres)
    
- Le [Rapport de périphérique dans Skype pour Business Server](device-report.md) (en cliquant sur le volume d’appels ou la mesure de pourcentage d’appels médiocres)
    
- Le [Media Quality Summary Report dans Skype pour Business Server](summary.md) (en cliquant sur le volume d’appels ou la mesure de pourcentage d’appels médiocres)
    
- Le [Rapport de performances du serveur dans Skype pour Business Server](server-performance.md) (en cliquant sur le volume d’appels ou la mesure de pourcentage d’appels médiocres)
    
À partir de dans le rapport liste des appels vous pouvez accéder au [Call Detail Report dans Skype pour Business Server](call-detail-report.md) en cliquant sur la mesure détail.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Utilisation optimale du rapport Liste des appels

Si vous ne vous souvenez pas de la signification de certaines des mesures du rapport Liste des appels (par exemple, Ratio de la durée du basculement vocal), maintenez le pointeur de la souris sur l’étiquette de la mesure ; une info-bulle s’affiche et fournit une brève description de la mesure.
  
## <a name="filters"></a>Filtres

Aucun. Il est impossible de filtrer le rapport de liste d’appels.
  
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de liste d’appels pour chaque appel.
  
**Mesures du rapport de liste d’appels**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Détails** <br/> |Non  <br/> |Lorsque vous cliquez sur cet élément, le rapport affiche des informations supplémentaires sur l’appel.  <br/> |
|**Appelant** <br/> |Oui  <br/> |Adresse IP de la personne ayant initié l’appel.  <br/> |
|**Appelé** <br/> |Oui  <br/> |Adresse IP de la personne qui a été appelée.  <br/> |
|**Heure de début** <br/> |Oui  <br/> |Date et heure de début de l’appel.  <br/> |
|**Heure de fin** <br/> |Oui  <br/> |Date et heure de fin de l’appel.  <br/> |
|**Agent utilisateur de l’appelant** <br/> |Oui  <br/> |Logiciel utilisé par le point de terminaison de la personne ayant initié l’appel.  <br/> |
|**Agent utilisateur de l’appelé** <br/> |Oui  <br/> |Logiciel utilisé par le point de terminaison de la personne qui a été appelée.  <br/> |
|**Boucle (ms)** <br/> |Oui  <br/> |Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**Dégradation (MOS)** <br/> |Oui  <br/> |Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée). Une valeur de 0,5 ou moins signifie une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Dans Skype pour Business Server, un ensemble d’algorithmes prévoir la façon dont les utilisateurs est comme un appel.  <br/> Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un point de terminaison surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Perte de paquets** <br/> |Oui  <br/> |Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Gigue** <br/> |Oui  <br/> |Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Taux de masquage de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Taux d’étirement de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.  <br/> |
|**Taux de compression de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.  <br/> |
|**Connectivité** <br/> |Oui  <br/> | Type de liaison de communication sans fil. Il s’agit en général de l’un des types suivants : <br/>  Relais <br/>  Direct <br/> |
   

