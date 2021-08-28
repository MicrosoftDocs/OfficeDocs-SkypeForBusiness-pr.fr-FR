---
title: Implémenter la qualité de service dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 3547f23d43f07d8de28ba8ca53626be119de30de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595286"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implémenter la qualité de service (QoS) dans Microsoft Teams

La qualité de service (QoS) dans Microsoft Teams permet au trafic réseau en temps réel qui est sensible aux retards réseau (par exemple, les flux vocaux ou vidéo) de « couper » devant le trafic moins sensible (par exemple, le téléchargement d’une nouvelle application, où une seconde supplémentaire à télécharger n’est pas très importante). QoS utilise Windows objets de stratégie de groupe et des listes de contrôle d’accès basées sur les ports pour identifier et marquer tous les paquets dans des flux en temps réel. Cela permet à votre réseau de fournir à vos flux voix, vidéo et partage d’écran une partie dédiée de la bande passante réseau.

Si vous supportez un groupe important d’utilisateurs qui rencontrent des problèmes décrits dans cet article, vous devrez probablement implémenter QoS. Une petite entreprise ne 1000 utilisateurs n’a peut-être pas besoin de QoS, mais même là, elle devrait être utile.

Sans QoS, vous pouvez constater les problèmes de qualité suivants dans les séquences voix et vidéo :

- Gigue – paquets multimédias qui arrivent à des taux différents, ce qui peut entraîner l’absence de mots ou de syllabes dans les appels
- Perte de paquets : perte de paquets supprimés, ce qui peut aussi réduire la qualité vocale et rendre la voix difficile à comprendre
- Retard de la durée des allers-retours (RTT) : l’accès des paquets multimédias à leurs destinations prend beaucoup de temps, ce qui provoque des retards importants entre les deux parties dans une conversation et amène les gens à discuter entre eux

La façon la plus complexe de résoudre ces problèmes consiste à augmenter la taille des connexions de données, à la fois internes et sortantes d’Internet. Étant donné que ce système est souvent interdit par les coûts, QoS offre un moyen de gérer plus efficacement les ressources dont vous disposez au lieu d’ajouter de la bande passante. Pour résoudre les problèmes de qualité, nous vous recommandons d’utiliser QoS avant d’ajouter de la bande passante uniquement si nécessaire.

Pour que QoS soit efficace, vous devez appliquer des paramètres de QoS cohérents dans votre organisation. Toute partie du chemin qui ne tient pas compte de vos priorités QoS peut dégrader la qualité des appels, de la vidéo et du partage d’écran. Cela inclut l’application de paramètres à tous les PC ou appareils des utilisateurs, aux commutateurs réseau, aux routeurs vers Internet et au service Teams service.

_Figure 1. La relation entre les réseaux d’une organisation et Microsoft 365 ou Office 365 services_

![Illustration de la relation entre les réseaux et les services](media/Qos-in-Teams-Image1.png "La relation entre les réseaux d’une organisation et les services Microsoft 365 ou Office 365 : un réseau et des périphériques locaux se connectent à un réseau interconnecté, qui se connecte à son tour à Microsoft 365 ou Office 365 Cloud Voice et aux services d’audioconférence.")

## <a name="qos-implementation-checklist"></a>Liste de contrôle de mise en œuvre de la QoS

À un niveau élevé, vous pouvez implémenter QoS comme suit :

