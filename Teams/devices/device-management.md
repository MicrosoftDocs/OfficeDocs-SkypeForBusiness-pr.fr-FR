---
title: Gérer vos périphériques dans Microsoft Teams
author: cazawideh
ms.author: czawideh
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
description: Découvrez comment gérer les appareils utilisés avec des Teams dans votre organisation.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69432c2a5fa3657a179e254e4bcdd047dc4c2f66
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63511202"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams : gestion de vos appareils 

Vous pouvez gérer les appareils utilisés avec des Microsoft Teams dans votre organisation à partir du Microsoft Teams d’administration. Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation et effectuer des tâches telles que la mise à jour, le redémarrage et le suivi des diagnostics pour les appareils. Vous pouvez également créer et attribuer des profils de configuration à un appareil ou à des groupes d’appareils.

Pour gérer les appareils, par exemple, modifier la configuration des appareils, redémarrer des appareils, gérer les mises à jour ou afficher l’état des périphériques et périphériques, vous devez avoir l’un des rôles d’administrateur de systèmes Microsoft 365 suivants :

- Microsoft 365 administrateur global
- Teams de services
- Teams administrateur d’appareils

Pour plus d’informations sur les rôles d’Teams administrateur, voir Utiliser Teams rôles d’administrateur [pour gérer Teams](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>Quels appareils pouvez-vous gérer ?

Vous pouvez gérer n’importe quel appareil certifié et inscrit, Teams. Un appareil est automatiquement inscrit la première fois qu’un utilisateur se Teams sur l’appareil. Pour obtenir la liste des périphériques certifiés qui peuvent être gérés, voir :

- [Barres de collaboration](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Téléphones de conférence](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Téléphones de bureau](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Salles Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Teams affiche](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams panneaux](teams-panels.md)

Pour gérer les appareils, dans le panneau de navigation gauche du [Microsoft Teams](https://admin.teams.microsoft.com) d’administration, sélectionnez Teams **appareils, puis** sélectionnez le type d’appareil. Chaque type d’appareil possède sa propre section, ce qui vous permet de les gérer séparément.

## <a name="manage-teams-rooms-devices"></a>Gérer salles Teams appareils

Vous pouvez utiliser le centre Teams d’administration pour afficher et gérer à distance vos appareils salles Teams votre organisation. Le Centre d’administration Teams permet de voir en un clin d’œil quels appareils sont en bonne santé et qui ont besoin d’être attentifs, et vous permet de vous concentrer sur des appareils spécifiques pour voir des informations détaillées sur l’état des appareils, les performances des réunions, la qualité des appels et les périphériques. 

Voici certaines choses que vous pouvez faire pour gérer vos salles Teams appareils mobiles. salles Teams appareils mobiles se trouvent dans le Centre [d’administration Microsoft Teams sous](https://admin.teams.microsoft.com) **Teams appareils salles Teams** > .

Pour plus d’informations sur la gestion de salles Teams appareils mobiles, voir [Gérer Salles Microsoft Teams](../rooms/rooms-manage.md).

| Pour...                          | Pour ce faire,                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier les paramètres sur un ou plusieurs appareils | Sélectionnez un ou plusieurs appareils > **modifier les paramètres**. Si vous sélectionnez plusieurs appareils, les valeurs que vous modifiez remplaceront elles sur tous les appareils sélectionnés.                                                                                                                                                                                                                       |
| Redémarrer des appareils                        | Sélectionnez un ou plusieurs appareils > **redémarrer**. Lorsque vous redémarrez un appareil, vous pouvez choisir de le redémarrer immédiatement ou  de sélectionner Planifier le redémarrage pour redémarrer l’appareil à une date et une heure spécifiques. La date et l’heure que vous sélectionnez sont locales pour l’appareil en cours de redémarrage.                                                                                            |
| Afficher l’activité d’une réunion                  | Sélectionnez un nom d’appareil pour ouvrir les détails de l’appareil > **activité**. Lorsque vous ouvrez **l’onglet** Activité, vous pouvez voir toutes les réunions à qui l’appareil a participé. Cette vue récapitulatif indique l’heure de début de la réunion, le nombre de participants, sa durée et la qualité globale des appels.                                                                                        |
| Afficher les détails de la réunion                   | Sélectionnez un nom d’appareil pour ouvrir les détails de l’appareil > **les >** une réunion. Lorsque vous ouvrez les détails d’une réunion, vous pouvez voir tous les participants à la réunion, leur durée d’appel, les types de session Teams et leur qualité individuelle. Si vous souhaitez voir des informations techniques sur l’appel d’un participant, sélectionnez l’heure de début de l’appel du participant. |

## <a name="manage-phones-collaboration-bars-teams-displays-and-teams-panels"></a>Gérer les téléphones, les barres de collaboration, Teams’affichage et les Teams panneaux 

Dans le Teams d’administration, vous pouvez afficher et gérer des téléphones, des barres de collaboration, des écrans Teams et des panneaux Teams inscrits dans Teams votre organisation. Les informations que vous verrez pour chaque appareil incluent le nom de l’appareil, le fabricant, le modèle, l’utilisateur, le statut, l’action, la dernière vue et l’historique. Vous pouvez personnaliser l’affichage pour afficher les informations qui sont adaptées à vos besoins.

Les téléphones, les barres de collaboration, Teams’affichages et les panneaux Teams sont automatiquement inscrits à Microsoft Intune si vous vous êtes inscrit pour ce programme. Une fois un appareil inscrit, la conformité des appareils est confirmée et les stratégies d’accès conditionnel sont appliquées à l’appareil.

Voici quelques exemples de la façon dont vous pouvez gérer les téléphones, les barres de collaboration, Teams des affichages et Teams panneaux dans votre organisation.  

| Pour...                           | Pour ce faire,                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modifier les informations sur l’appareil               | Sélectionnez un périphérique > **Modifier**. Vous pouvez modifier des détails tels que le nom de l’appareil, une balise d’actif et ajouter des notes.                                                                                                                                                                                                              |
| Gérer les mises à jour logicielles                 | Sélectionnez un appareil sur > **Mise à jour**. Vous pouvez afficher la liste des mises à jour logicielles et microprogrammes disponibles pour l’appareil et choisir les mises à jour à installer. Pour plus d’informations sur la mise à jour des appareils, voir [Mettre à Teams à distance](remote-update.md)                                                          |
| Mettre à niveau Teams téléphones portables vers Teams’affichage  | Sur la page **Téléphones IP**, sélectionnez un ou plusieurs Teams pour > **mise à niveau**. Cette option est disponible uniquement pour les téléphones qui supportent la mise à niveau vers Teams’affichages. Pour en savoir plus, voir [Mettre à Teams niveau vers Teams’affichage.](upgrade-phones-to-displays.md)                                                      |
| Affecter ou modifier des stratégies de configuration | Sélectionnez un ou plusieurs appareils > **la configuration Attribuer**.                                                                                                                                                                                                                                                       |
| Ajouter ou supprimer des balises d’appareil               | Sélectionnez un ou plusieurs appareils > **les balises**. Pour plus d’informations sur les balises d’appareil, voir [Gérer Teams balises d’appareil](manage-device-tags.md).                                                                                                                                                                 |
| Redémarrer des appareils                         | Sélectionnez un ou plusieurs appareils > **redémarrer**.                                                                                                                                                                                                                                                                    |
| Filtrer des appareils à l’aide de balises d’appareil        | Sélectionnez l’icône de filtre, **sélectionnez le champ Balise** , spécifiez une balise d’appareil sur qui filtrer, puis **sélectionnez Appliquer**. Pour plus d’informations sur le filtrage des appareils à l’aide de balises d’appareil, voir Utiliser des filtres pour renvoyer des appareils [avec une balise spécifique](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| Afficher l’historique et les diagnostics de l’appareil     | Sous la **colonne Historique** , cliquez sur le lien **Afficher** d’un appareil pour afficher son historique des mises à jour et ses détails de diagnostic.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Utiliser des profils de configuration dans Teams

Utilisez les profils de configuration pour gérer les paramètres et fonctionnalités de différents appareils Teams dans votre organisation, notamment les barres de collaboration, les affichages Teams, les téléphones Teams et les panneaux Teams. Vous pouvez créer ou télécharger des profils de configuration pour inclure les paramètres et fonctionnalités que vous voulez activer ou désactiver, puis attribuer un profil à un appareil ou un ensemble d’appareils. 

#### <a name="create-a-configuration-profile"></a>Créer un profil de configuration

Pour créer un profil de configuration pour un type Teams appareil :

1. Dans la barre de navigation de gauche, sélectionnez Teams **et > le** type Teams d’appareil > **profils de configuration**. Par exemple, sélectionnez **Teams panneaux** >  **Teams** >  **des** profils de configuration pour créer un profil de configuration Teams panneaux.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour le profil et éventuellement ajoutez une description conviviale.
4. Spécifiez les paramètres de votre profil, puis cliquez sur **Enregistrer**.
   Le profil de configuration nouvellement créé s’affiche dans la liste des profils.

#### <a name="assign-a-configuration-profile"></a>Attribuer un profil de configuration
Après avoir créé un profil de configuration pour Teams type d’appareil, affectez-le à un ou plusieurs appareils.

1. Dans la barre de navigation gauche, **sélectionnez Teams et** > le type Teams’appareil sélectionné. Par exemple, pour attribuer un profil de configuration à un Teams panneaux, sélectionnez Teams **panneaux** >  Teams **panneaux**.
2. Sélectionnez un ou plusieurs appareils, puis cliquez sur **Affecter la configuration**.  
3. Dans le **volet Attribuer un périphérique de configuration** , recherchez le profil de configuration à affecter aux appareils sélectionnés.
4. Cliquez sur **Appliquer**.
   Pour les appareils sur lesquels vous avez appliqué la stratégie de configuration, la colonne  **Action** affiche la mise à jour de configuration et la colonne Profil de **configuration** affiche le nom du profil de configuration.
