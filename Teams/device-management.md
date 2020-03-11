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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Découvrez comment gérer les appareils utilisés avec les équipes de votre organisation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587276"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gérer vos périphériques dans Microsoft Teams

En tant qu’administrateur, vous pouvez gérer les appareils utilisés avec les équipes de votre organisation à partir du centre d’administration Microsoft Teams. Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation, et effectuer des tâches telles que la mise à jour, le redémarrage et l’analyse des diagnostics pour les appareils. Vous pouvez également créer des profils de configuration et les affecter à un appareil ou à un groupe d’appareils. 

## <a name="what-devices-can-you-manage"></a>Quels appareils pouvez-vous gérer ?
Vous pouvez gérer tous les appareils qui sont certifiés pour et inscrits dans Teams. Un appareil est automatiquement inscrit la première fois qu’un utilisateur se connecte à teams sur l’appareil. Pour obtenir la liste des appareils certifiés qui peuvent être gérés, voir :

- [Conférences téléphoniques](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [Téléphones de bureau](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- Barres de collaboration

Les appareils sont gérés dans le [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com) sous **appareils** dans le volet de navigation de gauche.

> [!NOTE]
> Si vous avez Microsoft Intune, les appareils sont automatiquement inscrits dans Intune. Après l’inscription d’un appareil, la conformité de l’appareil est confirmée et les stratégies d’accès conditionnel sont appliquées à l’appareil.

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>Gérer les téléphones et les barres de collaboration dans teams

Même si le centre d’administration Microsoft teams est géré en tant que téléphones et barres de collaboration, ils disposent de leurs propres sections dans le volet de navigation de gauche, sous **périphériques**. Cela vous permet de gérer chaque type d’appareil séparément.

À partir de cet emplacement, vous pouvez afficher et gérer les téléphones et les barres de collaboration inscrits dans teams au sein de votre organisation. Les informations qui s’affichent pour chaque appareil incluent le nom de l’appareil, le fabricant, le modèle, l’utilisateur, le statut, l’action, le dernier affichage et l’historique. Vous pouvez personnaliser l’affichage pour afficher les informations qui correspondent à vos besoins.

Voici quelques exemples de la manière dont vous pouvez gérer les appareils teams au sein de votre organisation.  
    
|Pour cela, procédez comme suit...  |Procédez comme suit |
|---------|---------|
|Modification des informations de périphérique   | Sélectionnez un appareil > **modifier**. Vous pouvez modifier les détails tels que le nom de l’appareil, l’étiquette de la ressource et ajouter des notes.     |
|Gérer les mises à jour logicielles   |Sélectionnez un appareil > **mettre à jour**. Vous pouvez afficher la liste des mises à jour de logiciels et de microprogrammes disponibles pour l’appareil, puis sélectionner les mises à jour pour procéder à l’installation.    |
|Redémarrer un appareil   |Sélectionnez un appareil > **redémarrer**.          |
|Afficher l’historique de l’appareil  | Sélectionnez un appareil > **historique**. Vous pouvez afficher l’historique des mises à jour de l’appareil.     |
|Afficher les Diagnostics  | Sélectionnez un appareil > **Diagnostics**.        |

## <a name="use-configuration-profiles-in-teams"></a>Utiliser des profils de configuration dans teams

Utilisez les profils de configuration pour gérer les paramètres et les fonctionnalités des appareils teams de votre organisation. Vous pouvez créer ou charger des profils de configuration pour inclure des paramètres et des fonctionnalités que vous souhaitez activer ou désactiver, puis attribuer un profil à un appareil ou à un groupe d’appareils. 

### <a name="create-a-configuration-profile"></a>Créer un profil de configuration

1. Dans le volet de navigation de gauche, accédez à**profils de configuration**de **périphériques** > .
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour le profil et, si vous le souhaitez, ajoutez une description conviviale.
4. Spécifiez les paramètres que vous voulez utiliser pour le profil, puis cliquez sur **Enregistrer**.

### <a name="assign-a-configuration-profile"></a>Attribuer un profil de configuration

1. Dans le volet de navigation de gauche, accédez à**profils de configuration**de **périphériques** > .
2. Sélectionnez le **profil de configuration** que vous voulez attribuer, puis cliquez sur **affecter au périphérique**.  
3. Dans le volet **affecter des appareils à un profil de configuration** , recherchez et sélectionnez les périphériques que vous voulez affecter.
4. Cliquez sur **Enregistrer**.
