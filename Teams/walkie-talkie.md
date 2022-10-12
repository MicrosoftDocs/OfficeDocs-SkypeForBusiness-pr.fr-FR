---
title: Application Walkie Talkie dans Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Comment configurer l’application Walkie Talkie dans Microsoft Teams, du point de vue de l’administrateur informatique.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0475fd161d3b53a8fc60d3a1419d20e3de2bfada
ms.sourcegitcommit: bb428cd5805151736f0a6786d737f67f2b3fc918
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68557477"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Application Walkie Talkie dans Microsoft Teams

L’application Walkie Talkie dans Teams fournit une communication push-to-talk (PTT) instantanée pour votre équipe et est disponible sur Android et iOS. Walkie Talkie permet aux utilisateurs de se connecter à leur équipe à l’aide des mêmes canaux sous-jacents dont ils sont membres. Seuls les utilisateurs qui se connectent à Walkie Talkie dans un canal deviennent des participants et peuvent communiquer les uns avec les autres à l’aide du push-to-talk, un par un.

Avec Walkie Talkie dans Teams, les employés de première ligne peuvent communiquer en toute sécurité avec une expérience PTT familière sans avoir à transporter des radios volumineuses, et Walkie Talkie fonctionne n’importe où avec la connectivité Internet WiFi ou cellulaire.

> [!NOTE]
> Walkie Talkie n’est actuellement pas disponible en Chine.

## <a name="license-requirements"></a>Exigences en matière de licence

Walkie Talkie est inclus dans toutes les licences payantes de Teams dans [Microsoft 365 et les abonnements Office 365](/office365/servicedescriptions/teams-service-description). Pour plus d’informations sur l’obtention de Teams, consultez [Comment faire accéder à Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b) ?

## <a name="deploying-walkie-talkie"></a>Déploiement de Walkie Talkie

Walkie Talkie est pris en charge sur les appareils Android avec Google Mobile Services (GMS) et les appareils iOS.

> [!NOTE]
> Si vos utilisateurs utilisent des accessoires Bluetooth, assurez-vous que votre solution de gestion des appareils mobiles (GPM) ne bloque pas les appareils Bluetooth.

### <a name="enable-or-disable-walkie-talkie-in-your-organization"></a>Activer ou désactiver Walkie Talkie dans votre organisation

Walkie Talkie est activé par défaut pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Applications Teams** > **Gérer les applications**.
2. Dans la liste des applications, recherchez l’application Walkie Talkie, sélectionnez-la, puis basculez le bouton bascule **État** sur **Bloqué** ou **Autorisé**.

### <a name="enable-or-disable-walkie-talkie-for-specific-users-in-your-organization"></a>Activer ou désactiver Walkie Talkie pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Walkie Talkie, assurez-vous que Walkie Talkie est activé pour votre organisation sur la page [Gérer les applications](manage-apps.md) . Créez ensuite une stratégie d’autorisation d’application personnalisée, ajoutez-la à une stratégie d’installation d’application et attribuez-la à ces utilisateurs. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md) et [Gérer les stratégies d’installation d’application dans Microsoft Teams](teams-app-setup-policies.md).

### <a name="pin-walkie-talkie-to-teams"></a>Épingler Walkie Talkie à Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Utiliser l’expérience d’application de première ligne personnalisée pour épingler Walkie Talkie et d’autres applications à Teams

L’expérience d’application de première ligne personnalisée dans Teams épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Les applications épinglées incluent Walkie Talkie, Shifts, Tasks et Approvals. Par défaut, cette fonctionnalité est activée, ce qui offre à vos employés de première ligne une expérience prêt à l’emploi adaptée à leurs besoins.

Les applications sont épinglées à la barre de l’application , la barre située sur le côté du client de bureau Teams et en bas des clients mobiles Teams, où les utilisateurs peuvent y accéder rapidement et facilement.

