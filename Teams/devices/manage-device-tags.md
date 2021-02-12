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
f1.keywords:
- CSH
description: Découvrez comment gérer et filtrer les balises sur vos appareils Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d29bc28de39c8d145914d3bddab4ed949ad0a338
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962895"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gérer les balises d’appareil Microsoft Teams

Les balises d’appareil dans Microsoft Teams vous permet de grouper, d’organiser et de gérer plus facilement les appareils que vous avez déployés dans votre organisation. Le Centre d’administration Microsoft Teams vous permet d’ajouter une ou plusieurs balises à des appareils, d’utiliser des filtres pour afficher les appareils qui correspondent à la balise que vous spécifiez, puis d’effectuer des actions sur les appareils qui y sont associés.

Vous pouvez ajouter une balise de périphérique à plusieurs types d’appareils. Toutefois, lorsque vous ouvrez un volet d’appareil dans le Centre d’administration, seuls les appareils de ce type sont renvoyés. Par exemple, vous pouvez attribuer la balise « Entreprise » à des téléphones et à des appareils de salles d’équipe. Si vous recherchez la balise « Entreprise » sur **Devices**  >  **Phones,** seuls les téléphones sont renvoyés. De même, si vous recherchez la balise « Entreprise » dans **Salles** Teams sur Appareils, seuls les appareils  >  Salles d’équipe sont renvoyés.

Pour gérer les balises d’appareil, vous devez être un administrateur global, un administrateur de service Teams ou un administrateur d’appareil Teams. Pour plus d’informations sur les rôles d’administrateur, voir [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams.](../using-admin-roles.md)

> [!IMPORTANT]
> Les balises d’appareil sont affectées au compte de ressource connecté à un appareil. Si vous signez un compte de ressource sur un appareil, puis que vous l’utilisez pour vous connectez à un autre appareil, les balises sont appliquées au nouvel appareil.

## <a name="create-remove-or-rename-device-tags"></a>Créer, supprimer ou renommer des balises d’appareil

À l’aide du panneau de gestion des balises de périphérique, vous pouvez :

- Voir toutes les balises de votre appareil.
- Créez facilement plusieurs balises d’appareil, puis attribuez-les ultérieurement à des appareils. Les balises peuvent avoir un pouvoir de 25 caractères.
- Supprimez les balises d’appareil qui ne sont plus nécessaires. Avant de pouvoir supprimer une balise d’appareil, vous devez la supprimer de tous les appareils sur qui elle a été ajoutée.
- Renommer les balises de l’appareil. Lorsque vous renommez une balise d’appareil, cette modification est reflétée sur tous les appareils sur qui elle a été ajoutée. Les balises peuvent avoir un pouvoir de 25 caractères.

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com .
2. Accédez **à Appareils,** puis sélectionnez un volet de l’appareil, tel que **Téléphones.**
3. Sélectionnez **Actions** dans le coin supérieur droit de la page, puis **Toutes les balises d’appareil.**
4. Pour créer une balise d’appareil, sélectionnez **+ Ajouter,** fournissez une valeur pour la balise de l’appareil, puis sélectionnez **l’icône Enregistrer.**
5. Pour supprimer une balise d’appareil, sélectionnez les ellipses... en côté de la balise de l’appareil que vous voulez supprimer, puis sélectionnez **Supprimer.** 
    > [!NOTE]
    > Si vous tentez de supprimer une balise d’appareil ajoutée aux appareils, vous recevez un message vous demandant si vous souhaitez le supprimer de tous les appareils. Si vous souhaitez le faire et continuer à supprimer la balise de l’appareil, sélectionnez **Supprimer la balise.**
6. Pour renommer une balise de périphérique, sélectionnez les ellipses... en côté de la balise de l’appareil que vous voulez renommer, puis sélectionnez **Modifier.**  Fournissez une nouvelle valeur pour la balise de l’appareil, puis sélectionnez **l’icône** Enregistrer.

## <a name="add-or-remove-tags-on-a-single-device"></a>Ajouter ou supprimer des balises sur un seul appareil

Lorsque vous ajoutez des balises à un appareil, vous pouvez soit sélectionner une balise existante, soit en créer une. Les balises peuvent avoir un pouvoir de 25 caractères.

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com .
2. Accédez **à Appareils,** puis sélectionnez le volet de l’appareil sur qui vous voulez ajouter ou supprimer des balises.
3. Cochez la cocher en regard de l’appareil sur qui vous voulez ajouter ou supprimer des balises, puis **sélectionnez Gérer les balises.**
4. Si vous voulez ajouter un balise :
    1. Commencez à taper le nom de balise que vous voulez ajouter.
    2. Si l’balise existe déjà, sélectionnez-la dans la liste des balises renvoyées.
    3. Si l’balise n’existe pas, **sélectionnez Ajouter \<tag name> « » en tant que nouvel balise.** Les balises peuvent avoir un pouvoir de 25 caractères.
