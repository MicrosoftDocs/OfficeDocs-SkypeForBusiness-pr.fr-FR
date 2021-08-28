---
title: Utiliser la fonctionnalité d’unité d’administration dans Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser les fonctionnalités d’unité d’administration dans Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 556f220c9ca250f014ae604c96cabf9ef0b0ca0f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636790"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>Fonctionnalités d’unité d’administration pour la gestion des appareils dans Teams

accédez à des rôles plus granulaires pour la gestion des appareils à l’aide du Microsoft Teams d’administration. Nous avons implémenté le concept d’Unité d’administration pour la gestion des appareils via le Teams d’administration.

Le concept d’unité d’administration vous permet de garantir l’accès à un ensemble spécifique de ressources à un administrateur dédié. L’unité d’administration limite l’accès à toutes les ressources. Vous pouvez étendre les mêmes fonctionnalités pour la gestion Teams appareils.

> [!NOTE]
> Le concept d’unité d’administration est disponible uniquement pour Teams rôle Administrateur d’appareil pour le moment.

Par exemple, Contoso a des opérations dans différentes régions. Contrôle est administrateur informatique global à Londres, tandis que Prashant est administrateur informatique pour l’Inde. Aujourd’hui, lorsque Prashant se Teams au Centre d’administration de l’appareil avec le rôle Administrateur de périphériques, il peut voir les appareils dans le monde entier. Souhaite restreindre l’accès de Prashant uniquement aux appareils présents en Inde. Le concept d’unités d’administration aide à résoudre ce problème. En savoir plus [sur le concept d’unité d’administration.](/azure/active-directory/roles/administrative-units)

![Diagramme 2010 2010 2016](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>Création d’unités d’administration

Créez des unités d’administration dans le portail Azure et affectez les administrateurs à des unités d’administration respectives. En savoir plus sur l’affectation d’unités d’administration [à l’unité de gestion des unités d’administration.](/azure/active-directory/roles/admin-units-manage)

![exemples d’unités administratives de l’entreprise](media/au-example.png)

Une fois créé, l’administrateur informatique global peut ensuite ajouter des utilisateurs d’appareils correspondant à cette unité d’administration.

![Exemple de société avec la prévisualisation des utilisateurs](media/au-example2.png)

L’affectation du rôle peut être effectuée via PowerShell à l’aide de l’cmdlet [Add-AzureADMSScopedRoleMembership.](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0)

Une fois que vous avez attribué des rôles aux utilisateurs pour les unités d’administration, les utilisateurs doivent se Teams centre d’administration pour commencer à gérer les appareils dans l’étendue.

## <a name="experience-for-administrative-unit-admin"></a>Expérience de l’administrateur d’unité d’administration

Si plusieurs unités d’administration sont affectées à des administrateurs identiques, ils peuvent basculer de l’une à l’autre sans se dé signer à partir du portail. Dans l’affichage Unités d’administration modifiées, ils ne voient que les appareils associés au nouveau service d’administration.
