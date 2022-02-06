---
title: Gérer les appareils avec des unités d’administration
author: mahoffman
ms.author: serdars
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser les unités d’administration dans Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
  - NOCSH
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Gérer les appareils dans le centre Teams d’administration avec des unités d’administration

Les unités d’administration du Teams d’administration fournissent un accès détaillé basé sur le rôle pour la gestion d Teams appareils mobiles. Les unités d’administration Teams l’accès d’un administrateur à des ressources spécifiques, mais limitent son accès à d’autres ressources. Ceci est particulièrement utile si vous avez des administrateurs Teams locaux dans différents pays ou régions.

Par exemple, Contoso a des opérations dans le monde entier. Contrôle est un administrateur informatique global basé à Londres, tandis que Prashant est un administrateur informatique local basé à Bengalre, Inde. Aujourd’hui, lorsque Prashant se Teams au Centre d’administration en tant qu’administrateur de périphériques, il peut voir Teams appareils dans le monde entier. L’équipe souhaite limiter l’accès de Prashant aux Teams aux périphériques de cette ville uniquement. Les unités d’administration lui la la font. Pour plus d’informations, [voir unités d’administration dans Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> Les unités d’administration sont actuellement disponibles dans le Centre Teams’administration pour le rôle d Teams administrateur de périphériques uniquement.

## <a name="add-administrative-units"></a>Ajouter des unités d’administration

Vous devez être un administrateur global pour ajouter des unités d’administration. Pour savoir comment faire, voir [Ajouter une unité d’administration](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Affecter des administrateurs à des unités d’administration

Vous devez également être administrateur global pour affecter des unités d’administration. Vous pouvez affecter des unités d’administration à l’aide du portail Azure, de PowerShell ou de l’API Microsoft Graph. Pour plus d’informations, voir [Attribuer Azure AD à des rôles ayant une étendue d’unité d’administration](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Sélectionner les unités d’administration

Si vous êtes un administrateur Teams appareils, après qu’un administrateur global vous a attribué une unité d’administration, vous pouvez vous connectez au Centre d’administration Teams pour gérer les appareils. Si vous n’êtes affecté qu’à une seule unité d’administration, vous ne verrez que les appareils affectés à cette unité d’administration. Si vous êtes affecté à plusieurs unités d’administration, vous pouvez basculer de l’une à l’autre sans vous dé signer à partir Teams centre d’administration. 

1. Connectez-vous au [Teams d’administration.](https://go.microsoft.com/fwlink/p/?linkid=2024339)

2. Dans la **boîte de dialogue Vos unités** d’administration, suivez l’une des étapes suivantes :
    - Sélectionnez l’unité d’administration que vous voulez gérer, ou 
    - **Sélectionnez Tous les appareils** si vous êtes autorisé à gérer tous les appareils pour votre organisation.

3. Sélectionnez **Enregistrer**.

## <a name="switch-administrative-units"></a>Changer d’unité d’administration

Si vous êtes un administrateur Teams appareils mobiles, vous pouvez basculer entre les unités d’administration si vous êtes connecté au Centre Teams’administration. Pour changer d’unité d’administration :

1. Connectez-vous au [Teams d’administration.](https://go.microsoft.com/fwlink/p/?linkid=2024339)

2. Dans la barre de navigation gauche, **sélectionnez Teams périphériques.**

3. Dans le volet droit, dans le coin supérieur gauche, sélectionnez l’unité d’administration affichée.

4. Dans la **boîte de dialogue Vos unités** d’administration, suivez l’une des étapes suivantes :
    - Sélectionnez l’unité d’administration que vous voulez gérer, ou 
    - **Sélectionnez Tous les appareils** si vous êtes autorisé à gérer tous les appareils pour votre organisation.

5. Sélectionnez **Enregistrer**.
