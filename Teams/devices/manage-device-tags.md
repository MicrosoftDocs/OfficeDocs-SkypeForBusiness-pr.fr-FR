---
title: Gérer et filtrer les balises d’appareil Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
description: Découvrez comment gérer et filtrer des balises sur vos appareils Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a372aacb7a8917dc169855fd671b1382d390f32
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271349"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gérer les balises d’appareil Microsoft Teams

Les balises d’appareil dans Microsoft Teams vous permettent de regrouper, d’organiser et de gérer plus facilement les appareils que vous avez déployés dans votre organisation. Avec le Centre d’administration Microsoft Teams, vous pouvez ajouter une ou plusieurs balises aux appareils, utiliser des filtres pour afficher les appareils qui correspondent à la balise que vous spécifiez, puis effectuer des actions sur les appareils qui ont cette balise.

Vous pouvez ajouter une balise d’appareil à plusieurs types d’appareil. Toutefois, lorsque vous ouvrez un volet d’appareil dans le Centre d’administration, seuls les appareils de ce type sont retournés. Par exemple, vous pouvez affecter la balise « Entreprise » à la fois aux téléphones et aux appareils salles Teams. Si vous recherchez la balise « Entreprise » dans **les téléphones** **d’appareils** >  Teams, seuls les téléphones sont renvoyés. De même, si vous recherchez la balise « Entreprise » dans **les appareils** >  Teams **salles Teams**, seuls salles Teams appareils sont retournés.

Pour gérer les balises d’appareil, vous devez être administrateur général, administrateur du service Teams ou administrateur d’appareil Teams. Pour plus d’informations sur les rôles d’administrateur, consultez [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams](../using-admin-roles.md).

> [!IMPORTANT]
> Les balises d’appareil sont affectées au compte de ressources connecté à un appareil. Si vous déconnectez un compte de ressource d’un appareil et que vous l’utilisez pour vous connecter à un autre appareil, les balises d’appareil sont appliquées au nouvel appareil.

## <a name="create-remove-or-rename-device-tags"></a>Créer, supprimer ou renommer des balises d’appareil

À l’aide du panneau de gestion des balises d’appareil, vous pouvez :

- Afficher toutes les balises de votre appareil.
- Créez facilement plusieurs balises d’appareil, puis attribuez-les aux appareils ultérieurement. Les balises peuvent avoir jusqu’à 25 caractères.
- Supprimez les balises d’appareil qui ne sont plus nécessaires. Avant de pouvoir supprimer une balise d’appareil, vous devez la supprimer de tous les appareils sur lesquels elle a été ajoutée.
- Renommez les balises d’appareil. Lorsque vous renommez une balise d’appareil, cette modification est répercutée sur tous les appareils auxquels elle a été ajoutée. Les balises peuvent avoir jusqu’à 25 caractères.

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com.
2. Accédez à **Appareils Teams** , puis choisissez n’importe quel volet d’appareil, tel que **Téléphones**.
3. Sélectionnez **Actions** dans le coin supérieur droit de la page, puis sélectionnez **Toutes les balises d’appareil**.
4. Pour créer une balise d’appareil, sélectionnez **+ Ajouter**, fournissez une valeur pour la balise d’appareil, puis **sélectionnez** l’icône Enregistrer.
5. Pour supprimer une balise d’appareil, sélectionnez les points de suspension **...** en regard de la balise d’appareil à supprimer, puis **sélectionnez Supprimer**.
    > [!NOTE]
    > Si vous essayez de supprimer une balise d’appareil qui a été ajoutée aux appareils, vous recevrez un message vous demandant si vous souhaitez la supprimer de tous les appareils. Si vous souhaitez effectuer cette opération et continuer à supprimer la balise d’appareil, sélectionnez **Annuler les appareils**.
6. Pour renommer une balise d’appareil, sélectionnez les points de suspension **...** en regard de la balise d’appareil à renommer, puis **sélectionnez Modifier**. Fournissez une nouvelle valeur pour la balise d’appareil, puis sélectionnez l’icône **Enregistrer** .

## <a name="add-or-remove-tags-on-a-single-device"></a>Ajouter ou supprimer des balises sur un seul appareil

