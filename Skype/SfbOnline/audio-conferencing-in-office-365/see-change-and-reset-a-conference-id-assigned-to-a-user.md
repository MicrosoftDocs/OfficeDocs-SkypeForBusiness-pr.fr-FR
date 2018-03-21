---
title: "Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to assign a conference ID to a user in Skype for Business and what the conference ID''s parameters should be. '
ms.openlocfilehash: b542e764d0b8b1587c34e78a54612410cd72a3bd
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur

Un ID de conférence est automatiquement affecté à un Skype pour l’utilisateur professionnel ou Teams de Microsoft lorsqu’ils sont configurés pour les conférences Audio dans Office 365 et utilisent Microsoft comme fournisseur de conférence audio. L’ID de conférence affecté peut être statique ou dynamique et est envoyé dans l’invitation à une réunion lorsque la réunion est planifiée.
  
ID statiques sont utilisés lorsque les personnes de votre organisation ne souhaitant mémoriser un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utiliser un qui soit facile à mémoriser. Lorsque des ID de conférence dynamiques sont utilisés, chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique. Si vous souhaitez affecter les dynamique au lieu de la conférence static ID, [Cliquez ici](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Bien qu’un ID de conférence statique sera automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous souhaitez la définir pour un certain nombre, ou lorsque vos utilisateurs ne vous souvenez plus ou ont perdu leur ID de conférence. Vous pouvez utiliser le **Skype pour Business admin center** et de Windows PowerShell pour afficher, de modifier et de réinitialiser leur ID de conférence.
  
Un e-mail sera envoyé à l’utilisateur avec l’ID de conférence et les numéros de téléphone de conférence audio par défaut, ou si vous réinitialisez l’ID de conférence une autre adresse e-mail sera envoyée qui inclut l’ID de conférence, mais pas d’un code confidentiel.
  
## <a name="view-and-change-conference-ids"></a>Permet d’afficher et de modifier l’ID de conférence

### <a name="to-view-the-conference-id"></a>Permet d’afficher l’ID de conférence

Vous pouvez afficher leur ID de conférence et l’envoyer aux utilisateurs.
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le **Skype pour le centre d’administration Business**> **audioconférence** > **les utilisateurs**, sélectionnez l’utilisateur qui a besoin de code de la conférence
    
4. Dans la page Action, regardez sous **l’ID de la conférence**.
    
    > [!TIP]
    > Vous pouvez envoyer toutes les informations de la conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur le lien **Envoyer les informations de conférence par courrier électronique** une fois que vous sélectionnez l’utilisateur dans la page **utilisateurs** .
  
    Vous pouvez utiliser Windows PowerShell pour afficher l’ID de conférence pour un utilisateur. Pour ce faire, exécutez la commande :
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    Reportez-vous à la section [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) pour en savoir plus sur l’applet de commande.
    
### <a name="to-assign-or-change-the-conference-id"></a>Pour affecter ou modifier l’ID de conférence

Vous pouvez affecter ou modifier un ID de conférence d’un utilisateur si, par exemple, un utilisateur souhaite un ID de conférence qui est facile à mémoriser.

  > [!NOTE]
  > Le Skype pour le centre d’administration commerciale ne permet pas de modifier un ID de conférence qui a été créé automatiquement, mais vous pouvez utiliser Windows PowerShell pour les modifier ou changer un ID de conférence que vous avez définies. 
     
Pour modifier ou changer l’ID de conférence pour un utilisateur, exécutez la commande :
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > Pour définir l'ID de conférence d'un utilisateur, exécutez : 
  
### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l’ID de conférence

Vous pouvez réinitialiser un ID de conférence d’un utilisateur si, par exemple, si elles l’oublier.
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le **Skype pour le centre d’administration Business**> **audioconférence** > **les utilisateurs**, dans le volet Actions, sous **ID de conférence**, cliquez sur **Réinitialiser**.
    
4. Dans le **Réinitialiser l’ID de conférence ?** la fenêtre, cliquez sur **Oui**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    Vous pouvez réinitialiser l’ID de conférence pour un utilisateur à l’aide de la de Windows PowerShell. Pour ce faire, exécutez la commande :
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a>Informations supplémentaires

   > [!IMPORTANT]
   >  Après la création d’un nouvel ID de conférence ou une réinitialisation, l’ancien ID de conférence ne peut pas être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business mise à jour de leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter l’outil, reportez-vous à la section : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, l’outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online, l’outil de Migration de réunion (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
- Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- L’ID de conférence doit respecter la longueur en chiffres sur le pont de conférence audio. Vous ne pouvez pas utiliser les caractères alphabétiques ou spéciales conférence ID ; Seuls des numéros peuvent être utilisés.
    
- L’ID de conférence pour tous vos utilisateurs de conférence audio sera 7 chiffres par défaut et le nombre de chiffres ne peut pas être modifié.
    
- Si l’utilisateur est déplacé à partir de Microsoft en tant que le fournisseur de conférence audio à un fournisseur de conférence audio de tiers ou le fournisseur de conférence audio est défini sur **Aucun**, l’ID de conférence ne fonctionneront plus. Reportez-vous à la section [affecter un comme fournisseur de conférence audio tiers](assign-a-third-party-as-the-audio-conferencing-provider.md) ou le [déplacement de fournisseur de conférence audio d’un utilisateur à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)

