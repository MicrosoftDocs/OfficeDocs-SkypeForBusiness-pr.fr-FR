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
description: Découvrez comment gérer les appareils utilisés avec les équipes de votre organisation.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6996b0980ae7305a7517a71645ba823a588e2f8
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49033004"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gérer vos périphériques dans Microsoft Teams

Vous pouvez gérer les appareils utilisés avec Microsoft teams dans votre organisation à partir du centre d’administration Microsoft Teams. Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation, et effectuer des tâches telles que la mise à jour, le redémarrage et l’analyse des diagnostics pour les appareils. Vous pouvez également créer des profils de configuration et les affecter à un appareil ou à un groupe d’appareils.

Pour gérer les appareils, par exemple pour modifier la configuration de l’appareil, redémarrez les appareils, gérez les mises à jour, ou les périphériques d’affichage et les périphériques, vous devez disposer d’un des rôles d’administrateur Microsoft 365 suivants :

- Administrateur général Microsoft 365
- Administrateur de service teams
- Administrateur d’appareil teams

Pour plus d’informations sur les rôles d’administrateur dans Teams, voir [utiliser des rôles d’administrateur d’équipes pour gérer teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quels appareils pouvez-vous gérer ?

Vous pouvez gérer tous les appareils qui sont certifiés pour et inscrits dans Teams. Un appareil est automatiquement inscrit la première fois qu’un utilisateur se connecte à teams sur l’appareil. Pour obtenir la liste des appareils certifiés qui peuvent être gérés, voir :

- [Salles Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Conférences téléphoniques](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Téléphones de bureau](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams s’affiche](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Barres de collaboration](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Pour gérer les appareils, dans le volet de navigation de gauche du [Centre d’administration de Microsoft teams](https://admin.teams.microsoft.com), accédez à **périphériques** , puis sélectionnez le type d’appareil. Chaque type d’appareil dispose de sa propre section respective qui vous permet de les gérer séparément.

## <a name="manage-teams-rooms-devices"></a>Gérer les appareils de salle d’équipe

Vous pouvez utiliser le centre d’administration teams pour afficher et gérer à distance les appareils de salle de votre organisation au sein de votre organisation. Le centre d’administration teams vous permet de consulter en un clin d’œil les appareils sains et qui nécessitent d’être attentifs, et vous permet de vous concentrer sur des appareils spécifiques pour afficher des informations détaillées sur l’état de l’appareil, les performances des réunions, la qualité des appels et les périphériques. 

Voici quelques opérations que vous pouvez effectuer pour gérer les appareils de salle de votre équipe. Pour plus d’informations, reportez-vous au [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com) dans la section **périphériques** de l’équipe  >  **Teams Rooms**.

Pour plus d’informations sur la gestion de vos appareils de salle d’équipe, voir [gérer les salles de Microsoft teams](../rooms/rooms-manage.md).

| Pour cela, procédez comme suit... | Procédez comme suit…|
|---------------|--------|
| Changer les paramètres d’un ou de plusieurs appareils | Sélectionnez un ou plusieurs appareils > **modifier les paramètres**. Si vous sélectionnez plusieurs appareils, les valeurs que vous modifiez remplaceront celles de tous les appareils sélectionnés. |
| Redémarrer les périphériques | Sélectionnez un ou plusieurs appareils > **redémarrer**. Lorsque vous redémarrez un appareil, vous pouvez choisir si vous voulez redémarrer l’appareil immédiatement ou sélectionner **planifier le redémarrage** pour redémarrer l’appareil à une date et une heure spécifiques. La date et l’heure que vous sélectionnez sont locales par le périphérique redémarré.|
| Afficher l’activité d’une réunion | Sélectionnez un nom d’appareil pour ouvrir détails de l’appareil > **activité**. Lorsque vous ouvrez l’onglet **activité** , vous pouvez voir toutes les réunions auxquelles l’appareil a participé. Cette vue récapitulative montre l’heure de début de la réunion, le nombre de participants, sa durée et la qualité d’appel globale.|
| Afficher les détails de la réunion |  Sélectionnez un nom d’appareil pour ouvrir détails de l’appareil > **activité** > sélectionnez une réunion. Lorsque vous ouvrez les informations d’une réunion, vous pouvez voir tous les participants à la réunion, la durée de l’appel, les types de session équipes et la qualité d’appel individuelle. Si vous souhaitez consulter des informations techniques sur l’appel d’un participant, sélectionnez l’heure de début de l’appel du participant.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Gestion des téléphones, des barres de collaboration et des équipes 

Le centre d’administration teams vous permet d’afficher et de gérer les téléphones, les barres de collaboration et les équipes dans les équipes de votre organisation. Les informations qui s’affichent pour chaque appareil incluent le nom de l’appareil, le fabricant, le modèle, l’utilisateur, le statut, l’action, le dernier affichage et l’historique. Vous pouvez personnaliser l’affichage pour afficher les informations qui correspondent à vos besoins.

Les numéros de téléphone, de barre de collaboration et d’équipe s’inscrivent automatiquement dans Microsoft Intune si vous vous êtes inscrit. Après l’inscription d’un appareil, la conformité de l’appareil est confirmée et les stratégies d’accès conditionnel sont appliquées à l’appareil.

Voici quelques exemples de la manière dont vous pouvez gérer les téléphones, les barres de collaboration et les équipes au sein de votre organisation.  

|Pour cela, procédez comme suit...  |Procédez comme suit… |
|---------|---------|
| Modification des informations de périphérique               | Sélectionnez un appareil > **modifier**. Vous pouvez modifier les détails tels que le nom de l’appareil, l’étiquette de la ressource et ajouter des notes.     |
| Gérer les mises à jour logicielles                 | Sélectionnez un appareil > **mettre à jour**. Vous pouvez afficher la liste des mises à jour de logiciels et de microprogrammes disponibles pour l’appareil, puis sélectionner les mises à jour pour procéder à l’installation. Pour plus d’informations sur la mise à jour des appareils, voir [mettre à jour les appareils teams](remote-update.md)   |
| Mise à niveau des téléphones teams vers teams                | Sur la page **téléphones IP** , sélectionnez un ou plusieurs téléphones teams > **mise à niveau**. Cette option n’est disponible que sur les téléphones prenant en charge la mise à niveau vers Teams. Pour plus d’informations, voir [mettre à niveau des téléphones teams vers teams](upgrade-phones-to-displays.md).   |
| Affecter ou modifier des stratégies de configuration | Sélectionnez un ou plusieurs appareils > **affecter la configuration**.                                                                                                                                                                                                                   |
| Ajouter ou supprimer des balises de périphériques               | Sélectionnez un ou plusieurs périphériques > **gérer les balises**. Pour plus d’informations sur les balises d’appareil, voir [gérer les balises d’appareil teams](manage-device-tags.md).                                                                                                      |
| Redémarrer les périphériques                         | Sélectionnez un ou plusieurs appareils > **redémarrer**.                                                                                                                                                                                                                                |
| Filtrer les périphériques à l’aide de balises de périphériques        | Sélectionnez l’icône de filtre, sélectionnez le champ **balise** , spécifiez une balise d’appareil sur **laquelle** filtrer, puis sélectionnez appliquer. Pour plus d’informations sur le filtrage des appareils à l’aide de balises d’appareil, voir [utiliser des filtres pour renvoyer des appareils avec une balise spécifique](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag).|
| Afficher l’historique de l’appareil                     | Sélectionnez un appareil > **historique**. Vous pouvez afficher l’historique des mises à jour de l’appareil.                                                                                                                                                                                |
| Afficher les Diagnostics                        | Sélectionnez un appareil > **Diagnostics**.                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Utiliser des profils de configuration dans teams

Utilisez les profils de configuration pour gérer les paramètres et les fonctionnalités des téléphones et des barres de collaboration de votre organisation. Vous pouvez créer ou charger des profils de configuration pour inclure des paramètres et des fonctionnalités que vous souhaitez activer ou désactiver, puis attribuer un profil à un appareil ou à un groupe d’appareils. 

#### <a name="create-a-configuration-profile"></a>Créer un profil de configuration

1. Dans le volet de navigation de gauche, accédez à profils de configuration de **périphériques**  >  **Configuration profiles**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour le profil et, si vous le souhaitez, ajoutez une description conviviale.
4. Spécifiez les paramètres que vous voulez utiliser pour le profil, puis cliquez sur **Enregistrer**.

#### <a name="assign-a-configuration-profile"></a>Attribuer un profil de configuration

1. Dans le volet de navigation de gauche, accédez à profils de configuration de **périphériques**  >  **Configuration profiles**.
2. Sélectionnez le **profil de configuration** que vous voulez attribuer, puis cliquez sur **affecter au périphérique**.  
3. Dans le volet **affecter des appareils à un profil de configuration** , recherchez et sélectionnez les périphériques que vous voulez affecter.
4. Cliquez sur **Enregistrer**.

