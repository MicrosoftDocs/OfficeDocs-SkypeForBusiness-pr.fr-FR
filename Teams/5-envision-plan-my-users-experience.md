---
title: Planifier l’expérience des utilisateurs de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Sélectionnez applications clientes Teams, planifiez la qualité du point de terminaison, obtenez des recommandations pour le déploiement de points de terminaison Wi-Fi et le choix de périphériques audio.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d156761d8ebc39822d6ccf2fc28ed6c380c4e117
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825182"
---
# <a name="plan-my-users-experience"></a>Planifier l’interface de mes utilisateurs

Cet article fournit une vue d’ensemble des exigences relatives à l’identification correcte des éléments de votre déploiement de services vocaux Cloud qui affectent directement l’interface de vos utilisateurs. En préservant ces éléments avant le déploiement, vous augmentez vos chances d’offrir à vos utilisateurs une interface fiable de grande qualité. 

## <a name="client-deployment"></a>Déploiement du client

Microsoft teams est disponible pour les clients Web, de bureau (Windows et Mac) et mobiles (Android et iOS). Pour plus d’informations sur l’installation de la version de bureau de bureau (Windows et Mac) et des clients mobiles, voir [obtenir des clients pour Microsoft teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Mises à jour du client

L’un des principaux avantages de teams est que le client est automatiquement mis à jour. Les clients sur PC et Mac sont mis à jour à l'aide d'un processus en arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l'application est inactive.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planifier la qualité des points de terminaison

Comme vous pouvez le voir dans le diagramme ci-dessous, les points de terminaison constituent un bloc de construction important pour offrir une qualité optimale aux utilisateurs.

![Diagramme décrivant les trois composantes de la qualité](media/plan-my-users-experience-image1.png "Diagramme décrivant les trois composantes de la qualité et la façon dont la gestion de service empiète sur les trois composants. Le focus est axé sur les points de terminaison.")

Les points de terminaison teams peuvent s’exécuter sur de nombreux appareils, notamment les PC, Mac, tablettes et appareils mobiles. Une partie de l’expérience n’englobe pas uniquement le périphérique, mais le mode de connexion de l’utilisateur à l’appareil (par exemple, à l’aide du micro/haut-parleur intégré du périphérique, de confortables ou d’un casque optimisé). L'utilisation d'un casque optimisé peut enrichir l'expérience globale de l'utilisateur.

Les conseils suivants sur la planification des points de terminaison vous aideront à vous assurer que votre organisation a une expérience d'intégration réussie avec Teams.

## <a name="endpoint-capability"></a>Capacité des points de terminaison

Dans la première partie de la planification, vous devez vous assurer que tous les PC et autres appareils de votre organisation peuvent exécuter Teams. Il ne s'agit pas seulement d'examiner les exigences matérielles, mais aussi de comprendre ce que le PC fait d'autre en arrière-plan. De nombreuses organisations utilisent d'autres logiciels, y compris les systèmes de détection d'intrusion et les logiciels antimalware, qui peuvent affecter les performances de base d'un appareil.

Pour plus d’informations sur la configuration logicielle requise pour les clients teams sur chaque plateforme (Web, ordinateur de bureau et appareil mobile), voir [obtenir des clients pour Microsoft teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Pare-feu des points de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l'expérience utilisateur.
Les pare-feu côté client peuvent affecter la qualité des appels en plus d'empêcher l'établissement d'un appel. Configurez les exclusions appropriées sur le pare-feu du client en fonction des informations contenues dans [Plages d'adresses URL et IP d’Office 365](https://aka.ms/o365ips). Votre fournisseur tiers recevra des directives précises sur la façon de créer les exclusions.

>[!NOTE]
> Les équipes Microsoft mettront automatiquement à jour le pare-feu Windows avec une configuration de pare-feu appropriée.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recommandations Wi-Fi pour les points de terminaison

Il est important de planifier le déploiement d’un réseau Wi-Fi optimisé pour prendre en charge les charges de travail en temps réel dans Microsoft Teams. Les sections suivantes fournissent des recommandations générales qui peuvent vous aider à éviter des pièges courants lors de la planification de points de terminaison.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Certains pilotes Wi-Fi peuvent poser problème. Par exemple, un pilote peut avoir des comportements d'itinérance très agressifs entre les points d'accès, provoquant une mauvaise qualité d'appel.
Ce n’est pas une occurrence courante, mais il est important de veiller à ce que les pilotes Wi-Fi sur le PC aient été mis à jour et testés avant de procéder au déploiement.

### <a name="wi-fi-bands"></a>Bandes Wi-Fi

Il existe principalement deux types de bandes utilisées aujourd'hui dans les équipements Wi-Fi : 2,4 GHz et 5,0 GHz. Si votre organisation fournit les deux bandes, vous devez configurer les paramètres de votre pilote pour préférer la bande 5,0 GHz. Cette bande est beaucoup plus dense en termes de débit et est moins affectée par les interférences observées dans la bande de 2,4 GHz.
Cette recommandation suppose que vous avez correctement optimisé la bande de réseau de 5,0 GHz.

### <a name="wi-fi-radio-type"></a>Type de radio Wi-Fi

Prévoyez des appareils qui prennent en charge les nouveaux types de radio Wi-Fi. Vous pouvez obtenir de très bonnes performances Wi-Fi si vous utilisez 802.11ac ou plus récent sur les appareils que vous approvisionnez.

### <a name="wireless-avoidance"></a>Évitement sans fil

Certaines organisations préfèrent éviter complètement le Wi-Fi. Parfois, ces conseils sont fournis par le biais d'une recommandation aux utilisateurs de se connecter directement à un réseau câblé. Dans certains cas, l'ordre de liaison réseau peut avoir la préférence pour la connexion sans fil et continuer à utiliser cette connexion même si le PC est connecté à la connexion câblée. Pour éviter ce scénario involontaire, configurez l'ordre de liaison.

### <a name="80211-power-save-protocol"></a>802,11 Power Save Protocol

Si votre organisation utilise des points d’accès sans fil ou des routeurs qui ne prennent pas en charge le protocole Power Save de 802,11, il est possible que vous rencontriez des appels interrompus ou une mauvaise qualité d’appel dans Microsoft teams sur les appareils Windows. Si la mise à niveau de votre point d'accès sans fil ou de vos routeurs est impossible, vous devez mettre à jour les paramètres du plan d'alimentation Windows sur les appareils fonctionnant sur batterie. De plus amples détails et des conseils de configuration sont fournis dans l'[article de support](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you) suivant.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Quels clients teams seront déployés au sein de votre organisation ?</li><li>Comment allez-vous déployer initialement les clients teams pour vos utilisateurs ?</li><li>Qui est responsable de l’évaluation des points de terminaison et des appareils pour vérifier qu’ils répondent aux exigences d’une équipe en matière de qualité ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Document le processus qui sera suivi pour le déploiement de clients Teams.</li><li>Évaluez les points de terminaison et les périphériques, puis effectuez et remédiez aux problèmes.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Appareils pour Teams

Microsoft Teams peut être utilisé pour des réunions ou comme système téléphonique. Lors de l'utilisation de ces fonctions, le dispositif d'interface utilisé pour Teams joue un rôle important dans l'expérience utilisateur.

L'utilisation d'un haut-parleur et d'un microphone d’ordinateur portable intégrés peut sembler acceptable pour l'utilisateur qui dispose de cette configuration. En règle générale, ces appareils ne sont pas optimisés pour l’annulation du bruit et tout type de bruit ambiant peut avoir une incidence en aval sur les autres participants. L'utilisation d'appareils optimisés pour ces scénarios contribuera à assurer une expérience de haute qualité.

Chaque appareil doit répondre aux besoins de vos utilisateurs. Vous devrez adapter les appareils tels que les casques pour les différentes personnes et les cas d'utilisation dans votre organisation.
Un exercice de mappage personne à appareil devrait être effectué dans le cadre du processus de planification.

Une fois que vous avez sélectionné les appareils, incluez-les dans le plan d'essai pilote pour la validation finale. Tirez parti des sondages pendant le projet pilote pour recueillir des commentaires afin de vous assurer que la stratégie de votre appareil est optimale.

> [!NOTE]
> Pour l'instant, nous vous recommandons d'utiliser des appareils audio certifiés dans le cadre du programme de certification Skype Entreprise. Pour rechercher des périphériques certifiés dans le cadre de ce programme, voir les appareils [Microsoft teams](https://products.office.com/en-us/microsoft-teams/across-devices/devices) et les [périphériques audio et vidéo USB](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices).



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Décider de la stratégie d’appareil globale de votre organisation pour les expériences utilisateur et salle de réunion.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Effectuez un exercice de mappage de personne à appareil pour votre organisation.</li><li>Documentez le processus d’obtention d’appareils pour les utilisateurs et les salles de réunion.</li><li>Documentez le processus de déploiement et de configuration des appareils pour les utilisateurs et les salles de réunion.</li><li>Pour commencer votre déploiement, vous pouvez procéder de la sorte.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
