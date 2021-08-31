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
description: Choisissez Teams applications clientes, planifiez la qualité des points de terminaison, obtenez des recommandations pour le déploiement de Wi-Fi points de terminaison et le choix d’appareils audio.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5176f40886bdc086df43a130cb9d8414bd8f40a3
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732963"
---
# <a name="plan-my-users-experience"></a>Planifier l’expérience de mes utilisateurs

Cet article donne une vue d’ensemble des conditions requises pour identifier correctement les éléments de déploiement de vos services vocaux cloud qui affectent directement l’expérience de vos utilisateurs. En vous préparez à ces éléments avant le déploiement, vous augmentez vos chances de fournir une expérience fiable et de haute qualité aux utilisateurs. 

## <a name="client-deployment"></a>Déploiement du client

Microsoft Teams clients sont disponibles pour le web, le bureau (Windows et Mac) et les appareils mobiles (Android et iOS). Pour plus d’informations sur la manière dont les clients de bureau (Windows et Mac) et mobiles sont installés, voir Obtenir des clients pour [Microsoft Teams.](./get-clients.md)

## <a name="client-updates"></a>Mises à jour du client

L’un des principaux avantages d Teams est que le client est automatiquement tenu à jour. Les clients sur PC et Mac sont mis à jour à l'aide d'un processus en arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l'application est inactive.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planifier la qualité des points de terminaison

Comme le montre le diagramme ci-dessous, les points de terminaison jouent un rôle essentiel dans la fourniture d’une expérience de qualité aux utilisateurs.

![Diagramme décrivant les trois composants de la qualité.](media/plan-my-users-experience-image1.png "Diagramme décrivant les trois composants de la qualité et la manière dont la gestion des services chevauche les trois composants. Avec le focus sur les points de terminaison.")

Teams points de terminaison peuvent s’exécuter sur de nombreux appareils, notamment des PC, des Mac, des tablettes et des appareils mobiles. Une partie de l’expérience englobe non seulement l’appareil, mais également la façon dont un utilisateur se connecte à l’appareil, par exemple, en utilisant le micro/haut-parleur intégré de l’appareil, les écouteurs ou un casque optimisé. L'utilisation d'un casque optimisé peut enrichir l'expérience globale de l'utilisateur.

Les conseils suivants sur la planification des points de terminaison vous aideront à vous assurer que votre organisation a une expérience d'intégration réussie avec Teams.

## <a name="endpoint-capability"></a>Capacité des points de terminaison

La première partie de la planification consiste à s’assurer que tous les PC et autres appareils de votre organisation peuvent exécuter Teams. Il ne s'agit pas seulement d'examiner les exigences matérielles, mais aussi de comprendre ce que le PC fait d'autre en arrière-plan. De nombreuses organisations utilisent d'autres logiciels, y compris les systèmes de détection d'intrusion et les logiciels antimalware, qui peuvent affecter les performances de base d'un appareil.

Pour plus d’informations sur la Teams logicielles requises pour vos clients sur chaque plateforme (web, ordinateur de bureau et appareil mobile), voir Obtenir [des clients pour Microsoft Teams.](./get-clients.md)

## <a name="endpoint-firewalls"></a>Pare-feu des points de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l'expérience utilisateur.
Les pare-feu côté client peuvent affecter la qualité des appels en plus d'empêcher l'établissement d'un appel. Configurez les exclusions appropriées sur le pare-feu du client en fonction des informations Microsoft 365 ou Office 365 URL et [plages d’adresses IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Votre fournisseur tiers recevra des directives précises sur la façon de créer les exclusions.

>[!NOTE]
> Les équipes Microsoft mettront automatiquement à jour le pare-feu Windows avec une configuration de pare-feu appropriée.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recommandations Wi-Fi pour les points de terminaison

Le déploiement d’un réseau Wi-Fi réseau optimisé pour prendre en charge les charges de travail en temps réel dans Microsoft Teams prend en charge une planification Microsoft Teams. Les sections suivantes fournissent des instructions générales qui peuvent vous aider à éviter les pièges courants lors de la planification de points de terminaison.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Certains Wi-Fi pilotes peuvent être problématiques. Par exemple, un pilote peut avoir des comportements d'itinérance très agressifs entre les points d'accès, provoquant une mauvaise qualité d'appel.
Cette occurrence n’est pas courante, mais il est important de vous assurer que les pilotes Wi-Fi sur PC ont été mis à jour et testés avant le déploiement.

### <a name="wi-fi-bands"></a>Bandes Wi-Fi

