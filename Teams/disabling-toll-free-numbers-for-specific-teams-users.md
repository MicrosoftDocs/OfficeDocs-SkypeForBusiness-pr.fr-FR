---
title: Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez comment contrôler la façon dont les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions de pont d’audioconférence.
ms.openlocfilehash: 18696143930c42649304bb62b5693e95179397e4
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055434"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques

Si votre organisation dispose de numéros gratuits dans son pont de conférence audio Microsoft, vous pouvez autoriser ou empêcher leur utilisation pendant les réunions d’organisateurs spécifiques.  

Par défaut, tous les utilisateurs de votre organisation sont activés pour utiliser des numéros gratuits, ce qui signifie que ces numéros, s’ils sont disponibles, peuvent être utilisés par les participants pour rejoindre leurs réunions. Si ce n’est pas le comportement souhaité pour certains utilisateurs de votre organisation, vous pouvez restreindre l’utilisation de ces numéros par des utilisateurs spécifiques dans leurs réunions via un contrôle d' enablement de numéro gratuit.

Lorsque les numéros gratuits sont désactivés pour un organisateur donné :

- Un numéro gratuit ne sera plus inclus dans ses invitations aux réunions.
- Les numéros gratuits ne seront plus répertoriés dans la page « Rechercher un numéro local » référencé dans ses invitations aux réunions.
- Les participants ne pourront pas participer à la réunion de l’organisateur donné s’ils composent un numéro gratuit de l’organisation.
- Toutes les réunions de l’organisateur sont automatiquement reprogrammées et le numéro gratuit leur est supprimé.  

    > [!IMPORTANT]
    > Cela renvoye toutes les invitations par courrier électronique de l’organisateur à tous les participants de ces réunions.

- Les participants peuvent continuer à rejoindre les réunions de l’organisateur à l’aide de numéros de téléphone.

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactiver les numéros gratuits pour des utilisateurs spécifiques

À partir du **Microsoft Teams d’administration :**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. A côté de **Conférence Audio**, cliquez sur **Modifier**.

3. Set **Include toll-free numbers in meeting requests from this user** to **Off.**

4. Cliquez sur **Enregistrer.**

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-powershell"></a>Utiliser PowerShell

Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)