1. [Assurez-vous que votre réseau est prêt.](#make-sure-your-network-is-ready)

1. [Sélectionnez une méthode d’implémentation de QoS.](#select-a-qos-implementation-method)

1. [Choisissez les plages de ports initiales pour chaque type de média.](#choose-initial-port-ranges-for-each-media-type)

1. Implémenter les paramètres de QoS :
   1. Sur les clients qui utilisent un objet de stratégie de groupe pour définir les plages de ports et [les marquages des appareils clients.](QoS-in-Teams-clients.md)
   2. Sur les routeurs (voir la documentation du fabricant) ou d’autres périphériques réseau. Cela peut inclure des listes de contrôle d’accès basées sur les ports, ou simplement définir les files d’attente QoS et les marquages DSCP, ou tous ces éléments.

      > [!IMPORTANT]
      > Nous vous recommandons d’implémenter ces stratégies de QoS à l’aide des ports source du client et d’une adresse IP source et de destination du « tout ». Cela capture le trafic de médias entrant et sortant sur le réseau interne.  

   3. [Définissez la façon dont vous voulez gérer le trafic de médias pour Teams réunions.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Validez l’implémentation de votre QoS](#validate-your-qos-implementation) en analysant Teams trafic sur le réseau.

Lorsque vous vous préparez à implémenter QoS, gardez les recommandations suivantes à l’esprit :

- Le chemin d’accès le Microsoft 365 le plus court est le plus court.
- La fermeture de ports entraîne uniquement une dégradation de la qualité.
- Tous les obstacles intermédiaires, tels que les proxies, ne sont pas recommandés.
- Limiter le nombre de sauts :
  - Du client au réseau de périphérie – 3 à 5 sauts
  - IsP vers le réseau de périphérie Microsoft – 3 sauts
  - Le réseau de périphérie Microsoft jusqu’à la destination finale – sans objet

Pour plus d’informations sur la configuration des ports du pare-feu, voir [Office 365 URL et plages d’adresses IP.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>Assurez-vous que votre réseau est prêt

Si vous envisagez une implémentation de la qualité de service, vous devriez déjà avoir déterminé vos besoins en bande passante et [d’autres exigences réseau.](prepare-network.md)
  
L’encombrement du trafic sur un réseau a un impact considérable sur la qualité multimédia. L’absence de bande passante entraîne une dégradation des performances et une expérience utilisateur médiocre. À mesure Teams’adoption et de l’utilisation accrues, utilisez les [rapports,](use-call-analytics-to-troubleshoot-poor-call-quality.md)l’analyse des appels par utilisateur et le tableau de bord de qualité des appels [pour](turning-on-and-using-call-quality-dashboard.md) identifier les problèmes et effectuer des ajustements à l’aide de QoS et d’ajouts sélectifs de bande passante.

### <a name="vpn-considerations"></a>Considérations en cas de réseau privé virtuel

La QoS fonctionne uniquement comme prévu lorsqu’elle est implémentée sur tous les liens entre les appelants. Si vous utilisez QoS sur un réseau interne et qu’un utilisateur se signe à partir d’un emplacement distant, vous ne pouvez donner la priorité qu’au sein de votre réseau interne géré. Bien que des emplacements distants peuvent recevoir une connexion gérée en implémentant un réseau privé virtuel (VPN), un réseau VPN ajoute intrinsèquement la surcharge des paquets et entraîne des retards dans le trafic en temps réel. Nous vous recommandons d’éviter d’utiliser le trafic de communications en temps réel sur un réseau VPN.

Dans une organisation mondiale qui gère des liens qui s’étendent sur plusieurs continents, nous recommandons vivement QoS, car la bande passante de ces liens est limitée par rapport au réseau lan.

## <a name="introduction-to-qos-queues"></a>Présentation des files d’attente QoS

Pour fournir la qualité de service, les périphériques réseau doivent avoir une façon de classifier le trafic et être capables de distinguer les messages vocaux et vidéo des autres trafics réseau.

Lorsque le trafic réseau entre un routeur, il est placé dans une file d’attente. Si une stratégie de QoS n’est pas configurée, il n’y a qu’une seule file d’attente, et toutes les données sont traitées comme le premier utilisateur, premier sorti avec la même priorité. Cela signifie que le trafic vocal (qui est très sensible aux retards) risque de rester bloqué par le trafic, pour lequel un retard de quelques millisecondes supplémentaires ne serait pas un problème.

Lorsque vous implémentez QoS, vous définissez plusieurs files d’attente à l’aide d’une des fonctionnalités de gestion de l’encombrement, telles que la mise en file d’attente de priorité de Cisco et la fonction [CBWFQ (Class-Based Weighted Fair Queueing)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) et les fonctionnalités d’évitement de congestion, telles que la détection aléatoire pondérée au plus [tôt.](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Figure 2. Exemples de files d’attente QoS_

![Illustration des files d’attente QoS et de la division de bande passante](media/Qos-in-Teams-Image2.png "La bande passante totale disponible est divisée en plusieurs files d’attente (audio, vidéo et autres types de trafic) qui ont reçu des priorités différentes.")

QoS crée des « couloirs de covoiturage » virtuels dans votre réseau de données de sorte que certains types de données ne rencontrent jamais ou rarement de retard. Une fois ces couloirs créés, vous pouvez ajuster leur taille relative et gérer beaucoup plus efficacement la bande passante de connexion dont vous avez besoin, tout en ajustant les utilisateurs de votre organisation de façon professionnelle.

## <a name="select-a-qos-implementation-method"></a>Sélectionner une méthode d’implémentation de QoS

Vous pouvez implémenter QoS via un marquage basé sur les ports, à l’aide de listes de contrôle d’accès sur les routeurs de votre réseau. Le marquage basé sur les ports est la méthode la plus fiable, car il fonctionne dans des environnements Windows, Mac et Linux et est la méthode la plus simple à implémenter. Les clients mobiles n’offrent pas de mécanisme pour marquer le trafic à l’aide de valeurs DSCP. Ils auront donc besoin de cette méthode.  

À l’aide d’un marquage basé sur les ports, le routeur de votre réseau examine un paquet entrant, et si le paquet arrivé utilise un certain port ou une certaine plage de ports, il l’identifie comme un certain type de média et le place dans la file d’attente pour ce type, en ajoutant une marque [DSCP](https://tools.ietf.org/html/rfc2474) prédéfinfine à l’en-tête de paquet IP pour que d’autres appareils reconnaissent son type de trafic et lui donnent la priorité dans sa file d’attente.

Bien que le marquage basé sur les ports fonctionne sur plusieurs plateformes, il marque uniquement le trafic sur le réseau WAN (pas jusqu’à l’ordinateur client) et crée des frais de gestion. Consultez la documentation fournie par le fabricant du routeur pour obtenir des instructions sur l’implémentation de cette méthode.

### <a name="insert-dscp-markers"></a>Insérer des marqueurs DSCP

Vous pouvez également implémenter QoS à l’aide d’un objet de stratégie de groupe pour diriger les appareils clients vers l’insertion d’un marqueur DSCP dans les en-têtes de paquets IP l’identifiant comme un type particulier de trafic (par exemple, voix). Les routeurs et autres périphériques réseau peuvent être configurés pour reconnaître ceci et placer le trafic dans une file d’attente distincte à priorité supérieure.

Bien que ce scénario soit entièrement valide, il ne fonctionne que pour les clients Windows domaine. Tout appareil qui n’est pas un client de domaine Windows n’est pas activé pour le marquage DSCP. Les autres clients, tels que ceux exécutant macOS, ont des balises codées en dur et balisent toujours le trafic.

Le fait de contrôler le marquage DSCP via un champ de groupe garantit que tous les ordinateurs joints à un domaine reçoivent les mêmes paramètres et que seul un administrateur peut les gérer. Les clients qui peuvent utiliser une GPD sont marqués sur l’appareil d’origine, puis les périphériques réseau configurés peuvent reconnaître le flux en temps réel par le code DSCP et lui donner une priorité appropriée.

### <a name="best-practice"></a>Meilleure pratique

Nous vous recommandons, si possible, une combinaison de marquages DSCP au point de terminaison et de l’ensemble des balises d’utilisation basées sur le port sur les routeurs. L’utilisation d’un stratégie de groupe pour capturer la majorité des clients, ainsi que l’utilisation d’un marquage DSCP basé sur un port garantit que les appareils mobiles, Mac et autres clients continueront à être pris en charge par la QoS (au moins partiellement).

Les marquages DSCP peuvent être marqués comme des tampons d’envoi qui indiquent aux travailleurs postaux à quel point l’envoi est urgent et comment le trier au mieux pour un envoi rapide. Une fois que vous avez configuré votre réseau pour donner la priorité aux flux multimédias en temps réel, la perte de paquets et de paquets en retard devrait diminuer considérablement.

Lorsque tous les appareils du réseau utilisent les mêmes classifications, marquages et priorités, il est possible de réduire ou d’éliminer les retards, les paquets supprimés et la gigue en modifiant la taille des plages de ports affectées aux files d’attente utilisées pour chaque type de trafic. Dans une perspective Teams, l’étape de configuration la plus importante est la classification et le marquage des paquets. Toutefois, pour que la QoS de bout en bout soit efficace, vous devez également aligner avec soin la configuration de l’application avec la configuration réseau sous-jacente. Une fois la qualité de services qoS entièrement implémentée, la gestion en continu consiste à ajuster les plages de ports affectées à chaque type de trafic en fonction des besoins et de l’utilisation réelle de votre organisation.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Choisir des plages de ports initiales pour chaque type de média

La valeur DSCP indique à un réseau configuré correspondant quelle priorité donner à un paquet ou à un flux, que la marque DSCP soit attribuée par des clients ou le réseau lui-même en fonction des paramètres de liste de distribution de données (ACL). Chaque charge de travail multimédia reçoit sa propre valeur DSCP (d’autres services peuvent autoriser les charges de travail pour le partage d’un marquage DSCP, pas des Teams non) et une plage de ports définie et distincte utilisée pour chaque type de média. D’autres environnements peuvent avoir une stratégie de QoS existante qui vous aide à déterminer la priorité des charges de travail réseau.

La taille relative des plages de ports pour différentes charges de travail de diffusion en continu en temps réel définit la proportion de la bande passante totale disponible dédiée à cette charge de travail. Pour revenir à notre analogique postal antérieure, il est possible qu’une lettre avec une lettre « Air Mail » soit envoyée dans l’heure jusqu’à l’aéroport le plus proche, tandis qu’un petit package marqué « Courrier en nombre » peut attendre un jour avant de pouvoir arriver sur une série d’aéroports.

_Plages de ports initiales recommandées_

|Type de trafic média| Plage de port source du client  |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| Entre 50 000 et 50 019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50 020–50 039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’application/d'écran| 50 040–50 059|TCP/UDP|18|Transfert garanti (AF21)|
||||||

N’ignorez pas les éléments suivants lorsque vous utilisez ces paramètres :

- Si vous envisagez d’implémenter ExpressRoute à l’avenir et que vous n’avez pas encore implémenté QoS, nous vous recommandons de suivre les instructions de sorte que les valeurs DSCP soient identiques d’un expéditeur à un récepteur.

- Tous les clients, y compris les clients mobiles et Teams, utiliseront ces plages de ports et seront affectés par toute stratégie DSCP que vous implémentez qui utilise ces plages de ports sources. Les seuls clients qui continueront d’utiliser des ports dynamiques sont les clients basés sur un navigateur (clients qui leur permet de participer à des réunions à l’aide de leur navigateur).

- Bien que le client Mac utilise les mêmes plages de ports, il utilise également des valeurs codées en dur pour l’audio (EF) et la vidéo (AF41). Ces valeurs ne sont pas configurables.

- Si vous devez par la suite ajuster les plages de ports pour améliorer l’expérience utilisateur, les plages de ports ne peuvent pas se chevaucher et doivent être adjacentes.

## <a name="migrate-qos-to-teams"></a>Migrer la QoS vers Teams

Si vous avez déjà déployé Skype Entreprise Online, y compris le marquage QoS et les plages de ports, et que vous êtes en cours de déploiement. Teams, Teams respectera la configuration existante et utilisera les mêmes plages de ports et balises que le client Skype Entreprise client. Dans la plupart des cas, aucune configuration supplémentaire n’est nécessaire.

> [!NOTE]
> Si vous utilisez le balisage QoS de nom d’application via une stratégie de groupe, vous devez ajouter Teams.exe nom d’application.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implémenter la QoS dans Teams sur une Windows à l’aide de PowerShell

**Définir la QoS pour l’audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Définir la qualité de qualité de vie pour la vidéo**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Définir la QoS pour le partage**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestion des ports sources dans le Centre Teams’administration

Dans Teams, les ports source de QoS utilisés par les différentes charges de travail doivent être gérés et ajustés en fonction des besoins. En faisant référence au tableau dans Choisir les plages de ports [initiales](#choose-initial-port-ranges-for-each-media-type)pour chaque type de média, les plages de ports sont ajustables, mais les marquages DSCP ne sont pas configurables. Une fois ces paramètres implémentés, vous découvrirez peut-être qu’un plus grand nombre de ports sont nécessaires pour un type de média donné. [](use-call-analytics-to-troubleshoot-poor-call-quality.md) L’analyse des [](turning-on-and-using-call-quality-dashboard.md) appels par utilisateur et le tableau de bord de qualité des appels doivent être utilisés pour décider d’ajuster les plages de ports une fois que Teams été implémenté, et régulièrement en cas d’évolution des besoins.

> [!NOTE]
> Si vous avez déjà configuré la QoS sur la base des plages de ports sources et des marquages DSCP pour Skype Entreprise Online, la même configuration s’applique à Teams et aucune modification apportée au mappage par le client ou le réseau n’est requise, même si vous devez définir les [plages](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) utilisées dans Teams pour qu’elles correspondent à ce qui a été configuré pour Skype Entreprise Online.

Si vous avez déjà déployé des Skype Entreprise Server local, vous devrez peut-être examiner à un autre jour vos stratégies QoS. Ajustez les stratégies pour correspondre aux paramètres de plage de ports que vous avez vérifiés et offrir une expérience utilisateur de qualité Teams.

## <a name="validate-your-qos-implementation"></a>Valider l’implémentation de votre QoS

Pour que QoS soit efficace, la valeur DSCP définie par l’stratégie de groupe doit être présente aux deux extrémités d’un appel. En analysant le trafic généré par le client Teams, vous pouvez vérifier que la valeur DSCP n’est pas modifiée ou n’est pas vidée lorsque le trafic de charge de travail Teams se déplace sur le réseau.

De préférence, vous capturez le trafic au point de sortie réseau. Pour cela, vous pouvez utiliser la mise en miroir des ports sur un commutateur ou un routeur.

## <a name="implement-qos-for-other-devices"></a>Implémenter la QoS pour d’autres appareils

Consultez ces rubriques pour plus d’informations sur l’implémentation de QoS pour Intune, Surface, iOS, Android et Mac

- [QoS pour Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS pour Surface Hub](/surface-hub/surface-hub-qos)

- [QoS pour iOS, Android et Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Rubriques connexes

- [Vidéo : Planification réseau](https://aka.ms/teams-networking)

- [Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)

- [Implémenter QoS dans le client Teams client](QoS-in-Teams-clients.md)