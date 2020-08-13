---
title: Gérer et filtrer les balises de périphérique de Microsoft teams
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
description: Découvrez comment gérer et filtrer des balises sur vos appareils Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f428a40e5a9adf4a53d4b2e12064b90b4ceebe43
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46657096"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gérer les balises de périphérique de Microsoft teams

> [!NOTE]
> La possibilité d’ajouter des balises à des appareils est mise à la disposition des clients de Microsoft teams en vagues. Si vous ne voyez pas l’option de gestion des balises dans le centre d’administration Teams, les balises d’appareil n’ont pas encore été activées sur votre client. Revenez à l’étape précédente.

Dans Microsoft Teams, les balises d’appareil vous permettent de regrouper, d’organiser et de gérer plus facilement les appareils que vous avez déployés au sein de votre organisation. Le centre d’administration Microsoft teams vous permet d’ajouter un ou plusieurs indicateurs aux appareils, d’utiliser des filtres pour afficher les appareils qui correspondent à la balise que vous spécifiez, puis d’effectuer des actions sur les appareils qui ont cette balise.

Vous pouvez ajouter une balise d’appareil à plusieurs types d’appareils. Toutefois, lorsque vous ouvrez un volet d’appareil dans le centre d’administration, seuls les appareils de ce type sont renvoyés. Par exemple, vous pouvez affecter la balise « entreprise » aux appareils de bureau et aux salles d’équipes. Si vous recherchez la balise « société » alors que **Devices**vous utilisez des  >  **téléphones**mobiles, seuls les téléphones sont renvoyés. De même, si vous recherchez la balise « entreprise » dans **périphériques**  >  **équipes**, seuls les appareils de salle teams sont renvoyés.

Pour gérer les balises d’appareil, vous devez être un administrateur général ou un administrateur de service Teams.

> [!IMPORTANT]
> Les balises d’appareil sont affectées au compte de ressources qui est connecté à un appareil. Si vous signez un compte de ressource sur un appareil et que vous l’utilisez pour vous connecter à un autre appareil, les balises d’appareil s’appliquent à un nouvel appareil.

## <a name="create-remove-or-rename-device-tags"></a>Créer, supprimer ou renommer des balises de périphériques

À l’aide du volet de gestion des indicateurs de périphériques, vous pouvez :

- Affichez toutes les balises de votre appareil.
- Créez facilement plusieurs balises d’appareil, puis affectez-les à des appareils ultérieurement. Les indicateurs peuvent comporter jusqu’à 25 caractères.
- Supprimer les balises de périphériques qui ne sont plus nécessaires. Avant de pouvoir supprimer une balise d’appareil, vous devez la supprimer de tous les appareils auxquels elle a été ajoutée.
- Renommer des balises de périphériques. Lorsque vous renommez une balise de périphérique, cette modification est répercutée sur tous les appareils auxquels elle a été ajoutée. Les indicateurs peuvent comporter jusqu’à 25 caractères.

1. Connectez-vous au centre d’administration Microsoft teams en visitanthttps://admin.teams.microsoft.com
2. Accédez à **périphériques** , puis sélectionnez n’importe quel volet de périphériques, comme **téléphone**
3. Sélectionner des **actions** dans le coin supérieur droit de la page, puis sélectionner **toutes les balises d’appareil**
4. Pour créer une balise de périphérique, sélectionnez **+ Ajouter**, indiquez une valeur pour la balise de périphérique, puis sélectionnez l’icône **Enregistrer** .
5. Pour supprimer une balise de périphérique, sélectionnez les points de suspension **...** en regard de la balise d’appareil que vous voulez supprimer, puis sélectionnez **supprimer** .
    > [!NOTE]
    > Si vous tentez de supprimer une balise de périphérique qui a été ajoutée à des appareils, vous recevez un message vous demandant si vous voulez le supprimer de tous les appareils. Pour cela, puis continuez à supprimer la balise de périphérique, sélectionnez **enlever les appareils**.
6. Pour renommer une balise de périphérique, sélectionnez les points de suspension **...** en regard de la balise d’appareil que vous voulez renommer, puis sélectionnez **modifier**. Entrez une nouvelle valeur pour la balise Device et sélectionnez l’icône **Save (enregistrer** ).

## <a name="add-or-remove-tags-on-a-single-device"></a>Ajouter ou supprimer des balises sur un seul appareil

Lorsque vous ajoutez des indicateurs à un appareil, vous pouvez sélectionner une balise existante ou en créer une nouvelle. Les indicateurs peuvent comporter jusqu’à 25 caractères.

