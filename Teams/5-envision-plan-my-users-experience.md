---
title: Plan d’expérience des utilisateurs de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Choisissez les applications client équipes, le plan de la qualité du point de terminaison, obtenir des recommandations pour le déploiement des points de terminaison Wi-Fi et de choisir les périphériques audio.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 866395a4dd58016c0989ec4b34f602877251d021
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="plan-my-users-experience"></a>Plan d’expérience de mes utilisateurs

Cet article donne une vue d’ensemble de la configuration requise pour identifier correctement les éléments de votre déploiement des services cloud voix qui affectent directement d’expérience de vos utilisateurs. En préparant pour ces éléments avant le déploiement, vous augmentez vos chances d’avec succès en fournissant une expérience de haute qualité et fiable pour les utilisateurs. 

## <a name="client-deployment"></a>Déploiement du client

Teams de Microsoft est disponible pour le web, de postes de travail clients (Windows et Mac) et mobile (iOS, Android et Windows Phone). Pour plus d’informations sur la façon dont le bureau (Windows et Mac) et les clients mobiles sont installés, consultez [obtenir des clients pour les équipes de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Mises à jour client

Un des principaux avantages des équipes est que le client est mis à jour automatiquement. Les clients sur les PC et les Mac sont mis à jour à l’aide d’un processus en arrière-plan qui vérifie les versions nouvelles et télécharge le nouveau client lorsque l’application est inactive.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Prévoir la qualité du point de terminaison

Comme vous pouvez le voir dans le schéma ci-dessous, les points de terminaison sont un bloc de construction important en offrant aux utilisateurs une expérience de qualité.

![Diagramme décrivant les trois composants de qualité et de la gestion des services superpose à toutes les trois composants. En mettant l’accent sur les points de terminaison.] (media/plan-my-users-experience-image1.png "Diagramme décrivant les trois composants de qualité et de la gestion des services superpose à toutes les trois composants. En mettant l’accent sur les points de terminaison.")

Les points de terminaison équipes peuvent s’exécuter sur de nombreux périphériques, notamment des PC, Mac, tablettes et les périphériques mobiles. Partie de l’expérience englobe non seulement le périphérique, mais comment un utilisateur se connecte au périphérique — par exemple, à l’aide de microphone/haut-parleur intégré du périphérique, écouteurs par ou un casque optimisé. À l’aide d’un casque optimisé peut enrichir de l’expérience utilisateur globale.

Les conseils suivants concernant la planification de point de terminaison vous permettra d’assurer que votre organisation a une intégration réussie d’expérience avec les équipes.

## <a name="endpoint-capability"></a>Fonction de point de terminaison

La première partie de la planification est de s’assurer de tous les PC et autres périphériques de votre organisation peuvent exécuter des équipes. Ceci implique non seulement en examinant la configuration matérielle requise, mais également comprendre quelles sont les autres PC fait en arrière-plan. De nombreuses organisations à exécuter d’autres logiciels, y compris les systèmes de détection d’intrusion et le logiciel contre les logiciels malveillants, qui peut affecter les performances de base d’un périphérique.

Pour plus d’informations sur la configuration logicielle requise pour les équipes clients sur chaque plate-forme (web, bureau et mobile), reportez-vous à la section [obtenir des clients pour les équipes de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Pare-feux de point de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l’expérience de l’utilisateur.
Les pare-feu côté client peuvent affecter la qualité prévenir un appel à l’établissement de l’appel. Configurez les exclusions à appropriés sur le pare-feu du client basé sur les informations contenues dans [les URL d’Office 365 et de plages d’adresses IP](https://aka.ms/o365ips). Votre fournisseur tiers auront des recommandations spécifiques sur la façon de créer des exclusions.

>[!NOTE]
> Teams Microsoft met automatiquement à jour le pare-feu Windows avec une configuration de pare-feu appropriée.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recommandations de Wi-Fi pour les points de terminaison

Il faut significative de planification du déploiement d’un réseau Wi-Fi optimisé pour prendre en charge les charges de travail en temps réel dans Microsoft Teams. Les sections suivantes fournissent des indications générales qui peuvent vous aider à éviter les pièges courants à éviter lors de la planification des points de terminaison.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Certains pilotes Wi-Fi peuvent être problématiques. Par exemple, un pilote peut avoir très agressifs comportements itinérants entre points d’accès, provoque l’appel de mauvaise qualité.
Ce n’est pas une occurrence courante, mais il est important de s’assurer que les pilotes Wi-Fi sur le PC ont été mis à jour et testés avant le déploiement.

### <a name="wi-fi-bands"></a>Bandes de Wi-Fi

Il existe principalement deux types de bandes utilisés dans les équipements informatiques de Wi-Fi, 2,4 GHz et 5,0 GHz. Si votre organisation fournit les deux bandes, vous devez configurer les paramètres de votre pilote pour le choix de la bande GHz 5.0. Cette bande est beaucoup plus dense en termes de débit et est moins affectés par l’interférence dans la bande des 2,4 GHz.
Cette recommandation suppose que vous avez correctement optimisé de la bande de réseau 5,0 GHz.

### <a name="wi-fi-radio-type"></a>Type de radio Wi-Fi

Plan pour les périphériques prenant en charge les nouveaux types de radio Wi-Fi. Vous pouvez obtenir de très bonnes performances Wi-Fi si vous utilisez 802.11ac ou plus récente sur les périphériques que vous mettez en service.

### <a name="wireless-avoidance"></a>Évitement sans fil

Certaines organisations préfèrent éviter Wi-Fi. Parfois, ce guide est fourni via une recommandation pour les utilisateurs de se connecter directement à un réseau câblé. Dans certains cas, l’ordre de liaison réseau peut avoir la connexion sans fil préférée et continuer à utiliser cette connexion, même si l’ordinateur est connecté à la connexion filaire. Pour éviter ce comportement involontaire, configurez l’ordre de liaison pour éviter ce scénario.

### <a name="80211-power-save-protocol"></a>802.11 protocole d’économie d’énergie de

Si votre organisation utilise des points d’accès sans fil ou les routeurs qui ne prennent pas en charge le protocole d’économie d’énergie 802.11, vous pouvez rencontrer des appels abandonnés ou qualité médiocre appel dans Teams de Microsoft en cours d’exécution sur les périphériques Windows. Si elle n’est pas possible de mettre à jour votre point d’accès sans fil ou des routeurs, vous devez mettre à jour Windows, alimentation des paramètres sur les équipements fonctionnant sur batterie. Des instructions supplémentaires de détail et de la configuration sont fournie dans la [prise en charge de l’article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)de suivant.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Les clients d’équipes seront déployés dans votre organisation ?</li><li>Comment vous déployez initialement aux équipes des clients à vos utilisateurs ?</li><li>Qui est chargé d’évaluer les points de terminaison et les périphériques pour valider ils satisfont aux exigences d’équipes pour une expérience de qualité ?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Documenter la procédure à suivre pour déployer des clients des équipes.</li><li>Évaluer les points de terminaison et les périphériques et effectuer et les mesures correctives nécessaires.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Périphériques pour les équipes

Microsoft Teams peut être utilisés pour les réunions ou sous la forme d’un système téléphonique. Lors de l’utilisation de ces fonctionnalités, le périphérique d’interface qui est utilisé pour les équipes joue un rôle important dans l’expérience de l’utilisateur.

À l’aide d’un haut-parleur du PC et un microphone intégrés peut paraître acceptable pour l’utilisateur qui a cette configuration. En règle générale, ces périphériques ne sont pas optimisés pour l’annulation de bruit, mais n’importe quel type de bruit peut avoir un impact en aval sur d’autres lors de l’appel. Exploitation des périphériques optimisés pour ces scénarios afin de garantir une expérience de qualité.

Chaque périphérique doit répondre aux besoins de vos utilisateurs. Vous devez adapter les périphériques tels que les casques pour les personnages différents et en cas d’utilisation dans votre organisation.
Un exercice de personnage-de mappage des périphériques doit être effectué dans le cadre du processus de planification.

Une fois que vous avez sélectionné les périphériques, les inclure dans le plan de test pilote pour la validation finale. Exploitez les enquêtes au cours de l’étape pilote afin de recueillir des commentaires afin de votre stratégie de périphérique est optimal.

> [!NOTE]
> À ce stade, nous recommandons d’utiliser des périphériques audio qui ont été certifiés par le biais de la Skype pour le programme de Certification d’entreprise. Pour rechercher des périphériques certifiés sous ce programme, consultez le catalogue de solutions [Certifié de périphériques USB pour Skype pour les entreprises](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Décider de la stratégie de votre organisation globale de périphérique de l’utilisateur et l’expérience de la salle de réunion.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Effectuer un exercice de mappage du personnage-dispositif pour votre organisation.</li><li>Documenter le processus d’obtention des périphériques pour les utilisateurs et les salles de réunion.</li><li>Documenter le processus de déploiement et configuration des périphériques pour les utilisateurs et les salles de réunion.</li><li>Se procurer des périphériques initiales pour commencer votre déploiement.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->