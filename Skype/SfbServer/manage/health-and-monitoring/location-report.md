---
title: Rapport d’emplacement dans Skype Entreprise Server
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
ms.assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
description: 'Résumé : Découvrez le rapport d’emplacement dans Skype Entreprise Server.'
ms.openlocfilehash: afbbf54e913146326ee49e6db051869fa2ac7aca
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862401"
---
# <a name="location-report-in-skype-for-business-server"></a>Rapport d’emplacement dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport d’emplacement dans Skype Entreprise Server.
  
Le rapport d’emplacement fournit des informations sur les mesures de la qualité des appels regroupées par emplacement réseau (c’est-à-dire, par sous-réseau). Si vos utilisateurs rencontrent des problèmes avec leurs appels, ce rapport peut vous aider à déterminer si ces problèmes sont étendus ou s’ils sont largement réduits à un segment de réseau donné.
  
## <a name="accessing-the-location-report"></a>Accès au rapport d’emplacement

Le rapport d’emplacement est accessible à partir de la page d’accueil des rapports de surveillance. Vous pouvez accéder au rapport des listes d’appels en cliquant sur l’une des mesures suivantes :
  
- Volume d’appels
    
- Pourcentage d’appels médiocres
    
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’emplacement vous permet de filtrer des éléments comme l’emplacement duquel un appel provient ou s’il s’est produit sur une connexion  réseau câblée ou sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’emplacement.
  
**Filtres du rapport d’emplacement**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Emplacement de l’appelant** <br/> |Sous-réseau IP de l’utilisateur qui a émis l’appel. Vous pouvez uniquement sélectionner **[Tous]** pour indiquer tous les sous-réseaux.<br/> |
|**Emplacement de l’appelé** <br/> |Sous-réseau IP de l’utilisateur qui a reçu l’appel. Vous pouvez uniquement sélectionner **[Tous]** pour indiquer tous les sous-réseaux.<br/> |
|**Type de réseau** <br/> | Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Câblé <br/>  Sans fil <br/> |
|**VPN** <br/> | Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  VPN <br/>  Non VPN <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’emplacement.
  
**Mesures du rapport d’emplacement**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Sous-réseau de l’appelant** <br/> |Non  <br/> |Sous-réseau IP de l’utilisateur qui a émis l’appel.  <br/> |
|**Sous-réseau de l’appelé** <br/> |Non  <br/> |Sous-réseau IP de l’utilisateur qui a reçu l’appel.  <br/> |
|**Volume d’appels** <br/> |Oui  <br/> |Nombre total d’appels émis.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Oui  <br/> |Pourcentage d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Boucle (ms)** <br/> |Oui  <br/> |Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**Dégradation (MOS)** <br/> |Oui  <br/> |Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée). Une valeur de 0,5 ou moins signifie une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Dans Skype Entreprise Server, un ensemble d’algorithmes prévoit la façon dont les utilisateurs auraient évalué un appel.  <br/> Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un système d’extrémité surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Perte de paquets** <br/> |Oui  <br/> |Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Gigue** <br/> |Oui  <br/> |Gigue moyenne du délai d’arrivée entre les paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Taux de masquage de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Taux d’étirement de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.  <br/> |
|**Taux de compression de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.  <br/> |
   

