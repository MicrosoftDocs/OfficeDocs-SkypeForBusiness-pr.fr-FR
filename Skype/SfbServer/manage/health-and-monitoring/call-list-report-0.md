---
title: Rapport de liste d’appels dans Skype Entreprise Server
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
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Résumé : Découvrez le rapport de liste d’appels utilisé dans Skype Entreprise Server.'
ms.openlocfilehash: d56374fa317f6c7b132a9d33dcf9fef966c55625
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864841"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Rapport de liste d’appels dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de liste d’appels utilisé dans Skype Entreprise Server.
  
Le rapport des listes d’appels fournit des mesures de qualité de l’expérience (QoE) pour les appels individuels effectués et reçus dans votre organisation. Notez que les mesures réelles signalées dépendent de la façon dont vous accédez au rapport liste des appels. Par exemple, si vous ouvrez le rapport à partir du rapport de périphérique dans [Skype Entreprise Server](device-report.md), vous verrez des mesures telles que les suivantes, qui sont également signalées dans le rapport de périphérique :
  
- Microphone de l’appelant
    
- Haut-parleur de l’appelant
    
- Microphone de l’appelé
    
- Haut-parleur de l’appelé
    
- Ratio de la durée du basculement vocal 
    
Toutefois, si vous ouvrez le rapport des listes d’appels à partir du rapport d’emplacement dans [Skype Entreprise Server](location-report.md), vous ne verrez aucune de ces mesures . Au lieu de cela, vous verrez des mesures comme celles-ci :
  
- Boucle (ms)
    
- Dégradation (MOS)
    
- Perte de paquets
    
- Gigue (ms)
    
Il s’adresse aux mesures signalées dans le rapport d’emplacement. Toutefois, à partir du rapport de liste d’appels, vous pouvez toujours cliquer sur la mesure Détail pour fournir des informations QoE complètes pour tout appel.
  
## <a name="accessing-the-call-list-report"></a>Accès au rapport de liste d’appels

Le rapport de liste d’appels est accessible à partir de l’un des rapports suivants :
  
- Rapport [d’emplacement en Skype Entreprise Server](location-report.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres)
    
- Rapport [de périphérique en Skype Entreprise Server](device-report.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres)
    
- Le [rapport de synthèse de la](summary.md) qualité des médias Skype Entreprise Server (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres)
    
- Rapport [sur les performances du serveur Skype Entreprise Server](server-performance.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres)
    
À partir du rapport de liste d’appels, vous pouvez accéder au rapport détaillé des appels [Skype Entreprise Server](call-detail-report.md) en cliquant sur la mesure Détail.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Utilisation du rapport des listes d’appels au mieux

Si vous ne vous souvenez pas de ce que mesurent réellement certaines mesures du rapport de liste d’appels (telles que la durée du basculement vocal ratio), maintenez la souris au-dessus de l’étiquette de mesure . Une info-conseil s’affiche pour vous donner une brève description de la mesure.
  
## <a name="filters"></a>Filtres

Aucune. Vous ne pouvez pas filtrer le rapport de liste d’appels.
  
## <a name="metrics"></a>Mesures

Le tableau suivant répertorie les informations fournies dans le rapport des listes d’appels pour chaque appel.
  
**Mesures du rapport des listes d’appels**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Détails** <br/> |Non  <br/> |Lorsque vous cliquez sur cet élément, le rapport affiche des informations supplémentaires sur l’appel.  <br/> |
|**Caller** <br/> |Oui  <br/> |Adresse SIP de la personne qui a initié l’appel.  <br/> |
|**Appelé** <br/> |Oui  <br/> |Adresse SIP de la personne qui a été appelée.  <br/> |
|**Heure de début** <br/> |Oui  <br/> |Date et heure de début de l’appel.  <br/> |
|**Heure de fin** <br/> |Oui  <br/> |Date et heure de fin de l’appel.  <br/> |
|**Agent utilisateur de l’appelant** <br/> |Oui  <br/> |Logiciel utilisé par le point de terminaison de la personne qui a initié l’appel.  <br/> |
|**Agent utilisateur de l’appelé** <br/> |Oui  <br/> |Logiciel utilisé par le point de terminaison de la personne qui a été appelée.  <br/> |
|**Boucle (ms)** <br/> |Oui  <br/> |Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**Dégradation (MOS)** <br/> |Oui  <br/> |Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée). Une valeur de 0,5 ou moins signifie une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Dans Skype Entreprise Server, un ensemble d’algorithmes prévoit la façon dont les utilisateurs auraient évalué un appel.  <br/> Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un système d’extrémité surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Perte de paquets** <br/> |Oui  <br/> |Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Gigue** <br/> |Oui  <br/> |Gigue moyenne du délai d’arrivée entre les paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Taux de masquage de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Taux d’étirement de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.  <br/> |
|**Taux de compression de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.  <br/> |
|**Connectivité** <br/> |Oui  <br/> | Type de lien de communication sans fil. En règle générale, il s’agit de l’une des suivantes : <br/>  Relais <br/>  Direct <br/> |
   

