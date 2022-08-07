---
title: Gérer les appareils avec des unités administratives
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser des unités administratives dans Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ccc079617a1ae58b3881da8ae48c8a993d5863
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269469"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Gérer les appareils dans le Centre d’administration Teams avec des unités administratives

Les unités administratives du Centre d’administration Teams fournissent un accès détaillé en fonction du rôle pour la gestion des appareils Teams. Les unités administratives accordent à l’administrateur Teams l’accès à des ressources spécifiques, mais limitent l’accès de cet administrateur à d’autres ressources. Cela est particulièrement utile si vous avez des administrateurs Teams locaux dans différents pays ou régions.

Par exemple, Contoso a des opérations dans le monde entier. Alice est un administrateur informatique général basé à Londres, tandis que Prashant est un administrateur informatique local basé àCrére, en Inde. Aujourd’hui, quand Prashant se connecte au Centre d’administration Teams en tant qu’administrateur d’appareils, il peut voir les appareils Teams dans le monde entier. Alice souhaite limiter l’accès de Prashant aux appareils Teams uniquement à Bengalre. Les unités administratives l’ont laissé faire. Pour en savoir plus, consultez [Unités administratives dans Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> Les unités administratives sont actuellement disponibles dans le Centre d’administration Teams uniquement pour le rôle d’administrateur des appareils Teams.

## <a name="add-administrative-units"></a>Ajouter des unités administratives

Vous devez être administrateur général pour ajouter des unités administratives. Pour savoir comment faire, consultez [Ajouter une unité administrative](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Affecter des administrateurs à des unités administratives

Vous devez également être administrateur général pour affecter des unités administratives. Vous pouvez affecter des unités administratives à l’aide de Portail Azure, PowerShell ou microsoft API Graph. Pour plus d’informations, consultez [Attribuer des rôles Azure AD avec étendue d’unité administrative](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Sélectionner des unités administratives

Si vous êtes administrateur d’appareils Teams, une fois qu’un administrateur général vous a affecté à une unité administrative, vous pouvez vous connecter au Centre d’administration Teams pour gérer les appareils. Si vous n’êtes affecté qu’à une seule unité administrative, seuls les appareils affectés à cette unité administrative s’affichent. Si vous êtes affecté à plusieurs unités administratives, vous pouvez basculer entre ces unités administratives sans vous déconnecter du Centre d’administration Teams. 

1. Connectez-vous au [Centre d’administration Teams](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Dans la boîte de dialogue **Vos unités administratives** , procédez comme suit :
    - Sélectionnez l’unité administrative que vous souhaitez gérer, ou 
    - Sélectionnez **Tous les appareils** si vous êtes autorisé à gérer tous les appareils de votre organisation.

3. Sélectionnez **Enregistrer**.

## <a name="switch-administrative-units"></a>Changer d’unité administrative

Si vous êtes administrateur d’appareils Teams, vous pouvez basculer entre les unités administratives si vous êtes connecté au Centre d’administration Teams. Pour basculer vers une autre unité administrative :

1. Connectez-vous au [Centre d’administration Teams](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Dans le volet de navigation de gauche, sélectionnez **Appareils Teams**.

3. Dans le volet droit, en haut à gauche, sélectionnez l’unité administrative affichée.

4. Dans la boîte de dialogue **Vos unités administratives** , procédez comme suit :
    - Sélectionnez l’unité administrative que vous souhaitez gérer, ou 
    - Sélectionnez **Tous les appareils** si vous êtes autorisé à gérer tous les appareils de votre organisation.

5. Sélectionnez **Enregistrer**.

## <a name="related-topics"></a>Voir aussi

- [Ajouter des utilisateurs ou des groupes à une unité administrative](/azure/active-directory/roles/admin-units-members-add)
