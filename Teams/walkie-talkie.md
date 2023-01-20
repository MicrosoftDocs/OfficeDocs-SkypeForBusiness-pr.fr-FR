---
title: Application Talkie-walkie dans Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Comment configurer l’application Talkie-walkie dans Microsoft Teams, du point de vue de l’administrateur informatique.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.date: 11/17/2022
ms.openlocfilehash: c4184e82e99fa4f3169fea14c62f3a892750bf8c
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845891"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Application Talkie-walkie dans Microsoft Teams

L’application Talkie-walkie dans Teams fournit une communication push-to-talk (PTT) instantanée pour votre équipe et est disponible sur Android et iOS. Talkie-walkie permet aux utilisateurs de se connecter à leur équipe à l’aide des mêmes canaux sous-jacents dont ils sont membres.

Seuls les utilisateurs qui se connectent au talkie-walkie dans un canal deviennent des participants et peuvent communiquer entre eux à l’aide de PTT. Les utilisateurs continueront à recevoir des transmissions jusqu’à ce qu’ils appuient sur  **Déconnecter**.

Avec talkie-walkie dans Teams, les utilisateurs peuvent communiquer en toute sécurité avec une expérience PTT familière sans avoir à transporter des radios volumineuses, et Talkie-walkie fonctionne n’importe où avec une connectivité Wi-Fi ou Internet cellulaire.

> [!NOTE]
> Talkie-walkie n’est actuellement pas disponible en Chine.

## <a name="license-requirements"></a>Conditions requises pour les licences

