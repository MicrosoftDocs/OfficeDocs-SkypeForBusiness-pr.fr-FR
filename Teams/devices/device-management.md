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

Vous pouvez gérer les appareils utilisés avec Microsoft Teams dans votre organisation à partir du Centre d’administration Microsoft Teams. Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation et effectuer des tâches telles que la mise à jour, le redémarrage et le suivi des diagnostics pour les appareils. Vous pouvez également créer et attribuer des profils de configuration à un appareil ou à des groupes d’appareils.

Pour gérer les appareils, par exemple, modifier la configuration des appareils, redémarrer des appareils, gérer les mises à jour ou afficher l’état des périphériques et périphériques, vous devez avoir l’un des rôles d’administrateur Microsoft 365 suivants :

- Administrateur global de Microsoft 365
- Administrateur du service Teams
- Administrateur d’appareils Teams

Pour plus d’informations sur les rôles d’administrateur dans Teams, voir [Utiliser les rôles d’administrateur Teams pour gérer Teams.](../using-admin-roles.md)

## <a name="what-devices-can-you-manage"></a>Quels appareils pouvez-vous gérer ?

Vous pouvez gérer n’importe quel appareil certifié pour Teams et inscrit. Un appareil est automatiquement inscrit la première fois qu’un utilisateur se connecté à Teams sur l’appareil. Pour obtenir la liste des périphériques certifiés qui peuvent être gérés, voir :

