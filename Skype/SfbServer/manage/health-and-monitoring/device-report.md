---
title: Rapport de périphérique dans Skype Entreprise Server
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
ms.assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
description: 'Résumé : Découvrez le rapport de périphérique dans Skype Entreprise Server.'
ms.openlocfilehash: 211dc69423f8f5b2edb9d5508a78c48297d3917c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392526"
---
# <a name="device-report-in-skype-for-business-server"></a>Rapport de périphérique dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport de périphérique dans Skype Entreprise Server.
  
Le Rapport de périphérique devrait plutôt s’appeler le Rapport de microphone et de haut-parleurs : en effet, le Rapport de périphérique récupère toutes les mesures de l’appel (comme le pourcentage d’appels médiocres, les échos et la durée du basculement vocal) regroupées par les microphones et les haut-parleurs utilisés pendant l’appel. Si vous êtes intéressé par les téléphones IP (également communément appelés « périphériques »), utilisez le rapport d’inventaire Téléphone [IP dans Skype Entreprise Server](ip-phone-inventory-report.md) à la place.
  
Le rapport de périphérique est très utile pour les administrateurs souhaitant déterminer si un type d’appareil spécifique rencontre un plus grand nombre d’appels médiocres que d’autres appareils. Ce rapport pourrait, à son tour, influencer les décisions que vous devez prendre au moment de l’achat de nouveaux périphériques ou du remplacement des périphériques existants.
  
Par défaut, les informations affichées dans le rapport de périphérique sont également basées sur le microphone (le périphérique de capture) et les haut-parleurs/casques (le périphérique de sortie) utilisés pour l’appel. Par exemple, supposons que vous ayez différents utilisateurs utilisant les périphériques de capture et de sortie suivants :
  
- Périphérique de capture : microphone (SoundMAX Integrated Digital HD Audio)
    
- Périphérique de rendu : casque pour téléphone (Microsoft LifeChat LX-3000)
    
Si ces utilisateurs passent 254 appels, une entrée semblable à celle-ci sera affichée dans le rapport :
  
