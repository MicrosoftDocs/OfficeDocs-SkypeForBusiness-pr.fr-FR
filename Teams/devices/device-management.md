---
title: Gérer les appareils dans Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- m365initiative-deployteams
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Gérer les appareils utilisés avec Microsoft Teams dans votre organisation.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: b34d554c0930efa622e60a695203e5fa35bd48ab
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245709"
---
# <a name="manage-devices-in-teams"></a>Gérer les appareils dans Teams 

Vous pouvez gérer les appareils utilisés avec Microsoft Teams dans votre organisation à partir du centre d’administration Microsoft Teams. Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation et effectuer des tâches telles que la mise à jour, le redémarrage et la surveillance des diagnostics pour les appareils. Vous pouvez également créer et attribuer des profils de configuration à un appareil ou à des groupes d’appareils.

Pour gérer les appareils, par exemple modifier la configuration de l’appareil, redémarrer des appareils, gérer les mises à jour ou afficher l’intégrité des appareils et des périphériques, vous devez disposer de l’un des rôles d’administrateur Microsoft 365 suivants :

- Microsoft 365 Administrateur général
- Administrateur de service Teams
- Administrateur d’appareil Teams

Pour plus d’informations sur les rôles d’administrateur dans Teams, consultez [Utiliser des rôles d’administrateur Teams pour gérer Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quels appareils pouvez-vous gérer ?

Vous pouvez gérer n’importe quel appareil certifié et inscrit dans Teams. Un appareil est automatiquement inscrit la première fois qu’un utilisateur se connecte à Teams sur l’appareil. Pour obtenir la liste des appareils certifiés qui peuvent être gérés, consultez :

- [Salles Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Téléphones de conférence](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Téléphones de bureau](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Affichages Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Panneaux Teams](teams-panels.md)

Pour gérer les appareils, dans le volet de navigation gauche du [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com), accédez à **Appareils Teams**, puis sélectionnez le type d’appareil. Chaque type d’appareil a sa propre section respective, qui vous permet de les gérer séparément.

## <a name="manage-teams-rooms-on-windows-devices"></a>Gérer les salles Teams sur les appareils Windows

Vous pouvez utiliser le Centre d’administration Teams pour afficher et gérer à distance vos salles Teams sur les appareils Windows au sein de votre organisation. Le centre d’administration Teams permet de voir facilement, en un coup d’œil, quels appareils sont sains et qui nécessitent une attention particulière, et vous permet de vous concentrer sur des appareils spécifiques pour afficher des informations détaillées sur l’intégrité des appareils, les performances des réunions, la qualité des appels et les périphériques. 

Voici quelques actions que vous pouvez effectuer pour gérer vos appareils salles Teams. salles Teams appareils se trouvent dans le [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com) sous **Appareils** >  Teams **salles Teams sur Windows**.

Pour plus d’informations sur la gestion de vos appareils salles Teams, consultez [Gérer les Salles Microsoft Teams](../rooms/rooms-manage.md).

| Pour ce faire...                          | Procédez comme suit                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier les paramètres sur un ou plusieurs appareils | Sélectionnez un ou plusieurs appareils > **Modifier les paramètres**. Si vous sélectionnez plusieurs appareils, les valeurs que vous modifiez remplacent les valeurs de tous les appareils sélectionnés.                                                                                                                                                                                                                       |
| Redémarrer des appareils                        | Sélectionnez un ou plusieurs appareils > **Redémarrer**. Lorsque vous redémarrez un appareil, vous pouvez choisir de redémarrer l’appareil immédiatement ou de sélectionner **Planifier le redémarrage** pour redémarrer l’appareil à une date et une heure spécifiques. La date et l’heure que vous sélectionnez sont locales pour l’appareil en cours de redémarrage.                                                                                            |
| Afficher l’activité de réunion                  | Sélectionnez un nom d’appareil pour ouvrir les détails de l’appareil > **Activité**. Lorsque vous ouvrez l’onglet **Activité** , vous pouvez voir toutes les réunions auxquelles l’appareil a participé. Cette vue récapitulative affiche l’heure de début de la réunion, le nombre de participants, sa durée et la qualité globale de l’appel.                                                                                        |
| Afficher les détails de la réunion                   | Sélectionnez un nom d’appareil pour ouvrir les détails de l’appareil > **Activité** > sélectionner une réunion. Lorsque vous ouvrez les détails d’une réunion, vous pouvez voir tous les participants à la réunion, la durée de l’appel, les types de session Teams et la qualité de leur appel individuel. Si vous souhaitez afficher des informations techniques sur l’appel d’un participant, sélectionnez l’heure de début de l’appel du participant. |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>Gérer les téléphones, les salles Teams sur Android, les écrans Teams et les panneaux Teams 

Dans le Centre d’administration Teams, vous pouvez afficher et gérer les téléphones, les salles Teams sur Android, les affichages Teams et les panneaux Teams inscrits dans Teams dans votre organisation. Les informations que vous verrez pour chaque appareil incluent le nom de l’appareil, le fabricant, le modèle, l’utilisateur, l’état, l’action, la dernière vue et l’historique. Vous pouvez personnaliser l’affichage pour afficher les informations qui répondent à vos besoins.

Les téléphones, les salles Teams sur Android, les écrans Teams et les panneaux Teams sont automatiquement inscrits dans Microsoft Intune si vous vous y êtes inscrit. Une fois qu’un appareil est inscrit, la conformité de l’appareil est confirmée et des stratégies d’accès conditionnel sont appliquées à l’appareil.

Voici quelques exemples de la façon dont vous pouvez gérer les téléphones, les salles Teams sur Android, les affichages Teams et les panneaux Teams dans votre organisation.  

| Pour ce faire...                           | Procédez comme suit                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier les informations de l’appareil               | Sélectionnez un appareil > **Modifier**. Vous pouvez modifier des détails tels que le nom de l’appareil, la balise de ressource et ajouter des notes.                                                                                                                                                                                                              |
| Gérer les mises à jour logicielles                 | Sélectionnez un appareil > **Mise à jour**. Vous pouvez afficher la liste des mises à jour de logiciels et de microprogrammes disponibles pour l’appareil et choisir les mises à jour à installer. Pour plus d’informations sur la mise à jour des appareils, consultez [Mettre à jour des appareils Teams à distance](remote-update.md)                                                          |
| Mettre à niveau les téléphones Teams vers les affichages Teams  | Dans la page **Téléphones IP** , sélectionnez un ou plusieurs téléphones Teams > **Mettre à niveau**. Cette option est disponible uniquement pour les téléphones qui prennent en charge la mise à niveau vers les écrans Teams. Pour plus d’informations, consultez [Mettre à niveau des téléphones Teams vers les écrans Teams](upgrade-phones-to-displays.md).                                                      |
| Affecter ou modifier des stratégies de configuration | Sélectionnez un ou plusieurs appareils > **Attribuer une configuration**.                                                                                                                                                                                                                                                       |
| Ajouter ou supprimer des étiquettes d’appareil               | Sélectionnez un ou plusieurs appareils > **Gérer les étiquettes**. Pour plus d’informations sur les étiquettes d’appareil, consultez [Gérer les étiquettes d’appareil Teams](manage-device-tags.md).                                                                                                                                                                 |
| Redémarrer des appareils                         | Sélectionnez un ou plusieurs appareils > **Redémarrer**.                                                                                                                                                                                                                                                                    |
| Filtrer les appareils à l’aide d’étiquettes d’appareil        | Sélectionnez l’icône de filtre, sélectionnez le champ **Balise** , spécifiez une balise d’appareil sur laquelle filtrer, puis sélectionnez **Appliquer**. Pour plus d’informations sur le filtrage des appareils à l’aide de balises d’appareil, consultez [Utiliser des filtres pour retourner des appareils avec une balise spécifique](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Afficher l’historique et les diagnostics des appareils     | Sous la colonne **Historique** , cliquez sur le lien **Afficher** d’un appareil pour afficher son historique des mises à jour et les détails de diagnostic.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Utiliser des profils de configuration dans Teams

Utilisez des profils de configuration pour gérer les paramètres et les fonctionnalités des différents appareils Teams de votre organisation, notamment les salles Teams sur Android, les affichages Teams, les téléphones Teams et les panneaux Teams. Vous pouvez créer ou charger des profils de configuration pour inclure des paramètres et des fonctionnalités que vous souhaitez activer ou désactiver, puis attribuer un profil à un appareil ou à un ensemble d’appareils. 

#### <a name="create-a-configuration-profile"></a>Créer un profil de configuration

Pour créer un profil de configuration pour un type d’appareil Teams :

1. Dans le volet de navigation de gauche, accédez à **Appareils Teams** > sélectionnez le type d’appareil Teams > **Profils de configuration**. Par exemple, sélectionnez Les **panneaux** >  **Teams Appareils** >  Teams **Profils de configuration** pour créer un profil de configuration pour les panneaux Teams.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour le profil et ajoutez éventuellement une description conviviale.
4. Spécifiez les paramètres souhaités pour le profil, puis cliquez sur **Enregistrer**.
   Le profil de configuration nouvellement créé s’affiche dans la liste des profils.

#### <a name="assign-a-configuration-profile"></a>Attribuer un profil de configuration
Après avoir créé un profil de configuration pour un type d’appareil Teams, affectez-le à un ou plusieurs appareils.

1. Dans le volet de navigation de gauche, accédez à **Appareils Teams** > sélectionnez le type d’appareil Teams. Par exemple, pour affecter un profil de configuration à un appareil de panneaux Teams, sélectionnez **Teams Appareils** > **Teams panneaux Teams**.
2. Sélectionnez un ou plusieurs appareils, puis cliquez sur **Attribuer une configuration**.  
3. Dans le volet **Affecter une configuration** , recherchez le profil de configuration à attribuer aux appareils sélectionnés.
4. Cliquez sur **Appliquer**.
   Pour les appareils auxquels vous avez appliqué la stratégie de configuration, la colonne **Action** affiche **La mise à jour** de la configuration et la colonne **Profil de** configuration affiche le nom du profil de configuration.
