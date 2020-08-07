---
title: Implémenter la qualité de service dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Découvrez comment préparer le réseau de votre organisation à la qualité de service (QoS) dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a83a18810268d3eb8317eb541f7eb06ff812c9c
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582091"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Mise en œuvre de la qualité de service (QoS) dans Microsoft teams

La qualité de service (QoS) dans Microsoft teams permet d’autoriser le trafic réseau en temps réel, qui est sensible aux retards de réseau (par exemple, les flux vocaux ou vidéo) en « Cut Line », devant le trafic moins sensible (par exemple, le téléchargement d’une nouvelle application, où le téléchargement d’une seconde version supplémentaire n’est pas une solution importante). La fonction QoS identifie et marque tous les paquets en flux temps réel (à l’aide d’objets de stratégie de groupe Windows et d’une fonctionnalité de routage appelée listes de contrôle d’accès basée sur le port, plus d’informations sur celles-ci sont disponibles), ce qui permet à votre réseau de transmettre des flux vocaux, vidéo et de partage d’écran une portion dédiée de la bande passante réseau

Si vous prenez en charge un groupe de nombreux utilisateurs et qu’ils rencontrent des problèmes décrits ci-dessous, vous devez probablement implémenter QoS. Une petite entreprise avec peu d’utilisateurs peut ne pas avoir besoin de la qualité de service (QoS), mais même celle-ci peut être utile.

Sans la qualité de service (QoS), vous risquez de rencontrer les problèmes de qualité suivants dans les fonctionnalités audio et vidéo :

- Gigue : paquets multimédias entrants à des tarifs différents, qui peuvent entraîner l’absence de mots ou de syllabes dans les appels
- Perte de paquets – paquets rejetés, ce qui peut entraîner une diminution de la qualité de la voix et des difficultés à comprendre les paroles
- Durée de l’aller-retour retardé (RTT) : les paquets multimédias prenaient un temps considérable pour joindre leurs destinataires, ce qui a pour effet de retarder les utilisateurs

Le moyen le plus complexe de traiter ces problèmes consiste à augmenter la taille des connexions de données, à la fois en interne et hors Internet. Étant donné qu’il s’agit souvent de coûts, la fonction QoS fournit un moyen de gérer plus efficacement les ressources que vous avez au lieu d’ajouter de la bande passante. Pour résoudre les problèmes de qualité, nous vous recommandons de commencer par utiliser QoS, puis d’ajouter de la bande passante uniquement si nécessaire.

Pour que la qualité de service (QoS) s’applique, vous devez appliquer des paramètres de QoS cohérents dans l’ensemble de votre organisation, car une partie du chemin d’accès qui ne prend pas en charge les priorités de QoS peut nuire à la qualité des appels, de la vidéo et du partage d’écran. Cela inclut l’application de paramètres à tous les PC ou appareils utilisateur, commutateurs réseau, routeurs vers Internet et service équipes.

_Figure 1. Relation entre les réseaux d’une organisation et Microsoft 365 ou les services 365 Office_

![Illustration de la relation entre les réseaux et les services](media/Qos-in-Teams-Image1.png "Relation entre les réseaux d’une organisation et les services 365 Microsoft 365 ou Office : le réseau local et les appareils se connectent à un réseau d’interconnexion, qui à son tour s’associe à Microsoft 365 365 ou aux services d’audioconférence Cloud et voix sur le Cloud.")

## <a name="qos-implementation-checklist"></a>Liste de vérification de l’implémentation QoS

À un niveau élevé, procédez comme suit pour implémenter QoS :

