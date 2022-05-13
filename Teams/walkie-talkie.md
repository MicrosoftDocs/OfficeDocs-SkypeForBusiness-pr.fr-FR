---
title: Application Walkie Talkie dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Comment configurer l’application Walkie Talkie dans Microsoft Teams, du point de vue d’ITAdmin.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29a632efc433a14d578eff80fdeb74a6f167dfc3
ms.sourcegitcommit: a388fd72e399f6e205c34707dc92cc309997e737
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2022
ms.locfileid: "65400230"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Application Walkie Talkie dans Microsoft Teams

L’application Walkie Talkie dans Teams fournit une communication push-to-talk instantanée pour votre équipe et est désormais disponible sur Android & iOS. Walkie Talkie permet aux utilisateurs de se connecter à leur équipe à l’aide des mêmes canaux sous-jacents dont ils sont membres. Seuls les utilisateurs qui se connectent à Walkie Talkie dans un canal deviennent des participants et peuvent communiquer les uns avec les autres à l’aide du push-to-talk, un par un.

Avec Walkie Talkie dans Teams, les travailleurs de première ligne peuvent désormais communiquer en toute sécurité avec une expérience PTT familière sans avoir à transporter des radios volumineuses, et Walkie Talkie fonctionne n’importe où avec la connectivité Internet WiFi ou cellulaire.

> [!NOTE]
> Walkie Talkie n’est actuellement pas disponible en Chine.

## <a name="getting-started"></a>Prise en main

### <a name="deploying-walkie-talkie"></a>Déploiement de Walkie Talkie

Walkie Talkie est pris en charge sur les appareils Android avec Google Mobile Services (GMS) et les appareils iOS.

### <a name="pin-walkie-talkie-to-teams"></a>Épingler Walkie Talkie à Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Utilisez l’expérience d’application de première ligne personnalisée pour épingler Walkie Talkie et d’autres applications à Teams

L’expérience d’application de première ligne personnalisée dans Teams épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Les applications épinglées incluent Walkie Talkie, Shifts, Tasks et Approbations. Par défaut, cette fonctionnalité est activée, ce qui offre à vos employés de première ligne une expérience prêt à l’emploi adaptée à leurs besoins.

Les applications sont épinglées à la barre de l’application , la barre située sur le côté du client de bureau Teams et en bas de la Teams clients mobiles, où les utilisateurs peuvent y accéder rapidement et facilement.

Pour en savoir plus, notamment sur le fonctionnement de l’expérience avec les stratégies d’application que vous définissez, consultez [Tailor Teams apps pour vos employés de première ligne](pin-teams-apps-based-on-license.md).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Utiliser une stratégie d’installation d’application pour épingler Walkie Talkie à Teams

Les stratégies d’installation d’application vous permettent de personnaliser Teams pour épingler les applications les plus importantes pour vos utilisateurs dans vos utilisateurs.

Pour épingler l’application Walkie Talkie pour vos utilisateurs, vous pouvez modifier la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et affecter une stratégie d’installation d’application personnalisée. Pour plus d’informations, consultez l’article [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Capture d’écran montrant l’ajout de Walkie Talkie à la liste des applications épinglées dans le volet Ajouter des applications épinglées." lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>Documentation réseau

Walkie Talkie dans Teams nécessite une connectivité Internet et en dessous des conditions réseau sont requises pour une expérience optimale.

|Mesure | Obligatoire |
|---|---|
|Latence (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Perte de paquets |< 1 % |

Comme indiqué ci-dessus, la qualité des médias en temps réel sur un réseau IP est considérablement affectée par la qualité de la connectivité réseau, mais surtout par la quantité de :

- **Latence** : il s’agit du temps nécessaire pour obtenir un paquet IP du point A au point B sur le réseau. Ce délai de propagation réseau est essentiellement lié à la distance physique entre les deux points et à la vitesse de la lumière, y compris une surcharge plus élevée prise par les différents routeurs entre les deux. La latence est mesurée en temps aller-retour (RTT).
- **Gigue entre les arrivées** : il s’agit de la variation moyenne du délai entre les paquets successifs.
- **Perte de paquets** : il s’agit souvent d’un pourcentage de paquets perdus dans une fenêtre donnée. La perte de paquets affecte directement la qualité audio, des petits paquets perdus individuels n’ayant presque aucun impact aux pertes de rafales dos à dos qui entraînent une coupure audio complète.

L’utilisation attendue des données de Walkie Talkie est d’environ 20 Ko/s lors de l’envoi ou de la réception d’audio. En cas d’inactivité, l’utilisation attendue des données de Walkie Talkie est négligeable.

### <a name="walkie-talkie-devices"></a>Appareils Walkie Talkie

Les employés de première ligne ont souvent besoin de parler et de recevoir des appels Talkie Walkie, même lorsque leur téléphone est verrouillé. Cette expérience est possible via des appareils spécialisés avec un bouton PTT dédié.

- **Casques**
  - Casques sans fil (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Casques câblés (Android uniquement)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Téléphones Android robustes**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - Configuration manuelle : une fois Teams installés, accédez à Paramètres > Fonctionnalités avancées > clé XCover/Active. Activez « Contrôler la clé XCover avec l’application », puis sélectionnez « Teams ».
    - [Configuration MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Configuration manuelle : avec Teams installé, le bouton PTT dédié (LEFT_TRIGGER_2) fonctionne avec Walkie Talkie par défaut
    
> [!NOTE]
> Ces appareils ne sont pas certifiés Teams. Ils ont été validés pour travailler avec Teams Talkie Walkie.

### <a name="license-requirements"></a>Exigences en matière de licence

L’application Walkie Talkie est incluse dans toutes les licences payantes de Teams dans [Office 365 abonnements](/office365/servicedescriptions/teams-service-description). Pour plus d’informations sur l’obtention de Teams, consultez  [Comment faire accéder à Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b) ?

## <a name="further-information"></a>Plus d’informations

- Les administrateurs informatiques peuvent contrôler qui utilise Walkie Talkie via les stratégies d’application.
- Si votre employé de première ligne utilise des données mobiles pour communiquer via Teams, Walkie Talkie utilise la même méthode.
- Walkie Talkie doit bien fonctionner dans les situations de faible bande passante, ou les situations où votre smartphone est connecté et fonctionne. Walkie Talkie ne fonctionnera pas quand il n’y a aucune connectivité du tout.

Pour plus d’informations sur l’expérience de l’utilisateur final, consultez :

- [Démarrage avec Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Communiquer avec votre équipe avec Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