- [Salles Microsoft Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [Téléphones de conférence](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [Téléphones de bureau](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams s’affiche](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Barres de collaboration](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

Pour gérer les appareils, dans le panneau de navigation gauche du Centre d’administration [Microsoft Teams,](https://admin.teams.microsoft.com)sélectionnez **Appareils,** puis sélectionnez le type d’appareil. Chaque type d’appareil possède sa propre section, ce qui vous permet de les gérer séparément.

## <a name="manage-teams-rooms-devices"></a>Gérer les appareils Des salles d’équipe

Vous pouvez utiliser le Centre d’administration Teams pour afficher et gérer à distance vos appareils Salles d’équipe dans votre organisation. Le Centre d’administration Teams permet de voir en un clin d’œil quels appareils sont en bonne santé et qui ont besoin d’être attentifs, et vous permet de vous concentrer sur des appareils spécifiques pour voir des informations détaillées sur l’état des appareils, les performances des réunions, la qualité des appels et les périphériques. 

Voici quelques opérations que vous pouvez prendre pour gérer vos appareils Salles d’équipe. Les appareils Salles Teams sont disponibles dans le Centre [d’administration Microsoft Teams](https://admin.teams.microsoft.com) sous **Salles d’équipe**  >  **appareils.**

Pour plus d’informations sur la gestion de vos appareils Salles d’équipe, voir [Gérer les salles Microsoft Teams.](../rooms/rooms-manage.md)

| Pour... | Procédez comme suit…|
|---------------|--------|
| Modifier les paramètres sur un ou plusieurs appareils | Sélectionnez un ou plusieurs appareils > **modifier les paramètres.** Si vous sélectionnez plusieurs appareils, les valeurs que vous modifiez remplaceront elles sur tous les appareils sélectionnés. |
| Redémarrer des appareils | Sélectionnez un ou plusieurs appareils > **redémarrer.** Lorsque vous redémarrez un appareil, vous pouvez choisir  de le redémarrer immédiatement ou de sélectionner Planifier le redémarrage pour redémarrer l’appareil à une date et une heure spécifiques. La date et l’heure que vous sélectionnez sont locales pour l’appareil en cours de redémarrage.|
| Afficher l’activité d’une réunion | Sélectionnez un nom d’appareil pour ouvrir les détails de l’appareil > **activité.** Lorsque vous ouvrez **l’onglet** Activité, vous pouvez voir toutes les réunions à qui l’appareil a participé. Cette vue récapitulatif indique l’heure de début de la réunion, le nombre de participants, sa durée et la qualité globale des appels.|
| Afficher les détails de la réunion |  Sélectionnez un nom d’appareil pour ouvrir les détails de l’appareil > **les >** une réunion. Lorsque vous ouvrez les détails d’une réunion, vous pouvez voir tous les participants à la réunion, leur durée d’appel, les types de session Teams et leur qualité individuelle. Si vous souhaitez voir des informations techniques sur l’appel d’un participant, sélectionnez l’heure de début de l’appel du participant.|

## <a name="manage-phones-collaboration-bars-and-teams-displays"></a>Gérer les téléphones, les barres de collaboration et les affichages de Teams 

Dans le Centre d’administration Teams, vous pouvez afficher et gérer les téléphones, les barres de collaboration et les affichages Teams inscrits dans Teams dans votre organisation. Les informations que vous verrez pour chaque appareil incluent le nom de l’appareil, le fabricant, le modèle, l’utilisateur, le statut, l’action, la dernière vue et l’historique. Vous pouvez personnaliser l’affichage pour afficher les informations qui sont adaptées à vos besoins.

Les téléphones, les barres de collaboration et les affichages Teams sont automatiquement inscrits à Microsoft Intune si vous vous y êtes inscrit. Une fois un appareil inscrit, la conformité des appareils est confirmée et les stratégies d’accès conditionnel sont appliquées à l’appareil.

Voici quelques exemples de la façon dont vous pouvez gérer les téléphones, les barres de collaboration et les affichages Teams dans votre organisation.  

|Pour...  |Procédez comme suit… |
|---------|---------|
| Modifier les informations sur l’appareil               | Sélectionnez un périphérique > **Modifier.** Vous pouvez modifier des détails tels que le nom de l’appareil, une balise d’actif et ajouter des notes.     |
| Gérer les mises à jour logicielles                 | Sélectionnez un appareil sur > **Mise à jour.** Vous pouvez afficher la liste des mises à jour logicielles et microprogrammes disponibles pour l’appareil et choisir les mises à jour à installer. Pour plus d’informations sur la mise à jour des appareils, voir [Mettre à jour les appareils Teams à distance](remote-update.md)   |
| Mise à niveau des téléphones Teams vers l’affichage Teams                | Sur la page **Téléphones IP,** sélectionnez un ou plusieurs téléphones Teams > **Mettre à niveau.** Cette option est disponible uniquement pour les téléphones qui supportent la mise à niveau vers l’affichage Teams. Pour en savoir plus, consultez [La mise à niveau des téléphones Teams vers l’affichage Teams.](upgrade-phones-to-displays.md)   |
| Affecter ou modifier des stratégies de configuration | Sélectionnez un ou plusieurs appareils > **la configuration.**                                                                                                                                                                                                                   |
| Ajouter ou supprimer des balises d’appareil               | Sélectionnez un ou plusieurs appareils sur > **gérer les balises.** Pour plus d’informations sur les balises d’appareil, [voir Gérer les balises d’appareil Teams.](manage-device-tags.md)                                                                                                      |
| Redémarrer des appareils                         | Sélectionnez un ou plusieurs appareils > **redémarrer.**                                                                                                                                                                                                                                |
| Filtrer des appareils à l’aide de balises d’appareil        | Sélectionnez l’icône de filtre, **sélectionnez le champ Balise,** spécifiez une balise d’appareil sur qui filtrer, puis **sélectionnez Appliquer.** Pour plus d’informations sur le filtrage des appareils à l’aide de balises d’appareil, voir Utiliser des filtres pour renvoyer des appareils [avec une balise spécifique.](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)|
| Afficher l’historique des appareils                     | Sélectionnez un appareil pour **>'historique.** Vous pouvez afficher l’historique des mises à jour de l’appareil.                                                                                                                                                                                |
| Afficher les diagnostics                        | Sélectionnez un appareil pour > **diagnostics.**                                                                                                                                                                                                                            |
### <a name="use-configuration-profiles-in-teams"></a>Utiliser des profils de configuration dans Teams

Utilisez les profils de configuration pour gérer les paramètres et fonctionnalités des téléphones Teams et des barres de collaboration dans votre organisation. Vous pouvez créer ou télécharger des profils de configuration pour inclure les paramètres et fonctionnalités que vous voulez activer ou désactiver, puis affecter un profil à un appareil ou à des groupes d’appareils. 

#### <a name="create-a-configuration-profile"></a>Créer un profil de configuration

1. Dans la barre de navigation de gauche, allez aux **profils**  >  **de configuration d’appareils.**
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour le profil et, si vous le souhaitez, ajoutez une description conviviale.
4. Spécifiez les paramètres de votre profil, puis cliquez sur **Enregistrer.**

#### <a name="assign-a-configuration-profile"></a>Attribuer un profil de configuration

1. Dans la barre de navigation de gauche, allez aux **profils**  >  **de configuration d’appareils.**
2. Sélectionnez **le profil de** configuration à attribuer, puis cliquez sur Affecter à **l’appareil.**  
3. Dans le volet Attribuer des appareils à un profil de **configuration,** recherchez et sélectionnez les appareils que vous souhaitez affecter.
4. Cliquez sur **Enregistrer**.

