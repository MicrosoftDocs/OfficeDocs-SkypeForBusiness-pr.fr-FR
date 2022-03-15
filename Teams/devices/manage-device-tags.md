---
title: Gérer et filtrer Microsoft Teams balises d’appareil
author: cazawideh
ms.author: czawideh
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
description: Découvrez comment gérer et filtrer les balises sur Microsoft Teams appareils mobiles.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 94ae03328121d4a54124de2446455b1c95d11854
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503931"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gérer Microsoft Teams balises d’appareil

Les balises d’Microsoft Teams vous permet de grouper, d’organiser et de gérer plus facilement les appareils que vous avez déployés dans votre organisation. Le Centre d’administration Microsoft Teams vous permet d’ajouter une ou plusieurs balises aux appareils, d’utiliser des filtres pour afficher les appareils qui correspondent à la balise que vous spécifiez, puis d’effectuer des actions sur les appareils qui en sont associés.

Vous pouvez ajouter une balise de périphérique à plusieurs types d’appareils. Toutefois, lorsque vous ouvrez un volet d’appareil dans le Centre d’administration, seuls les appareils de ce type sont renvoyés. Par exemple, vous pouvez attribuer la balise « Entreprise » à des téléphones et salles Teams appareils mobiles. Si vous recherchez la balise « Entreprise » sur Teams **DevicesPhone** > , **seuls** les téléphones sont renvoyés. De même, si vous recherchez  >  la balise « Entreprise » dans Teams appareils mobiles **salles Teams**, seuls salles Teams appareils sont renvoyés.

Pour gérer les balises d’appareil, vous devez être administrateur global, administrateur Teams service ou administrateur de Teams périphérique. Pour plus d’informations sur les rôles d’administrateur, voir [Utiliser Microsoft Teams rôles d’administrateur pour gérer Teams](../using-admin-roles.md).

> [!IMPORTANT]
> Les balises d’appareil sont affectées au compte de ressource connecté à un appareil. Si vous signez un compte de ressource sur un appareil et que vous l’utilisez pour vous connectez à un autre appareil, les balises sont appliquées au nouvel appareil.

## <a name="create-remove-or-rename-device-tags"></a>Créer, supprimer ou renommer des balises d’appareil

À l’aide du panneau de gestion des balises de périphérique, vous pouvez :

- Voir toutes les balises de votre appareil.
- Créez facilement plusieurs balises d’appareil, puis attribuez-les ultérieurement à des appareils. Les balises peuvent avoir un pouvoir de 25 caractères.
- Supprimez les balises d’appareil qui ne sont plus nécessaires. Avant de pouvoir supprimer une balise d’appareil, vous devez la supprimer de tous les appareils sur qui elle a été ajoutée.
- Renommer les balises de l’appareil. Lorsque vous renommez une balise d’appareil, cette modification est reflétée sur tous les appareils sur qui elle a été ajoutée. Les balises peuvent avoir un pouvoir de 25 caractères.

1. Connectez-vous Microsoft Teams centre d’administration en vous rendant sur le sitehttps://admin.teams.microsoft.com.
2. Accédez **à Teams appareils mobiles**, puis sélectionnez un volet d’appareil, tel que **Téléphones**.
3. **Sélectionnez Actions** dans le coin supérieur droit de la page, puis **Toutes les balises d’appareil**.
4. Pour créer une balise d’appareil, sélectionnez **+ Ajouter**, fournissez une valeur pour la balise de l’appareil, puis sélectionnez **l’icône Enregistrer** .
5. Pour supprimer une balise d’appareil, sélectionnez les ellipses **...** en côté de la balise de l’appareil que vous voulez supprimer, puis sélectionnez **Supprimer**.
    > [!NOTE]
    > Si vous tentez de supprimer une balise d’appareil ajoutée aux appareils, vous recevez un message vous demandant si vous souhaitez le supprimer de tous les appareils. Si vous souhaitez le faire et continuer à supprimer la balise de l’appareil, sélectionnez **Supprimer la balise**.
6. Pour renommer une balise de périphérique, sélectionnez les ellipses **...** en côté de la balise de l’appareil que vous voulez renommer, puis sélectionnez **Modifier**. Fournissez une nouvelle valeur pour la balise de l’appareil, puis sélectionnez **l’icône** Enregistrer.

## <a name="add-or-remove-tags-on-a-single-device"></a>Ajouter ou supprimer des balises sur un seul appareil

Lorsque vous ajoutez des balises à un appareil, vous pouvez soit sélectionner une balise existante, soit en créer une. Les balises peuvent avoir un pouvoir de 25 caractères.

