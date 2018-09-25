---
title: Afficher, modifier et réinitialiser l'ID de conférence attribué à un utilisateur dans Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment attribuer un ID de conférence dans Microsoft Teams et quels sont les paramètres d’ID de conférence obligatoires. '
ms.openlocfilehash: 317216f84044eb404541a98d24c69b2f7fb61bc4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017084"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Afficher et réinitialiser l'ID de conférence attribué à un utilisateur dans Microsoft Teams

Un ID de conférence est automatiquement attribué à un utilisateur de Microsoft Teams lorsqu’ils sont configurés pour les services d’audioconférence dans Office 365 et utilisent Microsoft comme fournisseur de services d’audioconférence. L’ID de conférence affecté est envoyé dans l’invitation à la réunion lorsque la réunion est planifiée. Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique. 
  
Bien qu’un ID de conférence est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous voulez lui attribuer un certain nombre, ou lorsque les utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence. Vous pouvez utiliser le centre d’administration de Microsoft Teams ou de Windows PowerShell pour afficher, modifier et de réinitialiser leur ID de conférence.
  
Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel. Pour plus d’informations sur la réinitialisation du code confidentiel de l’organisateur d’une conférence, [Cliquez ici](reset-a-conference-id-for-a-user-in-teams.md). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Afficher et réinitialiser les ID de conférence

### <a name="to-view-the-conference-id"></a>Pour afficher l'ID de conférence

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, recherchez l’**ID de conférence**.

    > [!TIP]
    > Vous pouvez envoyer toutes les informations sur la conférence à l'utilisateur dans un courrier électronique qui inclut l'ID de conférence et les numéros de téléphone à composer en cliquant sur le lien **Envoyer les informations de la conférence dans un courrier électronique**.
  
**Utiliser Windows PowerShell**

Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l'ID de conférence

Si un utilisateur a oublié son ID de conférence, par exemple, vous pouvez le réinitialiser.
  
![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.

4. Dans la fenêtre **Réinitialiser l’ID de conférence** , cliquez sur **Réinitialiser**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Utiliser Windows PowerShell**

Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="what-else-should-you-know"></a>Informations supplémentaires

   > [!IMPORTANT]
   >  Une fois un nouvel ID de conférence est créé ou une est réinitialisée, l’ancien ID de conférence ne peut être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. 
  
    
- L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio. Vous ne pouvez pas utiliser des caractères alphabétiques ou spéciaux conférence ID ; Seuls les nombres peuvent être utilisées.
    
- L'ID de conférence comporte 7 chiffres par défaut pour tous les utilisateurs d’audioconférence. Il n'est pas possible de modifier le nombre de chiffres.
    
    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

