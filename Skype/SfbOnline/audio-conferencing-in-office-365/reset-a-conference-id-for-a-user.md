---
title: Réinitialiser l’ID de conférence d’un utilisateur dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez les étapes permettant de réinitialiser l’ID de conférence d’un utilisateur dans Skype Entreprise Online et obtenez des liens vers les outils de mise à jour et de migration de réunion. '
ms.openlocfilehash: b2f816cf423a25016a67176d6b1479f585ee14e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586132"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Réinitialiser l’ID de conférence d’un utilisateur dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Pour plus d’informations sur la réinitialisation de l’ID de conférence dans Microsoft Teams, voir Réinitialiser [l’ID](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)de conférence d’un utilisateur Microsoft Teams.

Un ID de conférence dynamique est inclus au bas des invitations aux réunions, ainsi que les numéros de téléphone à composer qui peuvent être utilisés par les appelants pour participer à une réunion. Lorsque l’utilisateur compose le numéro de téléphone, le attendant automatique de la réunion demande à l’appelant d’entrer cet ID de conférence afin qu’il puisse participer à la réunion.
  
> [!NOTE]
> Si votre fournisseur de conférence est Microsoft, l’ID de conférence de vos utilisateurs est définie sur Dynamique uniquement. Cette situation ne peut pas être modifiée. Les ID de conférence sont automatiquement Skype Entreprise pour les utilisateurs activés pour l’audioconférence. 

## <a name="resetting-the-conference-id-for-a-user"></a>Réinitialisation de l’ID de conférence d’un utilisateur
   
1. Dans le **Skype Entreprise d’administration,** cliquez sur **Utilisateurs de l’audioconférence,** sélectionnez un utilisateur, puis dans le volet Action sous  >   **ID** de conférence, cliquez sur **Réinitialiser.**
    
2. Dans la fenêtre **Réinitialiser l’ID de conférence** ? cliquez sur **Oui.** A conference ID will be automatically created and an email sent to the user with the new conference ID. Par défaut, les courriers électroniques sont envoyés aux utilisateurs, mais cette option peut être désactivée.
    
> [!NOTE]
> Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce courrier électronique est envoyé à son adresse de messagerie principale, le plus souvent, Microsoft 365 ou Office 365 boîte aux lettres. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message électronique  qui inclut l’ID de conférence et les numéros de téléphone à composer en cliquant sur Envoyer les informations sur la conférence par courrier électronique à l’utilisateur dans le volet Action. Le code confidentiel n'est pas envoyé.
    
- Un ID de conférence contient sept chiffres, et vous ne pouvez pas modifier sa longueur dans le Skype Entreprise d’administration ou à l’aide Windows PowerShell.
    
- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.
    
- L’ID de conférence d’un utilisateur pour l’audioconférence est  consultable au bas du volet Action sous Audioconférence lorsque vous sélectionnez l’utilisateur dans la **page** Utilisateurs.
    
- Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser Skype Entreprise outil de réunion pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter l’outil de mise à jour Skype Entreprise réunion, voir :
    
  - [Skype Entreprise (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Outil de migration de réunions Skype Entreprise Online (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Outil de migration de réunions Skype Entreprise Online (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes pour gérer vos Microsoft 365 vos Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin.md)
