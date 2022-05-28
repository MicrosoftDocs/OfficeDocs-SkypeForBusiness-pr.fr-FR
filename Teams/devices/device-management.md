---
title: Gérer vos périphériques dans Microsoft Teams
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Découvrez comment gérer les appareils utilisés avec Teams dans votre organisation.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 576c22d95dbbbb16105eb8e365c717ba7140cfb8
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65767240"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams : Gestion de vos appareils 

Vous pouvez gérer les appareils utilisés avec Microsoft Teams dans votre organisation à partir du centre d’administration Microsoft Teams. Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation et effectuer des tâches telles que la mise à jour, le redémarrage et la surveillance des diagnostics pour les appareils. Vous pouvez également créer et affecter des profils de configuration à un appareil ou à des groupes d’appareils.

Pour gérer les appareils, tels que la modification de la configuration des appareils, le redémarrage des appareils, la gestion des mises à jour ou l’affichage de l’intégrité des périphériques et des appareils, vous devez disposer de l’un des rôles d’administrateur Microsoft 365 suivants :

- administrateur général Microsoft 365
- administrateur de service Teams
- administrateur d’appareil Teams

Pour plus d’informations sur les rôles d’administrateur dans Teams, consultez [Utiliser Teams rôles d’administrateur pour gérer Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quels appareils pouvez-vous gérer ?

Vous pouvez gérer n’importe quel appareil certifié pour et inscrit à Teams. Un appareil est inscrit automatiquement la première fois qu’un utilisateur se connecte à Teams sur l’appareil. Pour obtenir la liste des appareils certifiés qui peuvent être gérés, consultez :

- [Salles Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Téléphones de conférence](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Téléphones de bureau](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams s’affiche](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [panneaux Teams](teams-panels.md)

Pour gérer les appareils, dans le volet de navigation gauche du centre d’administration [Microsoft Teams](https://admin.teams.microsoft.com), accédez à **Teams Appareils**, puis sélectionnez le type d’appareil. Chaque type d’appareil a sa propre section respective, qui vous permet de les gérer séparément.

## <a name="manage-teams-rooms-on-windows-devices"></a>Gérer salles Teams sur des appareils Windows

Vous pouvez utiliser le centre d’administration Teams pour afficher et gérer à distance vos salles Teams sur Windows appareils au sein de votre organisation. Le centre d’administration Teams vous permet de voir facilement, en un clin d’œil, quels appareils sont sains et qui nécessitent une attention particulière, et vous permet de vous concentrer sur des appareils spécifiques pour afficher des informations détaillées sur l’intégrité des appareils, les performances des réunions, la qualité des appels et les périphériques. 

Voici quelques actions que vous pouvez effectuer pour gérer vos appareils salles Teams. salles Teams les appareils se trouvent dans le [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com) sous **Teams Appareils** >  **salles Teams sur Windows**.

Pour plus d’informations sur la gestion de vos appareils salles Teams, consultez [Gérer Salles Microsoft Teams](../rooms/rooms-manage.md).

| Pour ce faire...                          | Procédez comme suit                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier les paramètres sur un ou plusieurs appareils | Sélectionnez un ou plusieurs appareils > **modifier les paramètres**. Si vous sélectionnez plusieurs appareils, les valeurs que vous modifiez remplacent les valeurs sur tous les appareils sélectionnés.                                                                                                                                                                                                                       |
| Redémarrer des appareils                        | Sélectionnez un ou plusieurs appareils > **redémarrer**. Lorsque vous redémarrez un appareil, vous pouvez choisir de redémarrer immédiatement l’appareil ou de sélectionner **Planifier le redémarrage** pour redémarrer l’appareil à une date et une heure spécifiques. La date et l’heure que vous sélectionnez sont locales sur l’appareil redémarré.                                                                                            |
| Afficher l’activité de réunion                  | Sélectionnez un nom d’appareil pour ouvrir les détails de l’appareil > **Activité**. Lorsque vous ouvrez l’onglet **Activité** , vous pouvez voir toutes les réunions auxquelles l’appareil a participé. Cette vue récapitulative montre l’heure de début de la réunion, le nombre de participants, sa durée et la qualité globale des appels.                                                                                        |
| Afficher les détails de la réunion                   | Sélectionnez un nom d’appareil pour ouvrir les détails de l’appareil > **activité** > sélectionnez une réunion. Lorsque vous ouvrez les détails d’une réunion, vous pouvez voir tous les participants à la réunion, la durée de leur participation à l’appel, les types de sessions Teams et la qualité de leur appel individuel. Si vous souhaitez afficher des informations techniques sur l’appel d’un participant, sélectionnez l’heure de début de l’appel du participant. |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>Gérer les téléphones, les salles Teams sur Android, les écrans Teams et les panneaux Teams 

Dans le centre d’administration Teams, vous pouvez afficher et gérer des téléphones, des salles Teams sur Android, des écrans Teams et des panneaux Teams inscrits dans Teams de votre organisation. Les informations que vous verrez pour chaque appareil incluent le nom de l’appareil, le fabricant, le modèle, l’utilisateur, l’état, l’action, la dernière vue et l’historique. Vous pouvez personnaliser la vue pour afficher les informations qui correspondent à vos besoins.

Les téléphones, les salles Teams sur Android, les écrans Teams et les panneaux Teams sont inscrits automatiquement dans Microsoft Intune si vous y êtes inscrit. Une fois qu’un appareil est inscrit, la conformité de l’appareil est confirmée et des stratégies d’accès conditionnel sont appliquées à l’appareil.

Voici quelques exemples de gestion des téléphones, des salles Teams sur Android, des écrans Teams et des panneaux Teams dans votre organisation.  

| Pour ce faire...                           | Procédez comme suit                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier les informations de l’appareil               | Sélectionnez un appareil > **Modifier**. Vous pouvez modifier des détails tels que le nom de l’appareil, la balise de ressource et ajouter des notes.                                                                                                                                                                                                              |
| Gérer les mises à jour logicielles                 | Sélectionnez un appareil > **Mettre à jour**. Vous pouvez afficher la liste des mises à jour logicielles et microprogrammes disponibles pour l’appareil et choisir les mises à jour à installer. Pour plus d’informations sur la mise à jour des appareils, consultez [Mettre à jour Teams des appareils à distance](remote-update.md)                                                          |
| Mettre à niveau des téléphones Teams vers des écrans Teams  | Dans la page **Téléphones IP**, sélectionnez un ou plusieurs téléphones Teams > **Mettre à niveau**. Cette option est disponible uniquement pour les téléphones qui prennent en charge la mise à niveau vers Teams affiche. Pour plus d’informations, consultez [Mettre à niveau Teams téléphones vers Teams affiche](upgrade-phones-to-displays.md).                                                      |
| Affecter ou modifier des stratégies de configuration | Sélectionnez un ou plusieurs appareils > **Affecter la configuration**.                                                                                                                                                                                                                                                       |
| Ajouter ou supprimer des balises d’appareil               | Sélectionnez un ou plusieurs appareils > **Gérer les balises**. Pour plus d’informations sur les balises d’appareil, consultez [Gérer Teams balises d’appareil](manage-device-tags.md).                                                                                                                                                                 |
| Redémarrer des appareils                         | Sélectionnez un ou plusieurs appareils > **redémarrer**.                                                                                                                                                                                                                                                                    |
| Filtrer les appareils à l’aide de balises d’appareil        | Sélectionnez l’icône de filtre, sélectionnez le champ **Balise** , spécifiez une balise d’appareil sur laquelle **filtrer, puis sélectionnez Appliquer**. Pour plus d’informations sur le filtrage des appareils à l’aide de balises d’appareil, consultez [Utiliser des filtres pour retourner des appareils avec une balise spécifique](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Afficher l’historique et les diagnostics des appareils     | Sous la colonne **Historique** , cliquez sur le lien **Afficher** pour un appareil afin d’afficher son historique des mises à jour et ses détails de diagnostic.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Utiliser des profils de configuration dans Teams

Utilisez des profils de configuration pour gérer les paramètres et les fonctionnalités des différents appareils Teams de votre organisation, notamment les salles Teams sur Android, les écrans Teams, Teams téléphone et les panneaux Teams. Vous pouvez créer ou charger des profils de configuration pour inclure des paramètres et des fonctionnalités que vous souhaitez activer ou désactiver, puis attribuer un profil à un appareil ou à un ensemble d’appareils. 

#### <a name="create-a-configuration-profile"></a>Créer un profil de configuration

Pour créer un profil de configuration pour un type d’appareil Teams :

1. Dans le volet de navigation de gauche, accédez à **Teams Appareils** > sélectionnez le type d’appareil Teams > **profils de configuration**. Par exemple, sélectionnez **Teams Appareils** >  **Teams panneaux Profils** > **de configuration** pour créer un profil de configuration pour Teams panneaux.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour le profil et ajoutez éventuellement une description conviviale.
4. Spécifiez les paramètres souhaités pour le profil, puis cliquez sur **Enregistrer**.
   Le profil de configuration nouvellement créé s’affiche dans la liste des profils.

#### <a name="assign-a-configuration-profile"></a>Affecter un profil de configuration
Après avoir créé un profil de configuration pour un type d’appareil Teams, affectez-le à un ou plusieurs appareils.

1. Dans le volet de navigation gauche, accédez à **Teams Appareils** > sélectionnez le type d’appareil Teams. Par exemple, pour affecter un profil de configuration à un appareil de panneaux Teams, sélectionnez **Teams Appareils** >  **Teams panneaux**.
2. Sélectionnez un ou plusieurs appareils, puis cliquez sur **Affecter la configuration**.  
3. Dans le volet **Affecter une configuration** , recherchez le profil de configuration à affecter aux appareils sélectionnés.
4. Cliquez sur **Appliquer**.
   Pour les appareils auxquels vous avez appliqué la stratégie de configuration, la colonne **Action** affiche **La mise à jour de configuration** et la colonne **Profil de** configuration affiche le nom du profil de configuration.
