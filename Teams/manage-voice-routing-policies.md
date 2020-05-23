---
title: Gérer les stratégies de routage de messagerie vocale dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment créer et gérer des stratégies de routage de messagerie vocale dans Microsoft Teams.
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350188"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Gérer les stratégies de routage de messagerie vocale dans Microsoft teams

Si vous avez déployé le [routage direct du système téléphonique](direct-routing-landing-page.md) au sein de votre organisation, vous utilisez les stratégies de routage vocal pour permettre aux équipes et aux utilisateurs de Skype entreprise Online de recevoir et de passer des appels téléphoniques à l’aide du réseau téléphonique public commuté (RTC) à l’aide de votre infrastructure de téléphonie locale.

Une stratégie de routage vocale est un conteneur d’enregistrements d’utilisation RTC. Pour créer et gérer des stratégies de routage de messagerie vocale, vous pouvez **accéder à**  >  **stratégies de routage vocal** dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell.

Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées. Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer.

Il est important de savoir que l’affectation d’une stratégie de routage vocale à un utilisateur ne permet pas à un utilisateur de passer des appels RTC dans Teams. Vous devez également activer l’utilisateur pour le routage direct du système téléphonique et effectuer d’autres étapes de configuration. Pour en savoir plus, voir [configurer le routage direct](direct-routing-configure.md).

## <a name="create-a-custom-voice-routing-policy"></a>Créer une stratégie de routage vocale personnalisée

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**stratégies de routage de voix vocales, puis  >  **Voice routing policies**cliquez sur **Ajouter**.<br>
    ![Capture d’écran de la page Ajouter une stratégie de routage vocale dans le centre d’administration Microsoft teams](media/manage-voice-routing-policies.png) 
2. Entrez un nom pour votre stratégie, ainsi qu’une description.
3. Sous **rapports d’utilisation RTC**, cliquez sur **Ajouter une utilisation PSTN**, puis sélectionnez les enregistrements que vous souhaitez ajouter. Si vous avez besoin de créer un nouvel enregistrement d’utilisation RTC, cliquez sur **Ajouter**.
4. Si vous avez ajouté plusieurs enregistrements d’utilisation RTC, réorganisez-les dans l’ordre de votre choix.
5. Lorsque vous avez terminé, cliquez sur **appliquer**.
6. Cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-voice-routing-policy"></a>Modification d’une stratégie de routage téléphonique

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de routage vocal**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. Cliquez sur **Ajouter/supprimer des enregistrements d’utilisation RTC**, apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Assigner une stratégie de routage vocale personnalisée aux utilisateurs

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

Pour attribuer une stratégie à un utilisateur :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.
3. Sous **stratégie de routage**de la voix, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.

Pour attribuer une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur l' &#x2713; (coche) en haut du tableau.
3. Cliquez sur **modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **appliquer**.  

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  **stratégies de routage vocal**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Configurer le routage de la voix pour le routage direct](direct-routing-voice-routing.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