Talkie-walkie est inclus dans toutes les licences payantes de Teams dans les [abonnements Microsoft 365 et Office 365](/office365/servicedescriptions/teams-service-description). Pour plus d’informations sur l’obtention de Teams, consultez [Comment faire obtenir Microsoft Teams ?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploying-walkie-talkie"></a>Déploiement de Talkie-walkie

Talkie-walkie est pris en charge sur les appareils Android avec les appareils Google Mobile Services (GMS) et iOS.

### <a name="step-1-make-sure-walkie-talkie-is-enabled-in-your-organization"></a>Étape 1 : Vérifier que talkie-walkie est activé dans votre organisation

Par défaut, l’application Talkie-walkie est activée pour tous les utilisateurs Teams de votre organisation.

Vous contrôlez si l’application est disponible au niveau de l’organisation dans la page [Gérer les applications](manage-apps.md) du Centre d’administration Microsoft Teams. Pour vérifier que l’application est activée dans votre organisation :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Applications** >  Teams **Gérer les applications**.
2. Dans la liste des applications, recherchez l’application Talkie-walkie, sélectionnez-la, puis vérifiez que le bouton bascule **État** est défini sur **Autorisé**.

Si vous souhaitez autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser talkie-walkie, assurez-vous que talkie-walkie est activé pour votre organisation dans la page [Gérer les applications](manage-apps.md) . Créez ensuite une stratégie personnalisée pour les autorisations d’application et affectez-la à ces utilisateurs. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

### <a name="step-2-pin-walkie-talkie-to-teams"></a>Étape 2 : Épingler Talkie Walkie à Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Utiliser l’expérience d’application de première ligne personnalisée pour épingler Walkie Talkie et d’autres applications à Teams

L’expérience d’application de première ligne personnalisée dans Teams épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Les applications épinglées incluent Talkie-walkie, Shifts, Tasks et Approvals. Par défaut, cette fonctionnalité est activée, ce qui offre à vos employés de première ligne une expérience prête à l’emploi adaptée à leurs besoins.

Les applications sont épinglées à la barre d’état des applications en bas des clients mobiles Teams, où les utilisateurs peuvent y accéder rapidement et facilement.

Pour en savoir plus, notamment sur le fonctionnement de l’expérience avec les stratégies d’application que vous définissez, consultez [Personnaliser des applications Teams pour vos employés de première ligne](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Utiliser une stratégie de configuration d’application pour épingler Walkie Talkie à Teams

Les stratégies de configuration des applications vous permettent de personnaliser Teams pour épingler les applications les plus importantes pour vos utilisateurs.

Pour épingler l’application Talkie-walkie pour vos utilisateurs, vous pouvez modifier la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer une stratégie personnalisée dans la stratégie de configuration de l’application. Pour plus d’informations, consultez l’article [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Capture d’écran montrant l’ajout de Talkie-walkie à la liste des applications épinglées dans le volet Ajouter des applications épinglées." lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>Documentation réseau

Talkie-walkie dans Teams nécessite une connectivité Internet. Les conditions réseau suivantes sont requises pour une expérience optimale.

|Mesure | Obligatoire |
|---|---|
|Latence (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Perte de paquets |< 1 % |

Comme indiqué ci-dessus, la qualité des médias en temps réel sur un réseau IP est fortement affectée par la qualité de la connectivité réseau, mais surtout par la quantité de :

- **Latence** : temps nécessaire pour obtenir un paquet IP du point A au point B sur le réseau. Ce retard de propagation du réseau est essentiellement lié à la distance physique entre les deux points et à la vitesse de la lumière, y compris une surcharge plus importante prise par les différents routeurs entre les deux. La latence est mesurée en temps aller-retour (RTT).
- **Gigue entre les arrivées** : variation moyenne du délai entre paquets successifs.
- **Perte de paquets** : la perte de paquets est souvent définie comme un pourcentage de paquets perdus dans une fenêtre de temps donnée. La perte de paquets affecte directement la qualité audio, des petits paquets individuels perdus qui n’ont presque aucun impact aux pertes de rafale dos à dos qui provoquent un découpage audio complet.

L’utilisation attendue des données du Talkie-walkie est d’environ 20 Ko/s lors de l’envoi ou de la réception de l’audio. En cas d’inactivité, l’utilisation attendue des données du Talkie-walkie est négligeable.

## <a name="walkie-talkie-devices"></a>Appareils Talkie-walkie

Les travailleurs de première ligne ont souvent besoin de parler et de recevoir des appels talkie-walkie, même lorsque leurs téléphones sont verrouillés. Cette expérience est possible via des appareils spécialisés avec un bouton PTT dédié.

#### <a name="headsets"></a>Casques

- Casques sans fil (iOS et Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Casques câblés (Android uniquement)
  - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>Téléphones Android robustes

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-x4-1001010801327.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) et [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - Configuration manuelle : Avec Teams installé, accédez à **Paramètres** > **Boutons**. Sur le bouton Dédié (1 ou 2), sélectionnez **Appui long**, puis choisissez **Application PTT**. Sélectionnez la roue bleue en regard de **Personnalisé**, puis sélectionnez **Teams**.
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) et [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - Configuration manuelle : Avec Teams installé, accédez à **Paramètres** > **Clés programmables**. Choisissez **la touche PTT** ou **Appuyez longuement** (selon l’appareil), puis sélectionnez **Teams**.
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer), [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer), [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp), [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer), [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer), [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer), 
  - Configuration manuelle : Avec Teams installé, le bouton PTT dédié fonctionne avec talkie-walkie par défaut.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - Configuration manuelle : Avec Teams installé, accédez à **Paramètres** > **Fonctionnalités avancées** > **XCover/Touche active**. Activez **Contrôler la clé XCover avec l’application** et sélectionnez **Teams**.
  - [Configuration de GPM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - Configuration manuelle : Une fois Teams installé, accédez à **Paramètres** > **Clés programmables**. Choisissez **Sélectionner l’application Clé PTT**, puis **Sélectionnez Teams**.
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - Configuration manuelle : Avec Teams installé, le bouton PTT dédié (LEFT_TRIGGER_2) fonctionne avec talkie-walkie par défaut.

> [!NOTE]
> Ces appareils ne sont pas certifiés Teams. Ils ont été validés pour fonctionner avec Talkie Walkie Teams.

## <a name="bluetooth-devices"></a>Appareils Bluetooth

> [!NOTE]
> Si vos utilisateurs utilisent des accessoires Bluetooth, assurez-vous que votre solution de gestion des appareils mobiles (GPM) ne bloque pas les appareils Bluetooth.

Sur les appareils exécutant Android OS version 12 ou ultérieure, les autorisations Bluetooth sont requises et les autorisations d’emplacement pour se connecter à l’aide de la pile BLE ne sont plus nécessaires. Si les « autorisations de proximité » ne sont pas accordées au niveau de Teams, un utilisateur reçoit une invite d’autorisations Bluetooth. Cette invite s’affiche, qu’un accessoire Bluetooth, tel qu’un casque, soit connecté ou non à son appareil. Si un accessoire Bluetooth est connecté, appuyez sur **Autoriser** pour connecter talkie-walkie à l’accessoire Bluetooth.

## <a name="get-insight-into-walkie-talkie-usage-and-performance"></a>Obtenir des informations sur l’utilisation et les performances de Talkie-Walkie

Le [rapport d’utilisation et de performances talkie-walkie](teams-analytics-and-reports/walkie-talkie-usage-report.md) dans le Centre d’administration Teams vous donne une vue d’ensemble de l’activité et des performances talkie-walkie dans votre organisation. Le rapport fournit des informations telles que le nombre de transmissions PTT effectuées et reçues, l’activité du canal, la durée de transmission et les détails de l’appareil et du participant.

## <a name="more-information"></a>Plus d’informations

- Si les utilisateurs utilisent des données mobiles pour communiquer via Teams, talkie-walkie utilise la même méthode.
- Talkie-walkie doit fonctionner correctement dans les situations de faible bande passante, ou dans les situations où votre smartphone est connecté et fonctionne. Talkie-walkie ne fonctionne pas quand il n’y a pas de connectivité du tout.

Pour en savoir plus sur l’expérience de l’utilisateur final, consultez :

- [Prise en main de Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Communiquer avec votre équipe avec talkie-walkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
