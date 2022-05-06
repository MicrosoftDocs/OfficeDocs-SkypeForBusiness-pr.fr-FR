---
title: Gérer les modèles d’équipe dans le Centre d’administration
author: serdars
ms.author: serdars
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment gérer les modèles d’équipe dans le Centre d’administration
ms.openlocfilehash: c753a92205844ebade9a713a8442837039232339
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "65248936"
---
# <a name="manage-team-templates-in-the-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration

Gérez les modèles d’équipe que vos utilisateurs finaux voient en créant des stratégies de modèles dans le Centre d’administration. Dans chaque stratégie de modèles, vous pouvez désigner les modèles affichés ou masqués.
Affectez des utilisateurs différents à différentes stratégies de modèles afin que vos utilisateurs n’affichent que le sous-ensemble de modèles d’équipe spécifié.

Regardez cette courte vidéo pour découvrir comment gérer les stratégies de modèles.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-templates-policies-and-assign-available-templates"></a>Créer des stratégies de modèles et affecter des modèles disponibles

1. Se connecter au Centre d’administration de Microsoft Teams.

2. Accédez à **Teams** >  **Templates** stratégies.

3. Sélectionnez **Ajouter**.

    ![Les stratégies de modèles sont sélectionnées et l’option Ajouter est mise en surbrillance.](media/template-policies-1.png)

1. Donnez un nom à la stratégie et ajoutez une brève description.

2. Dans la liste **des modèles visibles** , sélectionnez les modèles à masquer, puis **sélectionnez Masquer**.

    ![Modèles sélectionnés avec masquage mis en surbrillance.](media/template-policies-2.png)

    Vous pouvez voir les modèles que vous avez choisis de masquer dans la liste **des modèles masqués** .

1. Pour afficher certains modèles, accédez à la liste **des modèles masqués** .

2. Sélectionnez les modèles à afficher, puis sélectionnez **Afficher**.

   ![Modèles sélectionnés qui ne sont pas masqués.](media/template-policies-3.png)

   Les modèles sélectionnés s’affichent dans la liste **des modèles visibles** .
3. Cliquez sur **Enregistrer**.

   Votre nouvelle stratégie de modèles s’affiche dans la liste **des stratégies de modèles** .

## <a name="assign-templates-policies-to-users"></a>Affecter des stratégies de modèles aux utilisateurs

Vous pouvez affecter une stratégie de modèles directement aux utilisateurs, individuellement ou à l’échelle par le biais d’une affectation par lots. Gardez à l’esprit qu’il peut prendre jusqu’à 24 heures pour que votre nouvelle stratégie prenne effet pour vos utilisateurs.

> [!Note]
> Actuellement, l’attribution de stratégies de modèles aux utilisateurs en fonction de l’appartenance au groupe, par exemple à tous les utilisateurs d’un groupe de sécurité, n’est pas prise en charge. Cette fonctionnalité sera disponible à l’avenir.

Pour obtenir une vue d’ensemble des façons d’affecter des stratégies dans Teams, consultez [Affecter des stratégies dans Teams](policy-assignment-overview.md).

### <a name="assign-a-templates-policy-to-individual-users"></a>Affecter une stratégie de modèles à des utilisateurs individuels

Vous pouvez utiliser le centre d’administration Teams ou PowerShell pour affecter une stratégie de modèles à un utilisateur individuel ou à un petit nombre d’utilisateurs à la fois. Pour plus d’informations, consultez [Affecter une stratégie à des utilisateurs individuels](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

### <a name="assign-a-templates-policy-to-a-batch-of-users"></a>Affecter une stratégie de modèles à un lot d’utilisateurs

Vous pouvez utiliser PowerShell pour affecter une stratégie de modèles à de grands ensembles d’utilisateurs à la fois. Pour ce faire, utilisez l’applet de commande [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) avec TeamsTemplatePermissionPolicy pour ```PolicyType``` envoyer un lot d’utilisateurs et la stratégie de modèles que vous souhaitez affecter. Par exemple :

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

Les attributions sont traitées comme une opération d’arrière-plan et un ID d’opération est généré pour chaque lot. Vous pouvez ensuite utiliser l’applet de commande [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) pour suivre la progression et l’état des affectations dans un lot.

Pour plus d’informations, consultez [Affecter une stratégie à un lot d’utilisateurs à l’aide de PowerShell](assign-policies-users-and-groups.md#use-powershell-method).

## <a name="size-limits-for-templates-policies"></a>Limites de taille pour les stratégies de modèles

Vous pouvez masquer un maximum de 100 modèles par stratégie. Le bouton **Masquer** est désactivé si la stratégie donnée a déjà 100 modèles masqués.

## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

**Q : Si un nouveau modèle est créé, le modèle sera-t-il inclus dans mes stratégies ?**

R : Tous les nouveaux modèles sont visibles par défaut. Vous pouvez choisir de masquer le modèle dans le centre d’administration dans la section Stratégies de modèles.

**Q : Que se passe-t-il si un modèle est supprimé ?**

R : Les modèles supprimés ne seront plus présents dans les stratégies de modèles.

**Q : Puis-je affecter plusieurs utilisateurs à une stratégie de modèles dans le centre d’administration Teams ?**

R : Oui.

1. Dans le centre d’administration Teams, accédez aux **utilisateurs UsersManage** > .
1. Dans la liste des utilisateurs, sélectionnez les utilisateurs que vous souhaitez affecter à la stratégie de modèles.
1. Sélectionnez **Modifier les paramètres**, puis, sous **Stratégie de modèles**, choisissez la stratégie que vous souhaitez affecter.
1. Choisissez **Appliquer**.

Pour plus d’informations, consultez [Affecter une stratégie à des utilisateurs individuels](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users).

**Q : Comment faire afficher tous les utilisateurs affectés à une stratégie spécifique ?**

R : Dans le centre d’administration Teams :

1. Accédez aux **utilisateurs UsersManage** > .
2. Sélectionnez **Filtrer**, définissez un filtre pour la stratégie de modèles, puis **choisissez Appliquer**.

    ![Stratégie de modèles sélectionnée et affichage des utilisateurs.](media/template-policies-5.png)

**Q : Puis-je gérer des stratégies de modèles via PowerShell ?**

R : Non, la gestion des stratégies de modèles dans PowerShell n’est pas prise en charge. Toutefois, vous pouvez utiliser PowerShell pour [affecter des stratégies de modèles](#assign-templates-policies-to-users) aux utilisateurs.

**Q : Les stratégies de modèles s’appliquent-ils à EDU ?**

R : Non, les stratégies de modèles pour EDU ne sont pas prises en charge.

## <a name="related-articles"></a>Articles connexes

- [Démarrage avec des modèles d’équipe dans le Centre d’administration](./get-started-with-teams-templates-in-the-admin-console.md)

- [Créer un modèle d’équipe personnalisé](./create-a-team-template.md)

- [Créer un modèle à partir d’une équipe existante](./create-template-from-existing-team.md)

- [Créer un modèle d’équipe à partir d’un modèle d’équipe existant](./create-template-from-existing-template.md)

- [Attribuer des stratégies à vos utilisateurs dans Microsoft Teams - Microsoft Teams \| Microsoft Docs](./policy-assignment-overview.md)

- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