Il existe principalement deux types de bandes utilisées aujourd'hui dans les équipements Wi-Fi : 2,4 GHz et 5,0 GHz. Si votre organisation fournit les deux bandes, vous devez configurer les paramètres de votre pilote pour préférer la bande 5,0 GHz. Cette bande est beaucoup plus dense en termes de débit et est moins affectée par les interférences observées dans la bande de 2,4 GHz.
Cette recommandation suppose que vous avez correctement optimisé la bande de réseau de 5,0 GHz.

### <a name="wi-fi-radio-type"></a>Type de radio Wi-Fi

Prévoyez des appareils qui prennent en charge les nouveaux types de radio Wi-Fi. Vous pouvez obtenir de très bonnes performances Wi-Fi si vous utilisez 802.11ac ou plus récent sur les appareils que vous approvisionnez.

### <a name="wireless-avoidance"></a>Évitement sans fil

Certaines organisations préfèrent éviter complètement le Wi-Fi. Parfois, ces conseils sont fournis par le biais d'une recommandation aux utilisateurs de se connecter directement à un réseau câblé. Dans certains cas, l'ordre de liaison réseau peut avoir la préférence pour la connexion sans fil et continuer à utiliser cette connexion même si le PC est connecté à la connexion câblée. Pour éviter ce scénario involontaire, configurez l'ordre de liaison.

### <a name="80211-power-save-protocol"></a>802.11 Protocole Power Save

Si votre organisation utilise des points d’accès sans fil ou des routeurs qui ne prend pas en charge le protocole Power Save 802.11, vous risquez de vivre des appels supprimés ou une qualité d’appel médiocre dans Microsoft Teams s’exécutant sur des appareils Windows. Si la mise à niveau de votre point d'accès sans fil ou de vos routeurs est impossible, vous devez mettre à jour les paramètres du plan d'alimentation Windows sur les appareils fonctionnant sur batterie. De plus amples détails et des conseils de configuration sont fournis dans l'[article de support](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you) suivant.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Quels Teams clients seront déployés dans votre organisation ?</li><li>Comment allez-vous déployer initialement Teams clients vers vos utilisateurs ?</li><li>Qui d’évaluation des points de terminaison et des appareils afin de vérifier qu’ils répondent Teams conditions requises pour une expérience de qualité ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Documenter le processus qui sera suivi pour déployer Teams clients.</li><li>Évaluez les points de terminaison et les appareils, et effectuez les corrections requises.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Appareils pour Teams

Microsoft Teams peut être utilisé pour des réunions ou comme système téléphonique. Lors de l'utilisation de ces fonctions, le dispositif d'interface utilisé pour Teams joue un rôle important dans l'expérience utilisateur.

L'utilisation d'un haut-parleur et d'un microphone d’ordinateur portable intégrés peut sembler acceptable pour l'utilisateur qui dispose de cette configuration. En règle générale, ces appareils ne sont pas optimisés pour l’annulation du bruit et tout type de bruit ambiant peut avoir un impact en aval sur les autres personnes qui font l’appel. L'utilisation d'appareils optimisés pour ces scénarios contribuera à assurer une expérience de haute qualité.

Chaque appareil doit répondre aux besoins de vos utilisateurs. Vous devrez adapter les appareils tels que les casques pour les différentes personnes et les cas d'utilisation dans votre organisation.
Un exercice de mappage personne à appareil devrait être effectué dans le cadre du processus de planification.

Une fois que vous avez sélectionné les appareils, incluez-les dans le plan d'essai pilote pour la validation finale. Tirez parti des sondages pendant le projet pilote pour recueillir des commentaires afin de vous assurer que la stratégie de votre appareil est optimale.

> [!NOTE]
> Pour l'instant, nous vous recommandons d'utiliser des appareils audio certifiés dans le cadre du programme de certification Skype Entreprise. Pour rechercher les périphériques certifiés dans le cadre de ce programme, consultez les périphériques [Microsoft Teams et](https://products.office.com/microsoft-teams/across-devices/devices) les périphériques audio et [vidéo USB.](/SkypeForBusiness/certification/devices-usb-devices)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Déterminez la stratégie globale de votre organisation en matière d’appareils pour les utilisateurs et les salles de réunion.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Effectuer un exercice de mappage de personnage sur appareil pour votre organisation.</li><li>Documenter le processus d’obtention des périphériques pour les utilisateurs et les salles de réunion.</li><li>Documentez le processus de déploiement et de configuration des appareils pour les utilisateurs et les salles de réunion.</li><li>Procurez-vous les appareils initiaux pour commencer votre déploiement.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->