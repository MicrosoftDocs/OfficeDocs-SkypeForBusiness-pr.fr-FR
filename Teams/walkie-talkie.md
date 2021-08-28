---
title: Application Talkie-walkie dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Configuration de l’application Talkie-walkie Microsoft Teams du point de vue ITAdmin.
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
ms.openlocfilehash: 80aedfd0c1bb4f4a20ecdfcd977ce74d667cad43
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602069"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Application Talkie-walkie dans Microsoft Teams

L’application Talkie-walkie Teams propose des communications PTT (Instant Push-to-Talk) pour votre équipe et est désormais disponible sur Android. Le Talkie-walkie permet aux utilisateurs de se connecter à leur équipe en utilisant les mêmes canaux sous-jacents que ceux dont ils sont membres. Seuls les utilisateurs qui se connectent au Talkie-walkie dans un canal deviennent des participants et peuvent communiquer entre eux par push-to-talk, un par un.

Grâce au Talkie-walkie Teams, les employés en avant-plan peuvent désormais communiquer en toute sécurité avec une expérience PTT familière sans avoir à transporter des radios volumineuses, et Talkie-walkie fonctionne en tout lieu avec le WiFi ou la connectivité Internet cellulaire.

## <a name="getting-started"></a>Prise en main

### <a name="deploying-walkie-talkie"></a>Déploiement de Talkie-walkie

Actuellement, le Talkie-walkie est disponible pour les appareils Android avec Google Mobile Services (GMS) et n’est pas préinstallé. Pour activer cette fonctionnalité pour les utilisateurs de votre organisation, vous devez ajouter le Talkie-walkie à la stratégie de configuration d’application qui est affectée aux utilisateurs à partir du Centre [](teams-app-setup-policies.md)   [Teams’administration.](https://admin.teams.microsoft.com/) Une fois activée, le Talkie-walkie sera disponible sur l’application Android dans les 48 heures.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Ajout d’un Talkie-walkie à votre liste d’applications

Dans le centre Microsoft Teams d’administration, sous Teams d’installation de l’application, vous devez définir l’accès à l’épinglage utilisateur   >  sur **On.**  Sous la section Applications épinglées, cliquez **sur +Ajouter des applications.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Section Applications épinglées et bouton Ajouter des applications à sélectionner.":::

Dans le **panneau Ajouter des applications épinglées** qui apparaît à droite, utilisez la zone de texte Rechercher pour rechercher talkie-walkie.  Lorsque vous l’avez comme résultat  de recherche, sélectionnez le bouton Ajouter à droite du nom pour l’ajouter à votre liste.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Affiche la barre latérale Ajouter des applications épinglées avec le walkie entré dans le volet de recherche et l’application Talkie-walkie dans les résultats de recherche, avec le bouton Ajouter à côté.":::

L’application Talkie-walkie doit maintenant apparaître dans la liste Applications épinglées et peut être utilisé une fois que vous cliquez sur **le bouton** Enregistrer.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Affiche la liste des applications épinglées avec l’application Talkie-walkie ajoutée et le bouton Enregistrer sous la liste.":::

### <a name="network-documentation"></a>Documentation réseau

Le Talkie-walkie Teams nécessite une connectivité Internet. En dessous des conditions réseau, une expérience optimale est requise.

|Mesure | Obligatoire |
|---|---|
|Latence (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Perte de paquets |< 1 % |

Comme indiqué ci-dessus, la qualité des médias en temps réel sur un réseau IP est largement impactée par la qualité de la connectivité du réseau, mais surtout par la quantité de :

- **Latence** - Il s’agit du temps que prend l’accès d’un paquet IP d’un point A à un point B sur le réseau. Ce retard de propagation sur le réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, ce qui comprend une surcharge des divers routeurs entre les deux. La latence se mesure en durée de l’aller-retour (Round-trip Time, RTT).
- **Gigue entre les arrivées** : il s’agit de la variation moyenne de délai entre les paquets successifs.
- **Perte de paquets** - Souvent définie comme le pourcentage de paquets perdus dans une période donnée. La perte de paquets affecte directement la qualité audio, de petits paquets individuels perdus, pratiquement sans impact, aux pertes en rafale dos-à-dos à l’origine de coupures audio complètes.

L’utilisation attendue des données de Talkie-walkie est d’environ 20 Ko lors de l’envoi ou de la réception d’audio. Lorsqu’elles sont inactives, l’utilisation attendue des données de Talkie-walkie est en veille.

### <a name="walkie-talkie-devices"></a>Talkie-walkie

Les employés en ligne doivent souvent parler et recevoir des appels Walkie Talkie même lorsque leur téléphone est verrouillé. Cette expérience est possible via des appareils spécialisés avec un bouton PTT dédié.

- **Casques**
  - Casques sans fil 
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Casques câblés 
    - [Tous les autres appareils sont en place.](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Téléphones accidentés**
  - Samsung [Galaxy XCover Pro,](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/) [Galaxy XCover 5,](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy) [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    -  Configuration manuelle : une fois Teams, accédez aux fonctionnalités Paramètres > avancées > XCover/Active. Activer « Touche Contrôle XCover avec l’application » et sélectionner « Teams »
    -  [Configuration de la gestion des mdm](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Ces appareils ne sont pas Teams certifiés. Ils ont été validés pour fonctionner avec Teams Talkie-walkie.

### <a name="license-requirements"></a>Conditions de licence requises

L’application Talkie-walkie est incluse dans toutes les licences payantes des Teams dans [Office 365 abonnements.](/office365/servicedescriptions/teams-service-description) Pour plus d’informations sur Teams' accès, consultez comment accéder [à Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

> [!NOTE]
> Certaines fonctionnalités avancées peuvent nécessiter des licences supplémentaires. Par exemple, l’intégration avec le Samsung Galaxy XCover Pro nécessite une licence Knox.

## <a name="further-information"></a>Informations complémentaires

- Les itAdmins peuvent contrôler les personnes qui utilisent talkie-walkie via les stratégies d’application.
- Si votre collègue en première ligne utilise des données mobiles pour communiquer via Teams, talkie-walkie utilisera la même méthode.
- Le Talkie-walkie doit fonctionner bien dans les situations de faible bande passante, ou dans les situations où votre smartphone est connecté et fonctionne. Le Talkie-walkie ne fonctionne pas lorsqu’il n’y a aucune connexion.

Pour plus d’informations sur l’expérience utilisateur final, voir :

- [Commencer à travailler avec Teams Talkie-walkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Communiquer avec votre équipe grâce au Talkie-walkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