1. Connectez-vous Microsoft Teams centre d’administration en vous rendant sur le sitehttps://admin.teams.microsoft.com.
2. Accédez **à Teams périphériques**, puis sélectionnez le volet de l’appareil sur qui vous voulez ajouter ou supprimer des balises.
3. Cochez la position en regard de l’appareil sur qui vous voulez ajouter ou supprimer des balises, puis **sélectionnez Gérer les balises**.
4. Si vous voulez ajouter un balise :
    1. Commencez à taper le nom de la balise que vous voulez ajouter.
    2. Si l’balise existe déjà, sélectionnez-la dans la liste des balises renvoyées.
    3. Si l’balise n’existe pas, **sélectionnez Ajouter «\<tag name> » en tant que nouvel balise**. Les balises peuvent avoir un pouvoir de 25 caractères.
5. Si vous voulez supprimer un balise, sélectionnez **X** en côté de l’balise que vous voulez supprimer.
6. Répétez les étapes ci-dessus si vous voulez ajouter ou supprimer d’autres balises.
7. **Sélectionnez Appliquer**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Ajouter ou supprimer des balises sur plusieurs appareils

Lorsque vous ajoutez des balises à un appareil, vous pouvez soit sélectionner une balise existante, soit en créer une. Les balises peuvent avoir un pouvoir de 25 caractères. Si vous voulez supprimer une balise de plusieurs appareils, vous devez sélectionner l’utilisateur Teams associé à l’appareil et supprimer la balise de l’utilisateur.

1. Connectez-vous Microsoft Teams centre d’administration en vous rendant sur le sitehttps://admin.teams.microsoft.com.
2. Accédez **à Teams périphériques**, puis sélectionnez le volet des appareils qui contient les appareils sur qui vous voulez ajouter ou supprimer des balises.
3. Cochez les cocher en regard des appareils sur qui vous voulez ajouter ou supprimer des balises, puis sélectionnez **Gérer les balises**.
4. Si vous voulez ajouter un balise :
    1. Commencez à taper le nom de balise que vous voulez ajouter dans **Gérer les balises pour tous les appareils Teams utilisateurs**.
    2. Si l’balise existe déjà, sélectionnez-la dans la liste des balises renvoyées.
    3. Si l’balise n’existe pas, **sélectionnez Ajouter «\<tag name> » en tant que nouvel balise**.
5. Si vous voulez supprimer un balise :
    1. **Développez Sélectionner Teams utilisateurs**.
    2. Développez **\<x> les** balises sous le nom Teams’utilisateur dont vous voulez supprimer les balises.
    3. **Sélectionnez X** en côté de l’balise à supprimer.
6. Répétez les étapes ci-dessus si vous voulez ajouter ou supprimer d’autres balises.
7. **Sélectionnez Appliquer**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Utiliser des filtres pour renvoyer les appareils avec une balise spécifique

Si vous avez ajouté des balises d’appareil à vos appareils, vous pouvez les utiliser pour filtrer la liste des appareils afin de renvoyer uniquement les appareils sur qui une balise spécifiée a été ajoutée. Cela peut s’avérer utile si vous souhaitez simplement afficher tous les appareils d’une salle spécifique, tous les appareils d’un certain type ou tout autre critère utilisé lors de l’ajout de vos balises. Vous pouvez également effectuer des actions en bloc sur les appareils renvoyés, comme appliquer des mises à jour par vagues ou définir des stratégies de configuration différentes selon les groupes d’appareils identifiés à l’aide de balises d’appareil.

1. Connectez-vous Microsoft Teams centre d’administration en vous rendant sur le sitehttps://admin.teams.microsoft.com.
2. Accédez **à Teams périphériques**, puis sélectionnez le volet de l’appareil qui contient les périphériques que vous voulez filtrer.
3. Sélectionnez **l’icône** Filtrer.
4. Si vous ne voulez spécifier qu’une seule balise, ou si vous voulez rechercher les appareils qui ont toutes les balises que vous spécifiez, sélectionnez Faire correspondre **toutes ces conditions**.
5. Si vous recherchez des appareils qui correspondent à une ou plusieurs balises d’appareil, sélectionnez **L’une de ces conditions**.
6. Sélectionnez **le champ** Balise, puis spécifiez un nom de balise d’appareil dans **le champ Entrer une** valeur.
7. Si vous voulez ajouter d’autres balises d’appareil, sélectionnez Ajouter d’autres balises et répétez l’étape 6 pour chaque balise à ajouter.
8. **Sélectionnez Appliquer**.

Après avoir filtré les appareils de votre liste d’appareils, vous pouvez effectuer des actions sur ces derniers comme vous le faites normalement. Par exemple, vous pouvez les sélectionner, puis leur attribuer des configurations, modifier leurs paramètres (s’ils ne sont salles Teams),et ainsi de suite. Lorsque vous avez terminé, vous pouvez supprimer le filtre en sélectionnant le **X** en face de l’entrée de filtre Balise ou en  sélectionnant Effacer tout à droite de la liste.