1. [Vérifier que votre réseau est prêt](#make-sure-your-network-is-ready)

1. [Sélectionner une méthode d’implémentation de QoS](#select-a-qos-implementation-method)

1. [Choisir les plages de port initiales pour chaque type de média](#choose-initial-port-ranges-for-each-media-type)

1. Mettre en œuvre des paramètres de QoS :
   1. Sur les clients utilisant un objet de stratégie de groupe pour [définir les plages de port de périphériques client et les marques](QoS-in-Teams-clients.md)
   2. Sur les routeurs (voir la documentation du fabricant) ou sur d’autres appareils réseau. Il s’agit de listes de Contrã’le de niveau de service, ou simplement de définir des files d’attente de QoS et des marques DSCP.

      > [!IMPORTANT]
      > Nous vous recommandons d’implémenter ces stratégies de QoS à l’aide des ports sources du client et d’une adresse IP source et de destination « tout. » Le trafic multimédia entrant et sortant est alors détecté sur le réseau interne.  

   3. [Définir la manière dont vous souhaitez gérer le trafic multimédia pour les réunions teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Validez la mise en œuvre](#validate-your-qos-implementation) de la qualité de service en analysant le trafic d’équipe sur le réseau.

Lorsque vous préparez la mise en œuvre de la qualité de service (QoS), gardez à l’esprit les recommandations suivantes :

- Le chemin le plus court à Microsoft 365 est préférable
- La fermeture des ports entraîne uniquement une dégradation de la qualité
- Tout obstacle entre, tels que les proxys, n’est pas recommandé
- Limiter le nombre de tronçons :
  - Client vers Edge réseau : 3 à 5 tronçons
  - Fournisseur de services Internet pour Microsoft Network Edge – 3 tronçons
  - Destination réseau Microsoft de destination finale-sans pertinence

Pour plus d’informations sur la configuration des ports de pare-feu, voir [URL et plages d’adresses IP Office 365](office-365-urls-ip-address-ranges.md).


## <a name="make-sure-your-network-is-ready"></a>Vérifier que votre réseau est prêt

Si vous envisagez une implémentation QoS, vous devez déjà avoir déterminé vos exigences de bande passante et d’autres [exigences réseau](prepare-network.md). 
  
La congestion du trafic sur un réseau aura un impact considérable sur la qualité multimédia. Un manque de bande passante entraîne une dégradation des performances et une expérience utilisateur médiocre. En vertu du développement et de l’utilisation des équipes, vous pouvez utiliser la création de rapports, l' [analyse des appels par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md)et le [tableau de bord de qualité d’appel (bord)](turning-on-and-using-call-quality-dashboard.md) pour identifier les problèmes, puis effectuer des ajustements à l’aide de la fonction QoS et des ajouts

### <a name="vpn-considerations"></a>Considérations relatives aux réseaux VPN

QoS fonctionne uniquement quand il est implémenté sur tous les liens entre les appelants. Si vous utilisez QoS sur un réseau interne et qu’un utilisateur se connecte à partir d’un emplacement distant, vous pouvez uniquement définir des priorités dans votre réseau interne géré. Bien que les emplacements distants puissent recevoir une connexion gérée via l’implémentation d’un réseau privé virtuel (VPN), un VPN ajoute par essence une surcharge de paquets et génère des retards en temps réel. Nous vous recommandons de ne pas utiliser le trafic de communications en temps réel sur un réseau privé virtuel (VPN).

Dans une organisation globale disposant de liens gérés qui couvrent des continents, nous vous recommandons vivement de QoS, car le niveau de bande passante pour ces liens est limité par rapport au réseau local.

## <a name="introduction-to-qos-queues"></a>Introduction aux files d’attente QoS

Pour garantir la qualité de service (QoS), les appareils réseau doivent disposer d’un moyen de classifier le trafic et doivent être en mesure de distinguer la voix ou la vidéo du reste du trafic réseau.

Lorsque le trafic réseau entre dans un routeur, le trafic est placé dans une file d’attente. Si aucune stratégie de QoS n’est configurée, il n’y a qu’une seule file d’attente, et toutes les données sont traitées comme étant de type First-in, premier niveau avec la même priorité. Cela signifie que le trafic vocal (qui est très sensible aux retards) peut rester bloqué derrière le trafic pour lequel un délai de quelques millisecondes supplémentaires ne serait pas un problème.

Lorsque vous implémentez QoS, vous définissez plusieurs files d’attente à l’aide de l’une des nombreuses fonctionnalités de gestion de la congestion (par exemple, la mise en file d’attente équitable de Cisco et la mise en [attente normale basée sur la classe (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641), ainsi que des fonctionnalités de prévention de congestion ( [WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).

_Figure 2. Exemples de files d’attente QoS_

![Illustration des files d’attente de QoS et de la Division de bande passante](media/Qos-in-Teams-Image2.png "La bande passante disponible totale est divisée en plusieurs files d’attente (audio, vidéo, etc.) auxquelles des priorités différentes sont affectées.")

Une simple analogie est que la qualité de service (QoS) crée des « couloirs Carpool » dans votre réseau de données de sorte que certains types de données ne soient jamais ou ne rencontrent pas de temps. Une fois que vous avez créé ces couloirs, vous pouvez ajuster leur taille relative et gérer davantage efficacement la bande passante de connexion que vous utilisez, tout en offrant aux utilisateurs de votre organisation des expériences de niveau professionnel.

## <a name="select-a-qos-implementation-method"></a>Sélectionner une méthode d’implémentation de QoS

Vous pouvez implémenter QoS par le biais du balisage basée sur le port, à l’aide des listes de contrôle d’accès (ACL) sur les routeurs de votre réseau. Le balisage basé sur les ports est la méthode la plus fiable, car elle fonctionne dans les environnements Windows, Mac et Linux et est la plus simple à implémenter. Les clients mobiles ne fournissent aucun mécanisme de marquage du trafic à l’aide de valeurs DSCP, de sorte qu’ils nécessitent cette méthode.  

Le routeur de votre réseau examine un paquet entrant et, si le paquet est reçu à l’aide d’un certain port ou d’une plage de ports, il l’identifie en tant que type de média et le place dans la file d’attente pour ce type, en ajoutant une marque [DSCP](https://tools.ietf.org/html/rfc2474) prédéfinie à l’en-tête de paquet IP, afin que d’autres appareils puissent reconnaître son type de trafic et

Même si cela fonctionne sur différentes plateformes, le trafic est uniquement marqué sur le périmètre du réseau WAN (et non sur l’ordinateur client) et entraîne une surcharge de gestion. Pour obtenir des instructions sur l’implémentation de cette méthode, consultez la documentation fournie par le fabricant du routeur.

### <a name="insert-dscp-markers"></a>Insérer des marqueurs DSCP

Vous pouvez également implémenter QoS à l’aide d’un objet de stratégie de groupe (GPO) pour diriger les appareils clients pour insérer un marqueur DSCP dans les en-têtes de paquets IP identifiant ce type de trafic particulier (par exemple, audio). Les routeurs et autres périphériques réseau peuvent être configurés pour reconnaître ce point et placer le trafic dans une file d’attente séparée et de priorité élevée.

Bien que ce scénario soit entièrement valide, il fonctionne uniquement pour les clients Windows associés à un domaine. Tout appareil qui n’est pas un client Windows qui n’est pas membre du domaine ne sera pas activé pour la balise DSCP. Les clients tels que Mac OS disposent de balises codées en dur et balisent toujours le trafic.

Sur le côté de plus, le contrôle du marquage DSCP via un objet de stratégie de groupe garantit que tous les ordinateurs appartenant à un domaine reçoivent les mêmes paramètres et que seul un administrateur peut les gérer. Les clients qui peuvent utiliser l’objet de stratégie de groupe seront balisés sur l’appareil d’origine, puis les appareils réseau configurés pourront reconnaître le flux en temps réel par le code DSCP et lui attribuer une priorité appropriée.

### <a name="best-practice"></a>Meilleure pratique

Nous vous recommandons d’utiliser une combinaison de marques DSCP au niveau du point de terminaison et des ACL de port sur les routeurs, le cas échéant. L’utilisation d’un objet de stratégie de groupe pour intercepter la plupart des clients, et l’utilisation du balisage DSCP par port permet de garantir que le traitement de la QoS (au moins partiellement) est appliqué au niveau du service.

Les marques DSCP peuvent être comparées aux timbres postaux qui indiquent aux travailleurs postaux le niveau d’urgence de la livraison et au meilleur ordre de tri pour la livraison rapide. Une fois que vous avez configuré votre réseau pour donner un ordre de priorité aux flux multimédias en temps réel, les paquets perdus et les paquets tardifs doivent considérablement diminuer.

Une fois tous les appareils du réseau utilisant les mêmes classifications, marques et priorités, il est possible de réduire ou d’éliminer les retards, les paquets interrompus et le scintillement en modifiant la taille des plages de port affectées aux files d’attente utilisées pour chaque type de trafic. Du point de vue de teams, l’étape de configuration la plus importante consiste à la classification et au marquage de paquets, mais pour garantir la réussite de la qualité de service (QoS) de bout en bout, vous devez également aligner soigneusement la configuration de l’application avec la configuration réseau sous-jacente. Une fois la QoS entièrement implémentée, la gestion en continu est une question de l’ajustement des plages de port affectées à chaque type de trafic selon les besoins de votre organisation et leur utilisation réelle.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Choisir les plages de port initiales pour chaque type de média

La valeur DSCP indique à une connexion réseau configurée quelle priorité définir un paquet ou un flux, si la marque DSCP est affectée par des clients ou le réseau lui-même en fonction des paramètres de la liste de contrôle d’accès. Chaque charge de travail multimédia obtient sa propre valeur DSCP unique (d’autres services peuvent permettre aux charges de travail de partager un marquage DSCP, teams n’est pas) et une plage de port définie et séparée utilisée pour chaque type de média. Dans d’autres environnements, il est possible qu’une stratégie QoS existe en place, ce qui vous permet de déterminer la priorité des charges de travail réseau.

La taille relative des plages de port pour différentes charges de travail en flux continu en temps réel définit le prorata de la bande passante disponible totale dédiée à cette charge de travail. Pour revenir à notre analogie initiale plus ancienne : une lettre portant le cachet « messagerie » peut être prélevée dans une heure à l’aéroport le plus proche, tandis qu’un petit emballage marqué « courrier en nombre » peut patienter pendant une journée avant de voyager sur terre sur une série de camions.

_Plages de port initiales recommandées_

|Type de trafic média| Plage de port source du client  |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| Entre 50 000 et 50 019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50 020–50 039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’application/d'écran| 50 040–50 059|TCP/UDP|19|Transfert garanti (AF21)|
||||||

Tenez compte des points suivants lorsque vous utilisez les paramètres suivants :

- Si vous envisagez d’implémenter ExpressRoute à l’avenir et que vous n’avez pas encore implémenté QoS, nous vous conseillons de suivre les recommandations de sorte que les valeurs DSCP soient les mêmes entre l’expéditeur et le destinataire.
- Tous les clients, notamment les appareils mobiles et les équipes Teams, utiliseront ces plages de ports et seront touchés par toute stratégie DSCP implémentée qui utilise ces plages de ports sources. Les seuls clients qui continuent à utiliser les ports dynamiques sont les clients basés sur le navigateur (autrement dit, les clients qui permettent aux participants de rejoindre des réunions à l’aide de leur navigateur).
- Même si le client Mac utilise les mêmes plages de port, il utilise également des valeurs codées en dur pour le son (EF) et la vidéo (AF41). Ces valeurs ne peuvent pas être configurées.
- Si vous devez ajuster plus tard les plages de port pour améliorer l’utilisation de l’utilisateur, les plages de port ne peuvent pas se chevaucher et doivent être adjacentes.

## <a name="migrate-qos-to-teams"></a>Migration de QoS vers teams

Si vous avez déjà déployé Skype entreprise Online, notamment le balisage QoS et les plages de port, et que vous déployez désormais Teams, teams respecte la configuration existante et utilise les mêmes plages de port et balisage que le client Skype entreprise. Dans la plupart des cas, aucune configuration supplémentaire n’est nécessaire.

> [!NOTE]
> Si vous utilisez le balisage QoS du nom de l’application via une stratégie de groupe, vous devez ajouter Teams.exe comme nom de l’application.


## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestion des ports sources dans le centre d’administration teams

Dans Teams, les ports sources QoS utilisés par les différentes charges de travail doivent être gérés activement et ajustés selon les besoins. Le fait de faire référence à la table dans [choisir des plages de port initiales pour chaque type de média](#choose-initial-port-ranges-for-each-media-type), les plages de port sont ajustables, mais les marques DSCP ne peuvent pas être configurées. Une fois ces paramètres implémentés, il est possible que vous ayez besoin de plus ou moins de ports pour un type de média donné. Le tableau de bord d’analyse des appels et des appels de qualité d’appel [par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md) [(bord)](turning-on-and-using-call-quality-dashboard.md) doit être utilisé pour prendre une décision d’ajuster les plages de port après la mise en œuvre d’équipes et périodiquement en cas de changement.

> [!NOTE]
> Si vous avez déjà configuré la qualité de service (QoS) sur la base des plages de ports sources et des marques DSCP pour Skype entreprise Online, la même configuration s’applique aux équipes et aucune modification du client ou du réseau supplémentaire n’est nécessaire, mais vous devrez peut-être [définir les plages utilisées dans teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) pour correspondre aux configurations de Skype entreprise online.

Si vous avez déjà déployé Skype entreprise Server en local, il est possible que vous deviez réexaminer vos stratégies de QoS et les ajuster pour correspondre aux paramètres de plage de port que vous avez vérifiés pour une utilisation optimale de l’utilisateur dans Teams.

## <a name="validate-your-qos-implementation"></a>Valider votre implémentation QoS

Pour que la qualité de service (QoS) soit effective, la valeur DSCP définie par l’objet de stratégie de groupe doit être présente aux deux extrémités d’un appel. En analysant le trafic généré par le client Teams, vous pouvez vérifier que la valeur DSCP n’est pas modifiée ou supprimée lorsque le trafic de charge de travail d’équipes se déplace sur le réseau.

De préférence, vous capturez le trafic sur le point de sortie du réseau. Pour cela, vous pouvez utiliser la mise en miroir de port sur un commutateur ou un routeur.


## <a name="related-topics"></a>Voir aussi

[Vidéo : planification du réseau](https://aka.ms/teams-networking)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)

[Implémenter QoS dans le client teams](QoS-in-Teams-clients.md)