|**Périphérique de capture**|**Périphérique de rendu**|**Volume d’appels**|
|:-----|:-----|:-----|
|Microphone (SoundMAX Integrated Digital HD Audio)  <br/> |Casque pour téléphone (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
   
À présent, supposons que vous ayez un nombre d’utilisateurs utilisant le même périphérique de capture, mais avec un autre périphérique de rendu. Dans ce cas, une deuxième entrée sera affichée dans le rapport, pour cette combinaison de périphériques de capture et de rendu :
  
|**Périphérique de capture**|**Périphérique de rendu**|**Volume d’appels**|
|:-----|:-----|:-----|
|Microphone (SoundMAX Integrated Digital HD Audio)  <br/> |Casque pour téléphone (Microsoft LifeChat LX-3000)  <br/> |254  <br/> |
|Microphone (SoundMAX Integrated Digital HD Audio)  <br/> |Haut-parleurs (SoundMAX Integrated Digital HD Audio)  <br/> |319  <br/> |
   
Si vous préférez consulter les totaux combinés d’un périphérique donné (par exemple, pour le périphérique de capture SoundMAX, indépendamment du périphérique de rendu utilisé), sélectionnez l’option adéquate dans la liste déroulante Typé de périphérique (que ce soit pour le périphérique de capture ou celui de rendu). Si vous sélectionnez le périphérique de capture dans cet exemple, l’entrée sera semblable à celle-ci :
  
|**Périphérique de capture**|**Volume d’appels**|
|:-----|:-----|
|Microphone (SoundMAX Integrated Digital HD Audio)  <br/> |573  <br/> |
   
## <a name="accessing-the-device-report"></a>Accès au rapport de périphérique

Normalement, vous pouvez accéder au rapport de périphérique à partir de la page d’accueil Rapports de surveillance. Toutefois, si vous affichez le rapport détaillé des appels dans [Skype Entreprise Server](call-detail-report.md) vous pouvez descendre dans le rapport de périphérique pour un appareil spécifique en cliquant sur l’une des mesures suivantes :
  
- Périphérique de capture
    
- Périphérique de rendu
    
À partir du rapport de périphérique, vous pouvez descendre dans le rapport des listes d’appels [Skype Entreprise Server](call-list-report-0.md) en cliquant sur l’une des mesures suivantes :
  
- Volume d’appels
    
- Pourcentage d’appels médiocres
    
## <a name="making-the-best-use-of-the-device-report"></a>Utilisation optimale du rapport de périphériques

Pour ce qui est des noms de périphériques, le rapport de périphérique est extrêmement détaillé : par exemple, supposons que vous ayez les périphériques de capture suivants :
  
- Microphone Aastra 3002 (2- Aastra 3002)
    
- Microphone Aastra 3002 (3- Aastra 3002)
    
- Microphone Aastra 3002 (Aastra 3002)
    
- Aastra 6725ip
    
- Microphone Aastra 6725ip (10- Aastra 6725ip)
    
- Microphone Aastra 6725ip (10- Aastra 6725ip)-V0
    
- Microphone Aastra 6725ip (2- Aastra 6725ip)
    
- Microphone Aastra 6725ip (3- Aastra 6725ip)
    
- Microphone Aastra 6725ip (4- Aastra 6725ip)
    
- Microphone Aastra 6725ip (5- Aastra 6725ip)
    
- Microphone Aastra 6725ip (6- Aastra 6725ip)
    
- Microphone Aastra 6725ip (7- Aastra 6725ip)
    
- Microphone Aastra 6725ip (9- Aastra 6725ip)
    
- Microphone Aastra 6725ip (9- Aastra 6725ip)-V0
    
- Microphone Aastra 6725ip (Aastra 6725ip)
    
- Microphone Aastra 6725ip (Aastra 6725ip)-V0
    
- Microphone Aastra 6725ip (périphérique audio USB)
    
- Microphone Aastra 6725ip (périphérique audio USB)-V0
    
> [!NOTE]
> N’oubliez pas que les noms d’appareils de capture peuvent ne pas être identiques si vous exécutez des versions localisées de Skype Entreprise Server. Un périphérique nommé Microphone Aastra 6725ip (Aastra 6725ip)-V0 en FR français peut être nommé différemment en français ou en espagnol. 
  
Il est possible que vous souhaitiez ce niveau de détail à plusieurs reprises ; cependant, la plupart du temps, vous serez probablement uniquement intéressé par le nombre d’appels utilisant n’importe quel microphone Aastra, indépendamment du numéro du modèle. Pour obtenir ce genre d’informations, exportez les données du Rapport de périphérique dans Microsoft Excel et enregistrez ces données sous la forme d’une chaîne de valeurs séparées par des virgules (par exemple, C:\Data\Rapport_périphériques.csv). Vous pouvez ensuite utiliser un ensemble de commandes similaires à celles-ci pour importer le fichier .CSV dans Windows PowerShell et renvoyer le nombre d’appels effectués en utilisant un périphérique de capture Aastra :
  
```PowerShell
$devices = Import-Csv "C:\Data\Device_Report.csv
$sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
$sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
$x
```

Ceci va renvoyer une valeur unique représentant le nombre d’appels effectués en utilisant un périphérique de capture Aastra. Par exemple : 384

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de périphérique vous permet de filtrer des éléments comme le type d’appel, c’est-à-dire s’il s’agissait d’un appel client, d’une téléconférence ou d’un appel du réseau téléphonique commuté (RTC). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les périphériques sont groupés par heure, jour, semaine ou mois.
  
Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de périphérique.
  
**Filtres du rapport de périphérique**

|**Name**|**Description**|
|:-----|:-----|
|**From** <br/> |Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**To** <br/> |Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :  <br/> 7/7/2015 13:00  <br/> Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :  <br/> 7/7/2015  <br/> Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :  <br/> 7/3/2015  <br/> Les semaines s’étalent toujours du dimanche au samedi.  <br/> |
|**Cause du basculement vocal** <br/> |Raison pour laquelle un appel a dû être émis en mode semi-duplex afin d’empêcher l’écho. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie. Sélectionnez l’une des options suivantes :  <br/> [Tous] Aucun signal d’écho d’écho d’timestamp mauvais (processeur nonligne dynamique) Faible complexité État de l’appareil Mauvais état Post-AEC écho (annulation de l’écho sonore) |
|**Cause de l’écho** <br/> |Raison pour laquelle un écho au-dessus du niveau acceptable a été détecté dans un appel. (Dans le domaine des télécommunications, un écho est la réflexion d’un son, il s’agit du même phénomène que vous entendez lorsque vous hélez en direction du fond d’un puits.) Sélectionnez l’une des options suivantes :  <br/> [Tous] Aucun mauvais timestamp écho post-AEC (annulation d’échos sonores) Découpage du microphone ANLP (processeur nonligne adaptatif) DNLP (processeur dynamique nonligne) |
|**Type d’appel** <br/> |Indique le type d’appel émis. Sélectionnez l’une des options suivantes :  <br/> [Tous] Appel client PSTN call Conference call |
|**Type d’accès** <br/> |Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :  <br/> [Tous] Interne externe |
|**Type de réseau** <br/> |Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :  <br/> [Tous] Fil câblé sans fil |
|**VPN** <br/> |Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :  <br/> [Tous] VPN non VPN |
|**Type de périphérique** <br/> |Indique le type du périphérique. Sélectionnez l’une des options suivantes :  <br/> Capture de la paire d’appareils de capture/rendu d’appareil de rendu |
|**Nom du périphérique** <br/> |Nom du périphérique de capture ou de rendu. Vous pouvez entrez le nom complet du périphérique ou seulement une partie. Par exemple, pour trouver le périphérique Microphone (Microsoft LifeCam VX-1000), vous pouvez entrer la totalité du nom du périphérique comme suit :  <br/> Microphone (Microsoft LifeCam VX-1000)  <br/> Ou, vous pouvez entrer uniquement une partie du nom. Par exemple :  <br/> LifeCam  <br/> Notez que le filtre précédant permet de retourner tous les périphériques qui contiennent la chaîne « LifeCam » dans leur nom.  <br/> |
   
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de périphérique.
  
**Mesures du rapport de périphérique**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Périphérique de capture** <br/> |Oui  <br/> |Périphérique (par exemple, un microphone ou une webcam) utilisé pour transmettre de l’audio.  <br/> |
|**Périphérique de rendu** <br/> |Oui  <br/> |Périphérique (par exemple, un casque ou des haut-parleurs) utilisé pour recevoir de l’audio.  <br/> |
|**Volume d’appels** <br/> |Oui  <br/> |Nombre total d’appels émis.  <br/> |
|**Pourcentage d’appels médiocres** <br/> |Oui  <br/> |Pourcentage d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).  <br/> |
|**Utilisateurs uniques** <br/> |Oui  <br/> |Utilisateurs uniques qui ont utilisé le périphérique. Si un utilisateur a utilisé le périphérique 13 fois, il compte comme un seul utilisateur, à l’instar d’un utilisateur qui l’a utilisé une seule fois.  <br/> |
|**Ratio de la durée du basculement vocal** <br/> |Oui  <br/> |Pourcentage de l’appel qui a dû être effectué en mode semi-duplex afin d’empêcher l’écho. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie.  <br/> |
|**Ratio du microphone ne fonctionnant pas** <br/> |Oui  <br/> |Pourcentage de l’appel pendant lequel le périphérique de capture ne fonctionnait pas à un niveau acceptable. Une valeur élevée suggère que les problèmes de qualité de l’appel étaient principalement dus au fonctionnement incorrect du périphérique de capture.  <br/> |
|**Ratio du haut-parleur ne fonctionnant pas** <br/> |Oui  <br/> |Pourcentage de l’appel pendant lequel le périphérique de rendu ne fonctionnait pas à un niveau acceptable. Une valeur élevée suggère que les problèmes de qualité de l’appel étaient principalement dus au fonctionnement incorrect du périphérique de rendu.  <br/> |
|**Appels avec basculement vocal (%)** <br/> |Oui  <br/> |Pourcentage du nombre total d’appels qui ont dû être émis en mode semi-duplex. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie.  <br/> |
|**Écho en entrée du microphone (%)** <br/> |Oui  <br/> |Pourcentage du temps où un écho a été détecté dans le flux de capture du microphone. En règle générale, les valeurs sont faibles pour les casques ou combinés, et plus élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui supportent l’annulation de l’écho sonore à bord, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.  <br/> |
|**Source-réverbération (%)** <br/> |Oui  <br/> |Pourcentage d’écho transmis à d’autres utilisateurs.  <br/> |
|**Appels avec écho (%)** <br/> |Oui  <br/> |Pourcentage du nombre total d’appels dont l’écho a dépassé le niveau acceptable.  <br/> |
   

