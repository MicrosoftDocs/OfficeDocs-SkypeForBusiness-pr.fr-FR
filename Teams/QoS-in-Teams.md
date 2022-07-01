---
title: Implémenter la qualité de service dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Découvrez comment préparer le réseau de votre organisation pour la qualité de service (QoS) dans Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: 6015c7b7cf1e7be5bc6b9b3e1fe0577a7f707377
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564142"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implémenter la qualité de service (QoS) dans Microsoft Teams

La qualité de service (QoS) dans Microsoft Teams permet au trafic réseau en temps réel sensible aux retards réseau (par exemple, les flux vocaux ou vidéo) de « couper en ligne » devant le trafic moins sensible (comme le téléchargement d’une nouvelle application, où le téléchargement d’une seconde supplémentaire n’est pas une grande affaire). QoS utilise des objets windows stratégie de groupe et des listes de Access Control basées sur des ports pour identifier et marquer tous les paquets dans des flux en temps réel. Cela permet à votre réseau de fournir aux flux de partage de voix, de vidéo et d’écran une partie dédiée de la bande passante réseau.

Si vous prenez en charge un grand groupe d’utilisateurs qui rencontrent l’un des problèmes décrits dans cet article, vous devez probablement implémenter QoS. Une petite entreprise avec peu d’utilisateurs n’a peut-être pas besoin de QoS, mais même là, elle doit être utile.

Sans une forme quelconque de QoS, vous pouvez voir les problèmes de qualité suivants dans la voix et la vidéo :

- Gigue : paquets multimédias arrivant à des vitesses différentes, ce qui peut entraîner l’absence de mots ou de syllabes dans les appels
- Perte de paquets : paquets supprimés, ce qui peut également entraîner une qualité de voix inférieure et une reconnaissance vocale difficile à comprendre
- Temps d’aller-retour différé (RTT) : les paquets multimédias prennent beaucoup de temps pour atteindre leurs destinations, ce qui entraîne des retards notables entre deux parties dans une conversation et provoque des échanges entre les personnes

La méthode la moins complexe pour résoudre ces problèmes consiste à augmenter la taille des connexions de données, à la fois en interne et vers Internet. Étant donné que cela est souvent prohibitif, QoS permet de gérer plus efficacement les ressources dont vous disposez au lieu d’ajouter de la bande passante. Pour résoudre les problèmes de qualité, nous vous recommandons d’abord d’utiliser QoS, puis d’ajouter de la bande passante uniquement si nécessaire.

Pour que QoS soit efficace, vous devez appliquer des paramètres QoS cohérents dans toute votre organisation. Toute partie du chemin qui ne prend pas en charge vos priorités QoS peut dégrader la qualité des appels, de la vidéo et du partage d’écran. Cela inclut l’application de paramètres à tous les PC ou appareils utilisateur, aux commutateurs réseau, aux routeurs sur Internet et au service Teams.

_Figure 1. Relation entre les réseaux d’une organisation et les services Microsoft 365 ou Office 365_

![Illustration de la relation entre les réseaux et les services.](media/Qos-in-Teams-Image1.png "La relation entre les réseaux d’une organisation et les services Microsoft 365 ou Office 365 : le réseau local et les appareils se connectent avec un réseau d’interconnexion, qui à son tour se connecte à Microsoft 365 ou Office 365 services de voix cloud et d’audioconférence.")

## <a name="qos-implementation-checklist"></a>Liste de vérification de l’implémentation de QoS

À un niveau élevé, procédez comme suit pour implémenter QoS :