1. Connectez-vous au centre d’administration Microsoft teams en visitanthttps://admin.teams.microsoft.com
2. Accédez à **périphériques** , puis sélectionnez le volet de périphériques contenant l’appareil sur lequel vous voulez ajouter ou supprimer des indicateurs.
3. Activez/désactivez la case à cocher en regard de l’appareil sur lequel vous voulez ajouter ou supprimer des indicateurs, puis sélectionnez **gérer les indicateurs** .
4. Si vous souhaitez ajouter un indicateur :
    1. Commencez à taper le nom de l’indicateur que vous voulez ajouter.
    2. Si la balise existe déjà, sélectionnez-la dans la liste des balises qui sont renvoyées.
    3. Si la balise n’existe pas, sélectionnez **ajouter «» \<tag name> en tant que nouvelle balise**. Les indicateurs peuvent comporter jusqu’à 25 caractères.
5. Si vous voulez supprimer une balise, sélectionnez **X** en regard de la balise que vous voulez supprimer.
6. Répétez les étapes ci-dessus si vous souhaitez ajouter ou supprimer d’autres indicateurs.
7. Sélectionnez **appliquer** .

## <a name="add-or-remove-tags-on-multiple-devices"></a>Ajouter ou supprimer des balises sur plusieurs appareils

Lorsque vous ajoutez des indicateurs à un appareil, vous pouvez sélectionner une balise existante ou en créer une nouvelle. Les indicateurs peuvent comporter jusqu’à 25 caractères. Si vous souhaitez supprimer une balise de plusieurs appareils, vous devez sélectionner l’utilisateur teams qui est associé à l’appareil et supprimer le mot-clé de l’utilisateur.

1. Connectez-vous au centre d’administration Microsoft teams en visitanthttps://admin.teams.microsoft.com
2. Accédez à **périphériques** , puis sélectionnez le volet de périphériques contenant les appareils auxquels vous voulez ajouter ou supprimer des indicateurs.
3. Activez/désactivez les cases à cocher en regard des appareils pour lesquels vous voulez ajouter ou supprimer des indicateurs, puis sélectionnez **gérer les indicateurs** .
4. Si vous souhaitez ajouter un indicateur :
    1. Commencez à taper le nom de l’indicateur que vous voulez ajouter dans **gérer les indicateurs pour tous les appareils des utilisateurs de teams** .
    2. Si la balise existe déjà, sélectionnez-la dans la liste des balises qui sont renvoyées.
    3. Si la balise n’existe pas, sélectionnez **ajouter « \<tag name> » en tant que nouvelle balise**
5. Si vous souhaitez supprimer une balise :
    1. Développez utilisateurs de la **sélection de équipes**
    2. Développez ** \<x> balises** sous le nom de l’utilisateur teams dont vous voulez supprimer les balises.
    3. Sélectionnez **X** en regard de la balise que vous voulez supprimer.
6. Répétez les étapes ci-dessus si vous souhaitez ajouter ou supprimer d’autres indicateurs.
7. Sélectionnez **appliquer** .

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Utiliser des filtres pour renvoyer des appareils avec une balise spécifique

Si vous avez ajouté des balises d’appareil à vos appareils, vous pouvez les utiliser pour filtrer la liste des appareils de manière à ce qu’elle renvoie uniquement les appareils pour lesquels une balise spécifiée a été ajoutée. Cela peut être utile si vous souhaitez simplement afficher tous les appareils d’une pièce spécifique, tous les appareils d’un type particulier ou tout autre critère que vous avez utilisé lors de l’ajout de vos indicateurs. Vous pouvez également effectuer des actions en bloc sur les appareils renvoyés, par exemple en appliquant des mises à jour dans des ondulations ou en définissant des stratégies de configuration différentes selon les groupes d’appareils identifiés à l’aide de balises de périphériques.

1. Connectez-vous au centre d’administration Microsoft teams en visitanthttps://admin.teams.microsoft.com
2. Accédez à **périphériques** , puis sélectionnez le volet de périphériques contenant les appareils que vous voulez filtrer.
3. Sélectionner l’icône de **filtre**
4. Si vous ne souhaitez spécifier qu’un seul indicateur, ou si vous souhaitez rechercher les appareils dont vous spécifiez toutes les balises, sélectionnez l’option **respecter toutes les conditions**.
5. Si vous voulez rechercher des appareils correspondant à une ou plusieurs balises de périphériques, sélectionnez **l’une des conditions suivantes** .
6. Sélectionnez le champ **balise** , puis spécifiez un nom de balise d’appareil dans le champ **entrer une valeur** .
7. Si vous souhaitez ajouter d’autres balises d’appareil, sélectionnez **ajouter plus** et répétez l’étape 6 pour chaque balise que vous voulez ajouter.
8. Sélectionnez **appliquer** .

Une fois que vous avez filtré les appareils dans la liste de votre appareil, vous pouvez effectuer des actions comme vous le feriez habituellement. Par exemple, vous pouvez les sélectionner, puis affecter des configurations, modifier leurs paramètres (s’il s’agit d’un appareil d’équipe), et ainsi de suite. Lorsque vous avez terminé, vous pouvez supprimer le filtre en sélectionnant le **X** en regard de l’entrée de filtre **balise** ou en sélectionnant **Effacer tout** sur le côté droit de la liste.
