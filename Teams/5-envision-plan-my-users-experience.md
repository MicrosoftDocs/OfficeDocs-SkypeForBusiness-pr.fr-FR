---
title: Planifier l’expérience des utilisateurs de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Choisissez les applications de client équipes, plan pour la qualité du point de terminaison, consultez les recommandations pour le déploiement de systèmes d’extrémité Wi-Fi et choix de périphériques audio.
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76bacfe85fce14b2d5b1469295134e560c14c54a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373291"
---
# <a name="plan-my-users-experience"></a>Planifier l’expérience des utilisateurs

Cet article donne une vue d’ensemble de la configuration requise pour identifier correctement les éléments de votre déploiement de services de cloud voice qui affectent directement l’expérience des utilisateurs. En préparation pour ces éléments avant le déploiement, vous allez augmenter vos chances de correctement proposer une expérience fiable, de haute qualité pour les utilisateurs. 

## <a name="client-deployment"></a>Déploiement du client

Microsoft Teams a clients disponibles pour le site web, du bureau (Windows et Mac) et mobile (Android, iOS et Windows Phone). Pour plus d’informations sur la façon dont les clients mobiles et bureau (Windows et Mac) sont installés, voir [obtenir des clients pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Mises à jour du client

Un des principaux avantages des équipes est que le client est mis à jour automatiquement. Les clients sur le PC et Mac sont mis à jour à l’aide d’un processus d’arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l’application est inactive.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Plan pour la qualité du point de terminaison

Comme vous pouvez le constater dans le diagramme ci-dessous, points de terminaison sont un bloc de construction important à fournir une expérience de qualité pour les utilisateurs.

![Diagramme décrivant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur les points de terminaison.] (media/plan-my-users-experience-image1.png "Diagramme décrivant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur les points de terminaison.")

Points de terminaison équipes peuvent s’exécuter sur de nombreux périphériques, y compris les PC, Mac, tablettes et les appareils mobiles. Partie de l’expérience englobe non seulement l’appareil, mais comment un utilisateur se connecte à l’appareil — par exemple, à l’aide de micro/haut-parleur intégré du périphérique, écouteurs par ou un casque optimisé. À l’aide d’un casque optimisé permettre enrichir l’expérience utilisateur globale.

Les instructions suivantes sur la planification de point de terminaison vous aideront à vérifier que votre organisation dispose d’une intégration réussie expérience des équipes.

## <a name="endpoint-capability"></a>Fonctionnalité du point de terminaison

La première partie de la planification consiste à vérifier tous les PC et autres périphériques de votre organisation peuvent exécuter des équipes. Cela implique pas la consultation de la configuration matérielle requise, mais également comprendre que fait le PC en arrière-plan. Bon nombre d’organisations exécuter d’autres logiciels, y compris les systèmes de détection d’intrusion et logiciels anti-programmes malveillants, ce qui peut affecter les performances de base d’un périphérique.

Pour plus d’informations sur la configuration logicielle requise pour les équipes de clients sur chaque plateforme (web, du bureau et mobile), voir [obtenir des clients pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Pare-feu de point de terminaison

Pare-feu côté client peuvent avoir un impact significatif sur l’expérience utilisateur.
Pare-feu côté client peuvent affecter la qualité des appels en plus empêche l’établissement d’un appel. Configurez les exclusions appropriées sur le pare-feu du client en fonction des informations dans [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips). Votre fournisseur tiers auront des instructions spécifiques sur la façon de créer les exclusions.

>[!NOTE]
> Microsoft Teams met automatiquement à jour le pare-feu Windows avec une configuration de pare-feu appropriée.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recommandations en matière de points de terminaison Wi-Fi

Important l’intention de déployer un réseau Wi-Fi optimisé pour prendre en charge des charges de travail en temps réel dans Microsoft Teams nécessaire. Les sections suivantes fournissent des conseils d’ordre général qui peuvent vous aider à éviter les pièges courants lors de la planification des points de terminaison.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Certains pilotes Wi-Fi peuvent être problématiques. Par exemple, un pilote peut avoir très agressifs comportements itinérance entre les points d’accès, entraînant l’appel de mauvaise qualité.
Ce n’est pas une occurrence courants, mais il est important de s’assurer que les pilotes Wi-Fi sur le PC ont été mis à jour et testés avant le déploiement.

### <a name="wi-fi-bands"></a>Bandes Wi-Fi

Il existe principalement deux types de bandes utilisées dans Wi-Fi équipement aujourd'hui, 2,4 GHz et GHz 5.0. Si votre organisation fournit les deux bandes, vous devez configurer les paramètres de votre pilote pour préfèrent la bande GHz 5.0. Cette bande est beaucoup plus dense en termes de débit et moins affectés à des interférences apparaît dans la bande 2,4 GHz.
Cette recommandation suppose que vous avez correctement optimisé la bande de réseau GHz 5.0.

### <a name="wi-fi-radio-type"></a>Type de radio Wi-Fi

Planifier les appareils qui prennent en charge les nouveaux types de radio Wi-Fi. Vous pouvez obtenir très bonnes performances Wi-Fi, notamment si vous faites 802.11ac ou plus récente sur les appareils que vous mettez en service.

### <a name="wireless-avoidance"></a>Réductions sans fil

Certaines organisations préfèrent éviter Wi-Fi. Parfois ce guide est fourni par le biais de recommandation pour les utilisateurs se connectent directement à un réseau câblé. Dans certains cas, l’ordre de liaison réseau peut-être par défaut de la connexion sans fil et continuer à utiliser cette connexion, même si l’ordinateur est connecté à une connexion câblée. Pour éviter ce comportement involontaire, configurez l’ordre de liaison pour éviter ce scénario.

### <a name="80211-power-save-protocol"></a>802.11 protocole d’économie d’énergie

Si votre organisation utilise des points d’accès sans fil ou des routeurs qui ne prennent pas en charge le protocole d’économie d’énergie 802.11, vous pouvez être confronté appels abandonnés ou la qualité des appels médiocre dans Teams Microsoft en cours d’exécution sur les périphériques Windows. Si elle n’est pas possible de mettre à niveau votre point d’accès sans fil ou les routeurs, vous devez mettre à jour Windows Power planifier les paramètres sur les appareils qui s’exécutent sur la batterie. Conseils de détail et de configuration supplémentaire est fournie dans le suivants [prennent en charge de l’article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Les clients équipes seront déployés dans votre organisation ?</li><li>Comment allez-vous initialement déployer les clients équipes à vos utilisateurs ?</li><li>Qui est responsable de l’évaluation des systèmes d’extrémité et des périphériques pour valider ils répondent aux exigences d’équipes pour une bonne qualité ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documenter la procédure à suivre pour déployer des clients équipes.</li><li>Évaluer les points de terminaison et les périphériques et effectuer et correction requis.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Périphériques pour les équipes

Microsoft Teams utilisable pour les réunions ou en tant qu’un système téléphonique. Lorsque vous utilisez ces fonctionnalités, le périphérique d’interface qui est utilisé pour les équipes joue un rôle important dans l’expérience utilisateur.

À l’aide d’un haut-parleur PC et un microphone intégrés peut sembler acceptable pour l’utilisateur ayant cette configuration. En règle générale, ces périphériques ne sont pas optimisés pour la suppression du bruit, mais n’importe quel type de bruit peut avoir un impact en aval sur d’autres lors de l’appel. Tirer parti des appareils optimisés pour ces scénarios afin de garantir une expérience de haute qualité.

Chaque périphérique doit répondre aux besoins de vos utilisateurs. Vous devrez adapter les appareils tels que des casques pour les personnages différents et en cas d’utilisation dans votre organisation.
Un exercice personnage-à mappage des périphériques doit être effectué dans le cadre du processus de planification.

Une fois que vous avez sélectionné les périphériques, les inclure dans le plan de test pilote pour la validation finale. Tirer parti des enquêtes pendant le pilote pour recueillir les commentaires pour vous assurer de votre stratégie de périphérique est optimal.

> [!NOTE]
> À ce stade, nous recommandons l’utilisation de périphériques audio qui ont été certifiés par le biais de la Skype pour le programme de Certification d’entreprise. Pour rechercher des périphériques certifiés sous ce programme, voir le catalogue de solutions [Certifiés de périphériques USB pour Skype pour les entreprises](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez la stratégie de périphérique globale de votre organisation pour des utilisateurs et les expériences de salle de réunion.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Effectuer un exercice personnage-à mappage des périphériques pour votre organisation.</li><li>Le processus permettant d’obtenir des périphériques pour les utilisateurs et les salles de réunion du document.</li><li>Le processus de déploiement et configuration des périphériques pour les utilisateurs et les salles de réunion du document.</li><li>Se procurer les appareils pour commencer votre déploiement initiales.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->