1. [Assurez-vous que votre réseau est prêt](#make-sure-your-network-is-ready).

1. [Sélectionnez une méthode d’implémentation QoS](#select-a-qos-implementation-method).

1. [Choisissez les plages de ports initiales pour chaque type de média](#choose-initial-port-ranges-for-each-media-type).

1. Implémenter les paramètres QoS :
   1. Sur les clients qui utilisent un objet stratégie de groupe (GPO) pour [définir des plages de ports d’appareil client et des marquages](QoS-in-Teams-clients.md).
   2. Sur les routeurs (consultez la documentation du fabricant) ou d’autres périphériques réseau. Cela peut inclure des listes de Access Control basées sur des ports ou simplement la définition des files d’attente QoS et des marquages DSCP, ou toutes ces listes.

      > [!IMPORTANT]
      > Nous vous recommandons d’implémenter ces stratégies QoS à l’aide des ports sources du client et d’une adresse IP source et de destination de « any ». Cela intercepte le trafic multimédia entrant et sortant sur le réseau interne.  

   3. [Définissez la façon dont vous souhaitez gérer le trafic multimédia pour les réunions Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).

5. [Validez votre implémentation QoS en](#validate-your-qos-implementation) analysant le trafic Teams sur le réseau.

Lorsque vous vous préparez à implémenter QoS, gardez à l’esprit les instructions suivantes :

- Le chemin le plus court vers Microsoft 365 est le meilleur.
- La fermeture des ports n’entraîne qu’une dégradation de la qualité.
- Les obstacles entre les deux, tels que les proxys, ne sont pas recommandés.
- Limitez le nombre de tronçons :
  - Périphérie du client vers le réseau – 3 à 5 tronçons
  - IsP to Microsoft network edge – 3 tronçons
  - Microsoft Network Edge vers la destination finale – non pertinent

Pour plus d’informations sur la configuration des ports de pare-feu, accédez à [Office 365 URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Assurez-vous que votre réseau est prêt

Si vous envisagez une implémentation QoS, vous devez déjà avoir déterminé vos besoins en bande passante et d’autres [exigences réseau](prepare-network.md).
  
La congestion du trafic sur un réseau aura un impact considérable sur la qualité des médias. Un manque de bande passante entraîne une dégradation des performances et une mauvaise expérience utilisateur. À mesure que l’adoption et l’utilisation de Teams augmentent, utilisez la création de rapports, [l’analytique des appels par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md) et le tableau de bord [de qualité des appels (CQD)](turning-on-and-using-call-quality-dashboard.md) pour identifier les problèmes, puis apportez des ajustements à l’aide de QoS et d’ajouts sélectifs de bande passante.

### <a name="vpn-considerations"></a>Considérations relatives au VPN

QoS fonctionne uniquement comme prévu lorsqu’il est implémenté sur tous les liens entre les appelants. Si vous utilisez QoS sur un réseau interne et qu’un utilisateur se connecte à partir d’un emplacement distant, vous ne pouvez hiérarchiser que dans votre réseau interne géré. Bien que les emplacements distants puissent recevoir une connexion managée en implémentant un réseau privé virtuel (VPN), un VPN ajoute intrinsèquement une surcharge de paquets et crée des retards dans le trafic en temps réel. Nous vous recommandons d’éviter d’exécuter le trafic de communications en temps réel sur un VPN.

Dans une organisation mondiale avec des liaisons gérées qui s’étendent sur des continents, nous recommandons vivement QoS, car la bande passante pour ces liaisons est limitée par rapport au réseau local.

## <a name="introduction-to-qos-queues"></a>Présentation des files d’attente QoS

Pour fournir la qualité de service, les appareils réseau doivent avoir un moyen de classer le trafic et doivent être en mesure de distinguer la voix ou la vidéo d’un autre trafic réseau.

Lorsque le trafic réseau entre dans un routeur, le trafic est placé dans une file d’attente. Si une stratégie QoS n’est pas configurée, il n’y a qu’une seule file d’attente et toutes les données sont traitées comme des données de première entrée et de premier sorti avec la même priorité. Cela signifie que le trafic vocal (qui est très sensible aux retards) peut être bloqué derrière le trafic où un délai de quelques millisecondes supplémentaires ne serait pas un problème.

Lorsque vous implémentez QoS, vous définissez plusieurs files d’attente à l’aide de l’une des fonctionnalités de gestion de la congestion, telles que la mise en file d’attente prioritaire de Cisco et la mise [en file d’attente juste pondérée basée sur les classes (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) et les fonctionnalités d’évitement de la congestion, telles que la [détection précoce pondérée (WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Figure 2. Exemples de files d’attente QoS_

![Illustration des files d’attente QoS et de la division de bande passante.](media/Qos-in-Teams-Image2.png "La bande passante disponible totale est divisée entre plusieurs files d’attente (audio, vidéo et autres trafics) qui ont reçu différentes priorités.")

Une analogie simple est que QoS crée des « voies de covoiturage » virtuelles dans votre réseau de données afin que certains types de données ne rencontrent jamais ou rarement un délai. Une fois que vous avez créé ces voies, vous pouvez ajuster leur taille relative et gérer beaucoup plus efficacement la bande passante de connexion dont vous disposez, tout en offrant des expériences professionnelles aux utilisateurs de votre organisation.

## <a name="select-a-qos-implementation-method"></a>Sélectionner une méthode d’implémentation QoS

Vous pouvez implémenter QoS via un balisage basé sur un port, à l’aide de listes de Access Control (ACL) sur les routeurs de votre réseau. Le balisage basé sur les ports est la méthode la plus fiable, car il fonctionne dans des environnements Windows, Mac et Linux mixtes et est le plus simple à implémenter. Les clients mobiles ne fournissent pas de mécanisme pour marquer le trafic à l’aide de valeurs DSCP. Ils auront donc besoin de cette méthode.  

À l’aide du balisage basé sur un port, le routeur de votre réseau examine un paquet entrant et, si le paquet est arrivé à l’aide d’un port ou d’une plage de ports donnés, il l’identifie comme un certain type de média et le place dans la file d’attente pour ce type, en ajoutant une marque [DSCP](https://tools.ietf.org/html/rfc2474) prédéterminée à l’en-tête paquet IP afin que d’autres appareils puissent reconnaître son type de trafic et lui donner la priorité dans leur file d’attente.

Bien que le balisage basé sur les ports fonctionne sur plusieurs plateformes, il marque uniquement le trafic à la périphérie du RÉSEAU ÉTENDU (et non jusqu’à l’ordinateur client) et crée une surcharge de gestion. Reportez-vous à la documentation fournie par le fabricant du routeur pour obtenir des instructions sur l’implémentation de cette méthode.

### <a name="insert-dscp-markers"></a>Insérer des marqueurs DSCP

Vous pouvez également implémenter QoS à l’aide d’un objet stratégie de groupe (GPO) pour diriger les appareils clients à insérer un marqueur DSCP dans les en-têtes de paquets IP l’identifiant comme type particulier de trafic (par exemple, voix). Les routeurs et autres périphériques réseau peuvent être configurés pour reconnaître ce problème et placer le trafic dans une file d’attente distincte de priorité plus élevée.

Bien que ce scénario soit entièrement valide, il ne fonctionne que pour les clients Windows joints à un domaine. Tout appareil qui n’est pas un client Windows joint à un domaine ne sera pas activé pour l’étiquetage DSCP. D’autres clients, tels que ceux exécutant macOS, ont des balises codées en dur et balisent toujours le trafic.

Du côté positif, le contrôle du marquage DSCP via un objet de stratégie de groupe garantit que tous les ordinateurs joints à un domaine reçoivent les mêmes paramètres et que seul un administrateur peut les gérer. Les clients qui peuvent utiliser l’objet de stratégie de groupe sont marqués sur l’appareil d’origine, puis les appareils réseau configurés peuvent reconnaître le flux en temps réel par le code DSCP et lui donner une priorité appropriée.

### <a name="best-practice"></a>Bonne pratique

Nous vous recommandons d’associer des marquages DSCP au point de terminaison et des listes de contrôle d’accès basées sur des ports sur les routeurs, si possible. L’utilisation d’un objet de stratégie de groupe pour intercepter la majorité des clients et l’utilisation de l’étiquetage DSCP basé sur un port garantissent que les clients mobiles, Mac et d’autres clients bénéficieront toujours d’un traitement QoS (au moins partiellement).

Les marquages DSCP peuvent être comparables à des timbres-poste qui indiquent aux travailleurs postaux l’urgence de la livraison et la meilleure façon de la trier pour une livraison rapide. Une fois que vous avez configuré votre réseau pour donner la priorité aux flux multimédias en temps réel, les paquets perdus et les paquets en retard doivent considérablement diminuer.

Une fois que tous les appareils du réseau utilisent les mêmes classifications, marquages et priorités, il est possible de réduire ou d’éliminer les retards, les paquets supprimés et la gigue en modifiant la taille des plages de ports affectées aux files d’attente utilisées pour chaque type de trafic. Du point de vue de Teams, l’étape de configuration la plus importante est la classification et le marquage des paquets. Toutefois, pour que la qualité de service de bout en bout réussisse, vous devez également aligner soigneusement la configuration de l’application avec la configuration réseau sous-jacente. Une fois QoS entièrement implémenté, la gestion continue consiste à ajuster les plages de ports affectées à chaque type de trafic en fonction des besoins et de l’utilisation réelle de votre organisation.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Choisir les plages de ports initiales pour chaque type de média

La valeur DSCP indique à un réseau configuré en conséquence la priorité à accorder à un paquet ou un flux, que la marque DSCP soit affectée par les clients ou le réseau lui-même en fonction des paramètres ACL. Chaque charge de travail multimédia obtient sa propre valeur DSCP unique (d’autres services peuvent permettre aux charges de travail de partager un marquage DSCP, ce qui n’est pas le cas de Teams) et une plage de ports définie et distincte utilisée pour chaque type de média. D’autres environnements peuvent avoir une stratégie QoS existante, qui vous aidera à déterminer la priorité des charges de travail réseau.

La taille relative des plages de ports pour différentes charges de travail de streaming en temps réel définit la proportion de la bande passante totale disponible dédiée à cette charge de travail. Pour revenir à notre analogie postale précédente : une lettre avec un tampon « Courrier aérien » peut être prise dans l’heure qui suit à l’aéroport le plus proche, tandis qu’un petit paquet marqué « Courrier en bloc » peut attendre un jour avant de passer à terre sur une série de camions.

_Plages de ports initiales recommandées_

|Type de trafic média| Plage de port source du client  |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| Entre 50 000 et 50 019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50 020–50 039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’application/d'écran| 50 040–50 059|TCP/UDP|18|Transfert garanti (AF21)|
||||||

Tenez compte des éléments suivants lorsque vous utilisez ces paramètres :

- Si vous envisagez d’implémenter ExpressRoute à l’avenir et que vous n’avez pas encore implémenté QoS, nous vous recommandons de suivre les instructions pour que les valeurs DSCP soient les mêmes de l’expéditeur au récepteur.

- Tous les clients, y compris les clients mobiles et les appareils Teams, utiliseront ces plages de ports et seront affectés par toute stratégie DSCP que vous implémentez qui utilise ces plages de ports sources. Les seuls clients qui continueront à utiliser des ports dynamiques sont les clients basés sur un navigateur (clients qui permettent aux participants de participer à des réunions à l’aide de leur navigateur).

- Bien que le client Mac utilise les mêmes plages de ports, il utilise également des valeurs codées en dur pour l’audio (EF) et la vidéo (AF41). Ces valeurs ne sont pas configurables.

- Si vous avez besoin ultérieurement d’ajuster les plages de ports pour améliorer l’expérience utilisateur, les plages de ports ne peuvent pas se chevaucher et doivent être adjacentes les unes aux autres.

## <a name="migrate-qos-to-teams"></a>Migrer QoS vers Teams

Si vous avez déjà déployé Skype Entreprise Online, y compris le balisage QoS et les plages de ports, et que vous le déployez maintenant. Teams, Teams respecte la configuration existante et utilise les mêmes plages de ports et les mêmes balises que le client Skype Entreprise. Dans la plupart des cas, aucune configuration supplémentaire n’est nécessaire.

> [!NOTE]
> Si vous utilisez le balisage QoS du nom d’application via stratégie de groupe, vous devez ajouter Teams.exe comme nom d’application.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implémenter QoS dans Teams sur Windows à l’aide de PowerShell

**Définir QoS pour l’audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Définir QoS pour la vidéo**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Définir QoS pour le partage**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestion des ports sources dans le Centre d’administration Teams

Dans Teams, les ports sources QoS utilisés par les différentes charges de travail doivent être gérés activement et ajustés si nécessaire. En faisant référence à la table dans [Choisir les plages de ports initiales pour chaque type de média](#choose-initial-port-ranges-for-each-media-type), les plages de ports sont réglables, mais les marquages DSCP ne sont pas configurables. Une fois que vous avez implémenté ces paramètres, vous constaterez peut-être que plus ou moins de ports sont nécessaires pour un type de média donné. [L’analytique des appels par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md) et le tableau de bord de qualité des appels [(CQD)](turning-on-and-using-call-quality-dashboard.md) doivent être utilisés pour prendre la décision d’ajuster les plages de ports une fois Teams implémenté, et régulièrement en fonction des besoins.

> [!NOTE]
> Si vous avez déjà configuré QoS en fonction des plages de ports sources et des marquages DSCP pour Skype Entreprise Online, la même configuration s’applique à Teams et aucune autre modification du client ou du réseau au mappage n’est nécessaire, même si vous devrez peut-être [définir les plages utilisées dans Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) pour qu’elles correspondent à ce qui a été configuré pour Skype Entreprise Online.

Si vous avez déjà déployé Skype Entreprise Server localement, vous devrez peut-être réexécuter vos stratégies QoS. Ajustez les stratégies pour qu’elles correspondent aux paramètres de plage de ports que vous avez vérifiés, ce qui offre une expérience utilisateur de qualité pour Teams.

## <a name="validate-your-qos-implementation"></a>Valider votre implémentation QoS

Pour que QoS soit efficace, la valeur DSCP définie par l’objet de stratégie de groupe doit être présente aux deux extrémités d’un appel. En analysant le trafic généré par le client Teams, vous pouvez vérifier que la valeur DSCP n’est pas modifiée ou supprimée lorsque le trafic de charge de travail Teams transite par le réseau.

De préférence, vous capturez le trafic au point de sortie du réseau. Pour cela, vous pouvez utiliser la mise en miroir de ports sur un commutateur ou un routeur.

## <a name="implement-qos-for-other-devices"></a>Implémenter QoS pour d’autres appareils

Lisez ces rubriques pour plus d’informations sur l’implémentation de QoS pour Intune, Surface, iOS, Android et Mac

- [QoS pour Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS pour Surface Hub](/surface-hub/surface-hub-qos)

- [QoS pour iOS, Android et Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Sujets associés

- [Vidéo : Planification réseau](https://aka.ms/teams-networking)

- [Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)

- [Implémenter QoS dans le client Teams](QoS-in-Teams-clients.md)