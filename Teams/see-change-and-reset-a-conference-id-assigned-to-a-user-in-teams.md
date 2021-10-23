---
title: Consulter, modifier et réinitialiser l’ID de conférence d’un utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Découvrez comment affecter un ID de conférence à un utilisateur Microsoft Teams les paramètres d’ID de conférence.
ms.openlocfilehash: 74e43f6dcb5599039007f784ad7ebdd5a053251e
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536865"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Afficher et réinitialiser un ID de conférence attribué à un utilisateur dans Microsoft Teams

Un ID de conférence est automatiquement attribué à un utilisateur de Microsoft Teams lorsqu’il est configurer pour l’audioconférence dans Microsoft 365 ou Office 365 et utilise Microsoft comme fournisseur de services d’audioconférence. L’ID de conférence attribué est envoyé dans l’invitation à la réunion lorsque la réunion est programmée. Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique. 
  
Bien qu’un ID de conférence soit automatiquement créé et attribué à un utilisateur, il peut arrive qu’un utilisateur ne souhaite pas l’utiliser et que vous le définissez sur un nombre donné, ou que vos utilisateurs ne peuvent pas se souvenir de leur ID de conférence ou qu’ils l’ont perdu. Vous pouvez utiliser le Microsoft Teams d’administration ou Windows PowerShell pour afficher, modifier et réinitialiser leur ID de conférence.
  
Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel. Pour [plus d’informations sur](reset-a-conference-id-for-a-user-in-teams.md) la réinitialisation du code confidentiel d’un organisateur de conférence, voir Réinitialiser l’ID de conférence d’un Microsoft Teams pour plus d’informations. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Afficher et réinitialiser les ID de conférence

### <a name="to-view-the-conference-id"></a>Pour afficher l’ID de conférence

 **Utiliser le centre d’administration Microsoft Teams**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence,** regardez sous **ID de conférence.**

    > [!TIP]
    > Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message  électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur Envoyer les informations sur la conférence dans un lien électronique.
  
**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)
    
  
### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l’ID de conférence

Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.
  
 **Utiliser le centre d’administration Microsoft Teams**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence,** cliquez sur **Réinitialiser l’ID de conférence.**

4. Dans la fenêtre **Réinitialiser l’ID de conférence,** cliquez sur **Réinitialiser.** A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)


## <a name="what-else-should-you-know"></a>Informations supplémentaires

   > [!IMPORTANT]
   >  Une fois qu’un nouvel ID de conférence est créé ou réinitialisé, l’ancien ID de conférence ne peut pas être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. 
  
    
- L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio. Vous ne pouvez pas utiliser de caractères alphabéétiques ou spéciaux dans les ID de conférence. seuls des nombres peuvent être utilisés.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Rubriques connexes

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)