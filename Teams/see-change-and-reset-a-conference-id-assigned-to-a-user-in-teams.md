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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Découvrez comment affecter un ID de conférence à un utilisateur dans Microsoft Teams et ce que doivent être les paramètres d’ID de conférence.
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691150"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Afficher et réinitialiser l'ID de conférence attribué à un utilisateur dans Microsoft Teams

Un ID de conférence est automatiquement attribué à un utilisateur de Microsoft Teams lorsqu’il est configurer pour l’audioconférence dans Microsoft 365 ou Office 365 et qu’il utilise Microsoft comme fournisseur de services d’audioconférence. L'ID de conférence attribué est envoyé dans l'invitation à participer à la réunion lors de sa planification. Chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique. 
  
Bien qu'un ID de conférence soit automatiquement créé et attribué à un utilisateur, il arrive qu'un utilisateur ne souhaite pas utiliser cet ID et préfère le définir sur un numéro spécifique, ou qu’il ne se rappelle pas de son ID de conférence ou l’ait perdu. Vous pouvez utiliser le centre d'administration de Microsoft Teams ou Windows PowerShell pour afficher, modifier et réinitialiser son ID de conférence.
  
Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel. Pour [plus d’informations sur](reset-a-conference-id-for-a-user-in-teams.md) la réinitialisation du code confidentiel d’un organisateur de conférence, voir Réinitialiser l’ID de conférence d’un utilisateur dans Microsoft Teams. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Afficher et réinitialiser les ID de conférence

### <a name="to-view-the-conference-id"></a>Pour afficher l'ID de conférence

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, recherchez l’**ID de conférence**.

    > [!TIP]
    > Vous pouvez envoyer toutes les informations sur la conférence à l'utilisateur dans un courrier électronique qui inclut l'ID de conférence et les numéros de téléphone à composer en cliquant sur le lien **Envoyer les informations de la conférence dans un courrier électronique**.
  
**Utiliser Windows PowerShell**

Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l'ID de conférence

Si un utilisateur a oublié son ID de conférence, par exemple, vous pouvez le réinitialiser.
  
![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.

4. Dans la fenêtre **Réinitialiser l’ID de conférence**, cliquez sur **Réinitialiser**. Un ID de conférence sera créé automatiquement et un courrier électronique contenant le nouvel ID sera envoyé à l’utilisateur.
  
**Utiliser Windows PowerShell**

Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="what-else-should-you-know"></a>Informations supplémentaires

   > [!IMPORTANT]
   >  Une fois qu'un nouvel ID de conférence est créé ou réinitialisé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. 
  
    
- L'ID de conférence doit respecter le nombre de chiffres défini dans le pont d’audioconférence. Les ID de conférence ne doivent comporter que des chiffres, jamais des caractères alphabétiques ou spéciaux.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Rubriques connexes

[Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
