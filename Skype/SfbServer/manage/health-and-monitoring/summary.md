---
title: Rapport qualité des médias résumé dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
description: 'Résumé : Découvrez le média qualité rapport de synthèse dans Skype pour Business Server.'
ms.openlocfilehash: dfe59d4c115f8396625979cf7c7dc88ac4f52ee5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197897"
---
# <a name="media-quality-summary-report-in-skype-for-business-server"></a>Rapport qualité des médias résumé dans Skype pour Business Server
 
**Résumé :** Découvrez le média qualité rapport de synthèse dans Skype pour Business Server.
  
Le rapport de synthèse de la qualité des médias permet d’analyser la qualité des appels au sein de votre organisation : ce rapport fournit des mesures d’appel de qualité de l’expérience (QoE) détaillées décomposées selon les catégories suivantes :
  
- Appels d’égal à égal UC (par exemple, un Skype pour les entreprises à Skype pour l’appel de l’entreprise)
    
- Sessions de conférence UC
    
- Sessions de conférence RTC
    
- Appels RTC : contournement du média
    
- Appels RTC (sans contournement) : partie UC
    
- Appels RTC (sans contournement) : partie passerelle
    
- Autres types d’appels
    
Quand vous ouvrez le rapport pour la première fois, une synthèse des informations pour chaque catégorie s’affiche. Sans quitter le rapport, vous pouvez développer chaque catégorie à examiner des sous-catégories telles que les appels passés à partir d’Office Communicator 2007 R2 à Skype pour les entreprises. Vous pouvez développer également ces sous-catégories pour afficher des détails sur chaque appel passé dans cette sous-catégorie.
  
Dans Skype pour Business Server davantage le rapport de synthèse de qualité des médias décompose les données en trois types d’appel : appels audio, les appels vidéo et les appels de partage d’application. Chaque type d’appel correspond à une section du rapport, et dispose d’un ensemble personnalisé de mesures des appels.
  
Le rapport de synthèse de la qualité des médias vous permet d’appliquer des filtres pour comparer la qualité des appels entre les appels câblés et les appels sans fil, les appels internes et externes, les appels VPN et non VPN.
  
## <a name="accessing-the-media-quality-summary-report"></a>Accès au rapport de synthèse de la qualité des médias

Le rapport de synthèse de la qualité des médias est accessible à partir de la page d’accueil Rapports de surveillance. Vous pouvez accéder au [Rapport liste des appels dans Skype pour Business Server](call-list-report-0.md) en cliquant sur une des mesures suivantes :
  
- Volume d’appels
    
- Pourcentage d’appels médiocres
    
De plus, vous pouvez accéder au Rapport de distribution des mesures de qualité des médias en cliquant sur l’une des mesures d’appel audio suivantes :
  
- Boucle (ms)
    
- Dégradation (MOS)
    
- Perte de paquets
    
- Gigue (ms)
    
- Taux de masquage de la réparation
    
- Taux d’étirement de la réparation
    
- Taux de compression de la réparation
    
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, grâce au rapport de synthèse de la qualité des médias, vous pouvez filtrer les données renvoyées selon des éléments précis, tels que le type d’accès (à savoir « accès interne » par comparaison à « accès externe ») ou la connexion réseau câblée/sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de la qualité des médias.
  
**Filtres du rapport de synthèse de la qualité des médias**

|**Nom**|**Description**|
|:-----|:-----|
|**De** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**À** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 07/07/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 07/07/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 03/07/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Type d’accès** <br/> | Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Interne <br/>  Externe <br/> |
|**Type de réseau** <br/> | Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  Câblé <br/>  Sans fil <br/> |
|**VPN** <br/> | Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes : <br/>  [Tous] <br/>  VPN <br/>  Non-VPN <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse de la qualité des médias.
  
