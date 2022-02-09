---
title: Rapport sur les performances du serveur Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
description: 'Résumé : Découvrez le rapport sur les performances du serveur dans Skype Entreprise Server.'
ms.openlocfilehash: 21bb6dbc462633d3d5620d63389b72a9b4d49a07
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396536"
---
# <a name="server-performance-report-in-skype-for-business-server"></a>Rapport sur les performances du serveur Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de performances du serveur dans Skype Entreprise Server.
  
Le rapport de performances du serveur fournit une liste des serveurs Skype Entreprise Server qui ont connu le pourcentage d’appels médiocres le plus élevé. Ce rapport est décomposé en fonction des types de serveur, et propose des statistiques séparées pour les types suivants :
  
- Serveur de médiation
    
- Serveur de conférence A/V
    
- Serveur Edge A/V
    
- Passerelle (serveur de médiation)
    
- Passerelle (contournement du serveur de médiation)
    
- Vidéo (y compris les mesures vidéo pour les serveurs de conférence A/V et les serveurs Edge A/V)
    
- Partage d’application (y compris les mesures de partage d’application pour les serveurs de conférence A/V et les serveurs Edge A/V)
    
Il est important de noter que le classement indiqué dans ce rapport est relatif. Par exemple, supposons que le serveur ayant les pires performances a reçu un appel médiocre sur les 1 000 passés. Ce pourcentage de 0,1 est plus qu’acceptable. Cependant, s’il s’agit du serveur ayant les pires performances (c’est-à-dire que les autres serveurs ont un pourcentage d’appels médiocres inférieur à 0,1 %), ce serveur s’affichera dans le rapport de performances du serveur.
  
## <a name="accessing-the-server-performance-report"></a>Accès au rapport de performances du serveur

Le rapport de performances du serveur est accessible à partir de la page d’accueil Rapports de surveillance. Vous pouvez descendre dans le rapport des listes d’Skype Entreprise Server [en](call-list-report-0.md) cliquant sur l’une des mesures suivantes :
  
- Volume d’appels
    
- Pourcentage d’appels médiocres
    
De plus, vous pouvez accéder au rapport de tendance de la qualité des médias serveur en cliquant sur la mesure suivante :
  
- Trend
    
## <a name="making-the-best-use-of-the-server-performance-report"></a>Utilisation du rapport de performances du serveur

Le rapport de performances du serveur fournit plusieurs moyens pour filtrer les données ; par exemple, vous pouvez filtrer sur un type de réseau (appels passés via une connexion câblée ou sans fil) et un type d’accès (appels passés à l’intérieur du pare-feu ou à l’extérieur). Il est conseillé d’utiliser ces filtres quand vous affichez le rapport de performances du serveur. Par exemple, vous avez un serveur de médiation avec un pourcentage d’appels médiocre de 3,24 %. Si vous considérez uniquement les appels sans fil, ce même serveur peut avoir un pourcentage d’appels médiocres de 20 %. Cela signifie que ce serveur ne gère pas bien les appels sans fil, mais ce problème peut être partiellement masqué par les appels câblés qui ne posent pas de problème.
  
## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le rapport de performances du serveur vous permet par exemple de filtrer les données renvoyées par type de serveur ou type de réseau (câblé ou sans fil). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les données sont groupées par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de performances du serveur.
  
**Filtres de rapport de performances du serveur**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines commencent le dimanche et se terminent le samedi.  <br/> |
|**Type de serveur** <br/> |Indique le type de serveur dont les performances doivent être rapportées. Sélectionnez l’une des options suivantes :  <br/> [Tous] Serveur Edge A/V du serveur de médiation A/V |
|**N premiers** <br/> |Indique le nombre de serveurs (sur la base du pourcentage d’appels médiocres) à afficher dans chaque catégorie. Par exemple, si vous sélectionnez **5**, les cinq serveurs ayant les performances les plus médiocres sont affichés. Sélectionnez l’une des options suivantes :<br/> [Tous] 5 10 |
|**Type d’accès** <br/> |Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :  <br/> [Tous] Interne externe |
|**Type de réseau** <br/> |Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :  <br/> [Tous] Fil câblé sans fil |
|**VPN** <br/> |Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :  <br/> [Tous] VPN non VPN |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de performances du serveur.
  
**Mesures du rapport de performances du serveur : synthèse des appels audio**