Lorsque vous ajoutez des balises à un appareil, vous pouvez sélectionner une balise existante ou en créer une. Les balises peuvent avoir jusqu’à 25 caractères.

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com.
2. Accédez à **Appareils Teams** , puis choisissez le volet d’appareil qui contient l’appareil sur lequel vous souhaitez ajouter ou supprimer des balises.
3. Cochez une coche en regard de l’appareil sur lequel vous souhaitez ajouter ou supprimer des balises, puis sélectionnez **Gérer les balises**.
4. Si vous souhaitez ajouter une balise :
    1. Commencez à taper le nom de balise que vous souhaitez ajouter.
    2. Si la balise existe déjà, sélectionnez-la dans la liste des balises retournées.
    3. Si la balise n’existe pas, **sélectionnez Ajouter «\<tag name> » comme nouvelle balise**. Les balises peuvent avoir jusqu’à 25 caractères.
5. Si vous souhaitez supprimer une balise, sélectionnez **X** en regard de la balise à supprimer.
6. Répétez les étapes ci-dessus si vous souhaitez ajouter ou supprimer d’autres balises.
7. Sélectionnez **Appliquer**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Ajouter ou supprimer des balises sur plusieurs appareils

Lorsque vous ajoutez des balises à un appareil, vous pouvez sélectionner une balise existante ou en créer une. Les balises peuvent avoir jusqu’à 25 caractères. Si vous souhaitez supprimer une balise de plusieurs appareils, vous devez sélectionner l’utilisateur Teams associé à l’appareil et supprimer la balise de l’utilisateur.

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com.
2. Accédez à **Appareils Teams** , puis choisissez le volet d’appareil qui contient les appareils sur lesquels vous souhaitez ajouter ou supprimer des balises.
3. Cochez une coche en regard des appareils sur lesquels vous souhaitez ajouter ou supprimer des balises, puis **sélectionnez Gérer les balises**.
4. Si vous souhaitez ajouter une balise :
    1. Commencez à taper le nom de balise que vous souhaitez ajouter dans **Gérer les balises pour tous les appareils des utilisateurs teams**.
    2. Si la balise existe déjà, sélectionnez-la dans la liste des balises retournées.
    3. Si la balise n’existe pas, **sélectionnez Ajouter «\<tag name> » comme nouvelle balise**.
5. Si vous souhaitez supprimer une balise :
    1. **Développez Sélectionner les utilisateurs de Teams**.
    2. Développez **\<x> les balises** sous le nom de l’utilisateur Teams dont vous souhaitez supprimer des balises.
    3. Sélectionnez **X** en regard de la balise à supprimer.
6. Répétez les étapes ci-dessus si vous souhaitez ajouter ou supprimer d’autres balises.
7. Sélectionnez **Appliquer**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Utiliser des filtres pour retourner des appareils avec une balise spécifique

Si vous avez ajouté des balises d’appareil à vos appareils, vous pouvez les utiliser pour filtrer la liste des appareils afin de renvoyer uniquement les appareils auxquels une balise spécifiée a été ajoutée. Cela peut être utile si vous souhaitez simplement afficher tous les appareils d’une pièce spécifique, tous les appareils d’un certain type ou tout autre critère que vous avez utilisé lors de l’ajout de vos balises. Vous pouvez également effectuer des actions en bloc sur les appareils renvoyés, telles que l’application de mises à jour par vagues ou la définition de différentes stratégies de configuration en fonction des groupes d’appareils identifiés à l’aide de balises d’appareil.

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com.
2. Accédez à **Appareils Teams** , puis choisissez le volet d’appareil qui contient les appareils que vous souhaitez filtrer.
3. Sélectionnez l’icône **Filtrer** .
4. Si vous ne souhaitez spécifier qu’une seule balise, ou si vous souhaitez rechercher des appareils qui ont toutes les balises que vous spécifiez, sélectionnez **Mettre en correspondance toutes ces conditions**.
5. Si vous souhaitez rechercher des appareils qui correspondent à une ou plusieurs balises d’appareil, sélectionnez **Mettre en correspondance l’une de ces conditions**.
6. Sélectionnez le champ **Balise** , puis spécifiez un nom de balise d’appareil dans le champ **Entrée d’une valeur** .
7. Si vous souhaitez ajouter d’autres balises d’appareil, sélectionnez **Ajouter plus** et répétez l’étape 6 pour chaque balise que vous souhaitez ajouter.
8. Sélectionnez **Appliquer**.

Une fois que vous avez filtré les appareils de votre liste d’appareils, vous pouvez effectuer des actions sur ces appareils comme vous le feriez normalement. Par exemple, vous pouvez les sélectionner, puis attribuer des configurations, modifier leurs paramètres (s’ils sont salles Teams appareils), et ainsi de suite. Lorsque vous avez terminé, vous pouvez supprimer le filtre en sélectionnant le **X**  en regard **de l’entrée** de filtre de balise ou en sélectionnant **Effacer tout** sur le côté droit de la liste.
