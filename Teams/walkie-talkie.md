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
ms.openlocfilehash: c19894106dfd06c13ec9936657837aa42fcdade0
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2022
ms.locfileid: "62015014"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Application Walkie Talkie dans Microsoft Teams

L’application Walkie Talkie dans Teams fournit une communication push-to-talk instantanée pour votre équipe et est désormais disponible sur Android & iOS. Walkie Talkie permet aux utilisateurs de se connecter à leur équipe à l’aide des mêmes canaux sous-jacents dont ils sont membres. Seuls les utilisateurs qui se connectent à Walkie Talkie dans un canal deviennent des participants et peuvent communiquer les uns avec les autres à l’aide du push-to-talk, un par un.

Avec Walkie Talkie dans Teams, les travailleurs de première ligne peuvent désormais communiquer en toute sécurité avec une expérience PTT familière sans avoir à transporter des radios volumineuses, et Walkie Talkie fonctionne n’importe où avec la connectivité Internet WiFi ou cellulaire.

## <a name="getting-started"></a>Prise en main

### <a name="deploying-walkie-talkie"></a>Déploiement de Walkie Talkie

Walkie Talkie est pris en charge sur les appareils Android avec les appareils Google Mobile Services (GMS) et iOS. 

Actuellement, Walkie Talkie n’est pas préinstallé. Pour activer cette fonctionnalité pour les utilisateurs de votre organisation, vous devez ajouter Walkie Talkie à la stratégie  [d’installation](teams-app-setup-policies.md)  de l’application attribuée aux utilisateurs à partir du [centre d’administration Teams](https://admin.teams.microsoft.com/). Une fois activé, Walkie Talkie sera disponible sur l’application dans les 48 heures.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Ajout de Walkie Talkie à votre liste d’applications

Dans le centre d’administration Microsoft Teams, sous Teams stratégies **appSetup** > , **l’option Autoriser l’épinglage utilisateur** doit être **activée.** Ensuite, sous la section Applications épinglées, cliquez sur **+Ajouter des applications**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Affiche la section Applications épinglées et le bouton Ajouter des applications à sélectionner.":::

Dans le panneau **Ajouter des applications épinglées** qui s’affiche à droite, utilisez la zone de texte **Rechercher** pour rechercher Walkie Talkie. Lorsque vous l’avez comme résultat de recherche, sélectionnez le bouton **Ajouter** à droite du nom pour l’ajouter à votre liste.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Affiche la barre latérale Ajouter des applications épinglées avec Walkie entré dans le volet de recherche et l’application Walkie Talkie dans les résultats de la recherche, avec le bouton Ajouter en regard de celui-ci.":::

L’application Walkie Talkie doit maintenant apparaître dans la liste des applications épinglées et être utilisable une fois que vous avez cliqué sur le bouton **Enregistrer** .

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Affiche la liste des applications épinglées avec l’application Walkie Talkie ajoutée et le bouton Enregistrer sous la liste.":::

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

- ITAdmins peut contrôler qui utilise Walkie Talkie via les stratégies d’application.
- Si votre employé de première ligne utilise des données mobiles pour communiquer via Teams, Walkie Talkie utilise la même méthode.
- Walkie Talkie doit bien fonctionner dans les situations de faible bande passante, ou les situations où votre smartphone est connecté et fonctionne. Walkie Talkie ne fonctionnera pas quand il n’y a aucune connectivité du tout.

Pour plus d’informations sur l’expérience de l’utilisateur final, consultez :

- [Démarrage avec Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Communiquer avec votre équipe avec Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