Pour en savoir plus, notamment sur le fonctionnement de l’expérience avec les stratégies d’application que vous définissez, consultez [Personnaliser les applications Teams pour vos employés de première ligne](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Utiliser une stratégie d’installation d’application pour épingler Walkie Talkie à Teams

Les stratégies d’installation d’application vous permettent de personnaliser Teams pour épingler les applications les plus importantes pour vos utilisateurs dans vos utilisateurs.

Pour épingler l’application Walkie Talkie pour vos utilisateurs, vous pouvez modifier la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et affecter une stratégie d’installation d’application personnalisée. Pour plus d’informations, consultez l’article [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Capture d’écran montrant l’ajout de Walkie Talkie à la liste des applications épinglées dans le volet Ajouter des applications épinglées." lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>Documentation réseau

Walkie Talkie dans Teams nécessite une connectivité Internet. Les conditions réseau suivantes sont requises pour une expérience optimale.

|Mesure | Obligatoire |
|---|---|
|Latence (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Perte de paquets |< 1 % |

Comme indiqué ci-dessus, la qualité des médias en temps réel sur un réseau IP est considérablement affectée par la qualité de la connectivité réseau, mais surtout par la quantité de :

- **Latence** : temps nécessaire pour obtenir un paquet IP du point A au point B sur le réseau. Ce délai de propagation réseau est essentiellement lié à la distance physique entre les deux points et à la vitesse de la lumière, y compris une surcharge plus élevée prise par les différents routeurs entre les deux. La latence est mesurée en temps aller-retour (RTT).
- **Gigue entre les arrivées** : variation moyenne du délai entre les paquets successifs.
- **Perte de paquets** : la perte de paquets est souvent définie comme un pourcentage de paquets perdus dans une fenêtre donnée. La perte de paquets affecte directement la qualité audio, des petits paquets perdus individuels qui n’ont presque aucun impact aux pertes de rafales dos à dos qui entraînent une coupure audio complète.

L’utilisation attendue des données de Walkie Talkie est d’environ 20 Ko/s lors de l’envoi ou de la réception d’audio. En cas d’inactivité, l’utilisation attendue des données de Walkie Talkie est négligeable.

## <a name="walkie-talkie-devices"></a>Appareils Walkie Talkie

Les employés de première ligne ont souvent besoin de parler et de recevoir des appels Talkie Walkie, même lorsque leur téléphone est verrouillé. Cette expérience est possible via des appareils spécialisés avec un bouton PTT dédié.

#### <a name="headsets"></a>Casques

- Casques sans fil (iOS et Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Casques câblés (Android uniquement)
  - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>Téléphones Android robustes

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-s4-1004010501053.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) et [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - Configuration manuelle : une fois Teams installé, accédez aux **boutons Paramètres** > . Sur le bouton Dédié (1 ou 2), sélectionnez **Appuyez longuement**, puis choisissez **l’application PTT**. Sélectionnez la roue bleue en regard de **Custom**, puis sélectionnez **Teams**.
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) et [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - Configuration manuelle : une fois Teams installé, accédez aux **clés programmables** **paramètres** > . Choisissez **la touche PTT** ou **Appuyez longuement** (selon l’appareil), puis sélectionnez **Teams**.
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer), [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer), [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp), [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer), [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer), [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer), 
  - Configuration manuelle : Avec Teams installé, le bouton PTT dédié fonctionne avec Walkie Talkie par défaut.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - Configuration manuelle : une fois Teams installé, accédez à La **clé XCover/Active** **des fonctionnalités avancées des paramètres** >  > . Activez la **touche Control XCover avec l’application** , puis sélectionnez **Teams**.
  - [Configuration MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - Configuration manuelle : une fois Teams installé, accédez aux **clés programmables** **des paramètres** > . **Sélectionnez Sélectionner l’application PTT Key**, puis Sélectionnez **Teams**.
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - Configuration manuelle : Une fois Teams installé, le bouton PTT dédié (LEFT_TRIGGER_2) fonctionne avec Walkie Talkie par défaut.

> [!NOTE]
> Ces appareils ne sont pas certifiés Teams. Ils ont été validés pour travailler avec Le Talkie Walkie Teams.

## <a name="more-information"></a>Plus d’informations

- Si votre worker de première ligne utilise des données mobiles pour communiquer via Teams, Walkie Talkie utilise la même méthode.
- Walkie Talkie doit bien fonctionner dans les situations de faible bande passante, ou les situations où votre smartphone est connecté et fonctionne. Walkie Talkie ne fonctionnera pas quand il n’y a aucune connectivité du tout.

Pour en savoir plus sur l’expérience de l’utilisateur final, consultez :

- [Prise en main de Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Communiquer avec votre équipe avec Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