5. Si vous voulez supprimer un balise, sélectionnez **X** en côté de l’balise que vous voulez supprimer.
6. Répétez les étapes ci-dessus si vous voulez ajouter ou supprimer d’autres balises.
7. Sélectionnez **Appliquer.**

## <a name="add-or-remove-tags-on-multiple-devices"></a>Ajouter ou supprimer des balises sur plusieurs appareils

Lorsque vous ajoutez des balises à un appareil, vous pouvez soit sélectionner une balise existante, soit en créer une. Les balises peuvent avoir un pouvoir de 25 caractères. Si vous voulez supprimer une balise de plusieurs appareils, vous devez sélectionner l’utilisateur Teams associé à l’appareil et supprimer la balise de l’utilisateur.

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com .
2. Accédez **à Appareils,** puis sélectionnez le volet de l’appareil qui contient les appareils sur qui vous voulez ajouter ou supprimer des balises.
3. Cochez les cocher en regard des appareils sur qui vous voulez ajouter ou supprimer des balises, puis sélectionnez **Gérer les balises.**
4. Si vous voulez ajouter un balise :
    1. Commencez à taper le nom de balise que vous voulez ajouter dans Gérer les **balises pour tous les appareils des utilisateurs de Teams.**
    2. Si l’balise existe déjà, sélectionnez-la dans la liste des balises renvoyées.
    3. Si l’balise n’existe pas, **sélectionnez Ajouter \<tag name> « » en tant que nouvel balise.**
5. Si vous voulez supprimer un balise :
    1. Développez **Sélectionner les utilisateurs de Teams.**
    2. Développez **\<x> les** balises sous le nom de l’utilisateur Teams dont vous souhaitez supprimer les balises.
    3. Sélectionnez **X** en côté de l’balise à supprimer.
6. Répétez les étapes ci-dessus si vous voulez ajouter ou supprimer d’autres balises.
7. Sélectionnez **Appliquer.**

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Utiliser des filtres pour renvoyer les appareils avec une balise spécifique

Si vous avez ajouté des balises d’appareil à vos appareils, vous pouvez les utiliser pour filtrer la liste des appareils afin de renvoyer uniquement les appareils sur qui une balise spécifiée a été ajoutée. Cela peut s’avérer utile si vous souhaitez simplement afficher tous les appareils d’une salle spécifique, tous les appareils d’un certain type ou tout autre critère utilisé lors de l’ajout de vos balises. Vous pouvez également effectuer des actions en bloc sur les appareils renvoyés, comme appliquer des mises à jour par vagues ou définir des stratégies de configuration différentes selon les groupes d’appareils identifiés à l’aide de balises d’appareil.

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com .
2. Accédez **à Appareils,** puis sélectionnez le volet de l’appareil qui contient les périphériques que vous voulez filtrer.
3. Sélectionnez **l’icône** Filtrer.
4. Si vous ne souhaitez spécifier qu’une seule balise, ou si vous voulez rechercher les appareils qui ont toutes les balises que vous spécifiez, sélectionnez Faire correspondre **toutes ces conditions.**
5. Si vous recherchez des appareils qui correspondent à une ou plusieurs balises d’appareil, sélectionnez Faire correspondre **l’une de ces conditions.**
6. Sélectionnez **le champ Balise,** puis spécifiez un nom de balise de périphérique dans **le champ Entrer une** valeur.
7. Si vous voulez ajouter d’autres balises d’appareil, sélectionnez Ajouter et répéter l’étape 6 pour chaque balise que vous voulez ajouter. 
8. Sélectionnez **Appliquer.**

Après avoir filtré les appareils de votre liste d’appareils, vous pouvez effectuer des actions sur ces derniers comme vous le faites normalement. Par exemple, vous pouvez les sélectionner, puis leur attribuer des configurations, modifier leurs paramètres (s’il s’il s’est s’il s’hui s’hui sur des appareils Salles Teams), et ainsi de suite. Lorsque vous avez terminé, vous pouvez supprimer le filtre  en sélectionnant le  **X** en face de l’entrée de filtre Balise ou en sélectionnant Effacer tout à droite de la liste.