|**Name**|**Tri possible**|**Description**|
|:-----|:-----|:-----|
|**Serveur** <br/> |Non  <br/> |Nom/adresse IP du serveur  <br/> |
|**Volume d’appels** <br/> |Non  <br/> |Nombre total d’appels effectués.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Non  <br/> |Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Boucle (ms)** <br/> |Oui  <br/> |Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.  <br/> Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.  <br/> |
|**Dégradation (MOS)** <br/> |Oui  <br/> |Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée). Une valeur de 0,5 ou moins signifie une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Dans Skype Entreprise Server, le serveur de surveillance utilise un ensemble d’algorithmes pour prédire la façon dont les utilisateurs auraient évalué un appel.  <br/> Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un système d’extrémité surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Perte de paquets** <br/> |Oui  <br/> |Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Gigue (ms)** <br/> |Oui  <br/> |Gigue moyenne du délai d’arrivée entre les paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Taux de masquage de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.  <br/> |
|**Taux d’étirement de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.  <br/> |
|**Taux de compression de la réparation** <br/> |Oui  <br/> |Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.  <br/> |
   
**Mesures du rapport de performances du serveur : synthèse des appels vidéo**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’appel/type de système d’extrémité** <br/> |Non  <br/> | Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants : <br/>  Appels d’égal à égal UC <br/>  Sessions de conférence UC <br/>  Sessions de conférence PSTN <br/>  Appels PSTN : contournement du média <br/>  Appels PSTN (sans contournement) : partie UC <br/>  Appels PSTN (sans contournement) : partie passerelle <br/>  Autres types d’appels <br/> |
|**Volume d’appels** <br/> |Non  <br/> |Nombre total d’appels par type d’appel.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Non  <br/> |Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Volume d’appels (appels sans fil)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion sans fil.  <br/> |
|**Volume d’appels (appels VPN)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion VPN.  <br/> |
|**Volume d’appels (appels externes)** <br/> |Non  <br/> |Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).  <br/> |
|**Vitesse de transmission moyenne (Kbit/s)** <br/> |Non  <br/> |Vitesse de transmission vidéo moyenne (en kilobits par seconde).  <br/> |
|**Vitesse de transmission faible (%)** <br/> |Non  <br/> |Pourcentage de l’appel où la vitesse de transmission était faible.  <br/> |
|**Perte de paquets sortante** <br/> |Non  <br/> |Perte de paquets RTP (Real-Time Transport Protocol) pour les paquets sortants. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Image figée (%)** <br/> |Non  <br/> |Pourcentage d’images « figées ». Dans une image figée, la vidéo cesse d’avancer tandis que la partie audio de l’appel continue.  <br/> |
|**Fréquence d’images moyenne sortante** <br/> |Non  <br/> |Fréquence d’images moyenne pour les transmissions sortantes pendant l’appel.  <br/> |
|**Fréquence d’images moyenne entrante** <br/> |Non  <br/> |Fréquence d’images moyenne pour les transmissions entrantes pendant l’appel.  <br/> |
|**Fréquence d’images basse entrante (%)** <br/> |Non  <br/> |Pourcentage de l’appel où la vitesse de transmission pour la vidéo entrante était faible.  <br/> |
|**Intégrité des clients (%)** <br/> ||Indique l’intégrité relative du périphérique client pendant l’appel.  <br/> |
   
**Mesures du rapport de performances du serveur : synthèse des appels de partage d’application**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Type d’appel/type de système d’extrémité** <br/> |Non  <br/> | Lorsque vous cliquez sur cet élément, le rapport affiche des informations détaillées sur les appels en fonction de ce type. Les types d’appels sont les suivants : <br/>  Appels d’égal à égal UC <br/>  Sessions de conférence UC <br/>  Sessions de conférence PSTN <br/>  Appels PSTN : contournement du média <br/>  Appels PSTN (sans contournement) : partie UC <br/>  Appels PSTN (sans contournement) : partie passerelle <br/>  Autres types d’appels <br/> |
|**Volume d’appels** <br/> |Non  <br/> |Nombre total d’appels par type d’appel.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Non  <br/> |Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Volume d’appels (appels sans fil)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion sans fil.  <br/> |
|**Volume d’appels (appels VPN)** <br/> |Non  <br/> |Nombre total d’appels qui utilisaient une connexion VPN.  <br/> |
|**Volume d’appels (appels externes)** <br/> |Non  <br/> |Nombre d’appels qui utilisaient une connexion externe (c’est-à-dire une connexion en dehors du réseau interne).  <br/> |
|**Gigue (ms)** <br/> |Non  <br/> |Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.  <br/> |
|**Unilatéral relatif moyen** <br/> |Non  <br/> |Retard unilatéral relatif moyen entre deux points de terminaison du média. Il s’agit d’une mesure de latence sur un seul tronçon.  <br/> |
|**Latence moyenne de traitement des mosaïques RDP** <br/> |Non  <br/> |Latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage. Cette mesure ne couvre pas la latence du réseau. Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés.  <br/> |
|**Nombre total de mosaïques altérées (%)** <br/> |Non  <br/> |Pourcentage total de mosaïques RDP altérées.  <br/> |
   

