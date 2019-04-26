---
title: Planifier l’expérience des utilisateurs de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Choisissez les applications de client équipes, plan pour la qualité du point de terminaison, consultez les recommandations pour le déploiement de systèmes d’extrémité Wi-Fi et choix de périphériques audio.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: abef4c9e1096396d7844002ebda38a32876b403b
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304364"
---
# <a name="plan-my-users-experience"></a>Planifier l’expérience des utilisateurs

Cet article donne une vue d’ensemble de la configuration requise pour identifier correctement les éléments de votre déploiement de services de cloud voice qui affectent directement l’expérience des utilisateurs. En préparation pour ces éléments avant le déploiement, vous allez augmenter vos chances de correctement proposer une expérience fiable, de haute qualité pour les utilisateurs. 

## <a name="client-deployment"></a>Déploiement du client

Microsoft Teams a clients disponibles pour le site web, du bureau (Windows et Mac) et mobile (Android et e/s). Pour plus d’informations sur la façon dont les clients mobiles et bureau (Windows et Mac) sont installés, voir [obtenir des clients pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Mises à jour du client

Un des principaux avantages des équipes est que le client est mis à jour automatiquement. Les clients sur PC et Mac sont mis à jour à l'aide d'un processus en arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l'application est inactive.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planifier la qualité des points de terminaison

Comme vous pouvez le constater dans le diagramme ci-dessous, points de terminaison sont un bloc de construction important à fournir une expérience de qualité pour les utilisateurs.

![Diagramme décrivant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur les points de terminaison.] (media/plan-my-users-experience-image1.png "Diagramme décrivant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur les points de terminaison.")

Points de terminaison équipes peuvent s’exécuter sur de nombreux périphériques, y compris les PC, Mac, tablettes et les appareils mobiles. Partie de l’expérience englobe non seulement l’appareil, mais comment un utilisateur se connecte à l’appareil — par exemple, à l’aide de micro/haut-parleur intégré du périphérique, écouteurs par ou un casque optimisé. L'utilisation d'un casque optimisé peut enrichir l'expérience globale de l'utilisateur.

Les conseils suivants sur la planification des points de terminaison vous aideront à vous assurer que votre organisation a une expérience d'intégration réussie avec Teams.

## <a name="endpoint-capability"></a>Capacité des points de terminaison

La première partie de la planification consiste à vérifier tous les PC et autres périphériques de votre organisation peuvent exécuter des équipes. Il ne s'agit pas seulement d'examiner les exigences matérielles, mais aussi de comprendre ce que le PC fait d'autre en arrière-plan. De nombreuses organisations utilisent d'autres logiciels, y compris les systèmes de détection d'intrusion et les logiciels antimalware, qui peuvent affecter les performances de base d'un appareil.

Pour plus d’informations sur la configuration logicielle requise pour les équipes de clients sur chaque plateforme (web, du bureau et mobile), voir [obtenir des clients pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Pare-feu des points de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l'expérience utilisateur.
Les pare-feu côté client peuvent affecter la qualité des appels en plus d'empêcher l'établissement d'un appel. Configurez les exclusions appropriées sur le pare-feu du client en fonction des informations contenues dans [Plages d'adresses URL et IP d’Office 365](https://aka.ms/o365ips). Votre fournisseur tiers recevra des directives précises sur la façon de créer les exclusions.

>[!NOTE]
> Les équipes Microsoft mettront automatiquement à jour le pare-feu Windows avec une configuration de pare-feu appropriée.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recommandations Wi-Fi pour les points de terminaison

Important l’intention de déployer un réseau Wi-Fi optimisé pour prendre en charge des charges de travail en temps réel dans Microsoft Teams nécessaire. Les sections suivantes fournissent des conseils d’ordre général qui peuvent vous aider à éviter les pièges courants lors de la planification des points de terminaison.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Certains pilotes Wi-Fi peuvent être problématiques. Par exemple, un pilote peut avoir des comportements d'itinérance très agressifs entre les points d'accès, provoquant une mauvaise qualité d'appel.
Ce n’est pas une occurrence courants, mais il est important de s’assurer que les pilotes Wi-Fi sur le PC ont été mis à jour et testés avant le déploiement.

### <a name="wi-fi-bands"></a>Bandes Wi-Fi

Il existe principalement deux types de bandes utilisées aujourd'hui dans les équipements Wi-Fi : 2,4 GHz et 5,0 GHz. Si votre organisation fournit les deux bandes, vous devez configurer les paramètres de votre pilote pour préférer la bande 5,0 GHz. Cette bande est beaucoup plus dense en termes de débit et est moins affectée par les interférences observées dans la bande de 2,4 GHz.
Cette recommandation suppose que vous avez correctement optimisé la bande de réseau de 5,0 GHz.

### <a name="wi-fi-radio-type"></a>Type de radio Wi-Fi

Prévoyez des appareils qui prennent en charge les nouveaux types de radio Wi-Fi. Vous pouvez obtenir de très bonnes performances Wi-Fi si vous utilisez 802.11ac ou plus récent sur les appareils que vous approvisionnez.

### <a name="wireless-avoidance"></a>Évitement sans fil

Certaines organisations préfèrent éviter complètement le Wi-Fi. Parfois, ces conseils sont fournis par le biais d'une recommandation aux utilisateurs de se connecter directement à un réseau câblé. Dans certains cas, l'ordre de liaison réseau peut avoir la préférence pour la connexion sans fil et continuer à utiliser cette connexion même si le PC est connecté à la connexion câblée. Pour éviter ce scénario involontaire, configurez l'ordre de liaison.

### <a name="80211-power-save-protocol"></a>802.11 protocole d’économie d’énergie

Si votre organisation utilise des points d’accès sans fil ou des routeurs qui ne prennent pas en charge le protocole d’économie d’énergie 802.11, vous pouvez être confronté appels abandonnés ou la qualité des appels médiocre dans Teams Microsoft en cours d’exécution sur les périphériques Windows. Si la mise à niveau de votre point d'accès sans fil ou de vos routeurs est impossible, vous devez mettre à jour les paramètres du plan d'alimentation Windows sur les appareils fonctionnant sur batterie. De plus amples détails et des conseils de configuration sont fournis dans l'[article de support](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you) suivant.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Les clients équipes seront déployés dans votre organisation ?</li><li>Comment allez-vous initialement déployer les clients équipes à vos utilisateurs ?</li><li>Qui est responsable de l’évaluation des systèmes d’extrémité et des périphériques pour valider ils répondent aux exigences d’équipes pour une bonne qualité ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documenter la procédure à suivre pour déployer des clients équipes.</li><li>Évaluer les points de terminaison et les périphériques et effectuer et correction requis.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Appareils pour Teams

Microsoft Teams peut être utilisé pour des réunions ou comme système téléphonique. Lors de l'utilisation de ces fonctions, le dispositif d'interface utilisé pour Teams joue un rôle important dans l'expérience utilisateur.

L'utilisation d'un haut-parleur et d'un microphone d’ordinateur portable intégrés peut sembler acceptable pour l'utilisateur qui dispose de cette configuration. En règle générale, ces périphériques ne sont pas optimisés pour la suppression du bruit, mais n’importe quel type de bruit peut avoir un impact en aval sur d’autres lors de l’appel. L'utilisation d'appareils optimisés pour ces scénarios contribuera à assurer une expérience de haute qualité.

Chaque appareil doit répondre aux besoins de vos utilisateurs. Vous devrez adapter les appareils tels que les casques pour les différentes personnes et les cas d'utilisation dans votre organisation.
Un exercice de mappage personne à appareil devrait être effectué dans le cadre du processus de planification.

Une fois que vous avez sélectionné les appareils, incluez-les dans le plan d'essai pilote pour la validation finale. Tirez parti des sondages pendant le projet pilote pour recueillir des commentaires afin de vous assurer que la stratégie de votre appareil est optimale.

> [!NOTE]
> Pour l'instant, nous vous recommandons d'utiliser des appareils audio certifiés dans le cadre du programme de certification Skype Entreprise. Pour rechercher des périphériques certifiés sous ce programme, voir le catalogue de solutions [Certifiés de périphériques USB pour Skype pour les entreprises](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez la stratégie de périphérique globale de votre organisation pour des utilisateurs et les expériences de salle de réunion.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Effectuer un exercice personnage-à mappage des périphériques pour votre organisation.</li><li>Le processus permettant d’obtenir des périphériques pour les utilisateurs et les salles de réunion du document.</li><li>Le processus de déploiement et configuration des périphériques pour les utilisateurs et les salles de réunion du document.</li><li>Se procurer les appareils pour commencer votre déploiement initiales.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->