**Mesures du rapport de synthèse de la qualité des médias : synthèse des appels audio**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’appel/type de point de terminaison** <br/> |Non  <br/> | Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants : <br/>  Appels P2P UC <br/>  Sessions de conférence UC <br/>  Sessions de conférence RTC <br/>  Appels RTC : contournement du média <br/>  Appels RTC (sans contournement) : partie UC <br/>  Appels RTC (sans contournement) : partie passerelle <br/>  Autres types d’appels <br/> |
|**Volume d’appels** <br/> |Non  <br/> |Nombre total d’appels par type d’appel.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Non  <br/> |Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Volume d’appels (appels sans fil)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion sans fil.  <br/> |
|**Volume d’appels (appels VPN)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion VPN.  <br/> |
|**Volume d’appels (appels externes)** <br/> |Non  <br/> |Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).  <br/> |
|**Boucle (ms)** <br/> |Non  <br/> |Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**Dégradation (MOS)** <br/> |Non  <br/> |Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée). Une valeur de 0,5 ou moins signifie une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Dans Skype pour Business Server un ensemble d’algorithmes prévoir la façon dont les utilisateurs est comme un appel.  <br/> Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un point de terminaison surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Perte de paquets** <br/> |Non  <br/> |Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Gigue (ms)** <br/> |Non  <br/> |Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Taux de masquage de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Taux d’étirement de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.  <br/> |
|**Taux de compression de la réparation** <br/> |Non  <br/> |Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.  <br/> |
   
**Mesures du rapport de synthèse de la qualité des médias : synthèse des appels vidéo**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’appel/type de point de terminaison** <br/> |Non  <br/> | Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants : <br/>  Appels P2P UC <br/>  Sessions de conférence UC <br/>  Sessions de conférence RTC <br/>  Appels RTC : contournement du média <br/>  Appels RTC (sans contournement) : partie UC <br/>  Appels RTC (sans contournement) : partie passerelle <br/>  Autres types d’appels <br/> |
|**Volume d’appels** <br/> |Non  <br/> |Nombre total d’appels par type d’appel.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Non  <br/> |Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Volume d’appels (appels sans fil)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion sans fil.  <br/> |
|**Volume d’appels (appels VPN)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion VPN.  <br/> |
|**Volume d’appels (appels externes)** <br/> |Non  <br/> |Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).  <br/> |
|**Vitesse de transmission moyenne (Kbit/s)** <br/> |Non  <br/> |Vitesse de transmission vidéo moyenne (en kilobits par seconde).  <br/> |
|**Vitesse de transmission faible (%)** <br/> |Non  <br/> |Pourcentage de l’appel où la vitesse de transmission était faible.  <br/> |
|**Perte de paquets sortante** <br/> |Non  <br/> |Perte de paquets RTP (Real-Time Transport Protocol) pour les paquets sortants. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Image figée (%)** <br/> |Non  <br/> |Pourcentage de trames « figer ». Dans une image figée, la vidéo cesse d’avancer tandis que la partie audio de l’appel continue.  <br/> |
|**Fréquence d’images moyenne sortante** <br/> |Non  <br/> |Fréquence d’images moyenne pour les transmissions sortantes pendant l’appel.  <br/> |
|**Fréquence d’images moyenne entrante** <br/> |Non  <br/> |Fréquence d’images moyenne pour les transmissions entrantes pendant l’appel.  <br/> |
|**Fréquence d’images basse entrante (%)** <br/> |Non  <br/> |Pourcentage de l’appel où la vitesse de transmission pour la vidéo entrante était faible.  <br/> |
|**Intégrité des clients (%)** <br/> ||Indique l’intégrité relative du périphérique client pendant l’appel.  <br/> |
   
**Mesures du rapport de synthèse de la qualité des médias : synthèse des appels de partage d’application**

|**Nom**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’appel/type de point de terminaison** <br/> |Non  <br/> | Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants : <br/>  Appels P2P UC <br/>  Sessions de conférence UC <br/>  Sessions de conférence RTC <br/>  Appels RTC : contournement du média <br/>  Appels RTC (sans contournement) : partie UC <br/>  Appels RTC (sans contournement) : partie passerelle <br/>  Autres types d’appels <br/> |
|**Volume d’appels** <br/> |Non  <br/> |Nombre total d’appels par type d’appel.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Non  <br/> |Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Volume d’appels (appels sans fil)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion sans fil.  <br/> |
|**Volume d’appels (appels VPN)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion VPN.  <br/> |
|**Volume d’appels (appels externes)** <br/> |Non  <br/> |Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).  <br/> |
|**Gigue (ms)** <br/> |Non  <br/> |Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Unilatéral relatif moyen** <br/> |Non  <br/> |Retard unilatéral relatif moyen entre deux points de terminaison du média. Il s’agit d’une mesure de latence sur un seul tronçon.  <br/> |
|**Latence moyenne de traitement des mosaïques RDP** <br/> |Non  <br/> |Latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage. Une moyenne élevée équivaut à une expérience de visionnage plus longue et inclut une latence du réseau. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés.  <br/> |
|**Nombre total de mosaïques altérées (%)** <br/> |Non  <br/> |Pourcentage total de mosaïques RDP altérées.  <br/> |
   

