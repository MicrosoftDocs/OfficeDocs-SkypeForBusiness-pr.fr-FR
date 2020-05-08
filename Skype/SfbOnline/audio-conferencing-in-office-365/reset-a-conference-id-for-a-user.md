---
title: Réinitialisation de l’ID de conférence d’un utilisateur dans Skype entreprise Online
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez les étapes de réinitialisation de l’ID de conférence d’un utilisateur dans Skype entreprise Online et obtenez des liens vers des outils de mise à jour et de migration de réunions. '
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164703"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Réinitialisation de l’ID de conférence d’un utilisateur dans Skype entreprise Online

> [!NOTE]
> Pour plus d’informations sur la réinitialisation de l’ID de conférence dans Microsoft Teams, voir [Réinitialiser un ID de conférence pour un utilisateur dans Microsoft teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Un ID de conférence dynamique est inclus en bas de l’invitation à la réunion, ainsi que les numéros de téléphone à composer qui peuvent être utilisés par les appelants pour appeler une réunion. Lorsque l’utilisateur compose le numéro de téléphone, le standard automatique de la réunion demande à l’appelant d’entrer cet ID de conférence pour pouvoir participer à la réunion.
  
> [!NOTE]
> S’il s’agit de votre fournisseur de services de conférence Microsoft, les ID de conférence de vos utilisateurs sont définis sur dynamique uniquement. Cette opération ne peut pas être modifiée. Les ID de conférence sont automatiquement définis uniquement pour les utilisateurs Skype entreprise activés pour les conférences audio. 

## <a name="resetting-the-conference-id-for-a-user"></a>Réinitialisation de l’ID de conférence d’un utilisateur
   
1. Dans le **Centre d’administration Skype entreprise**, cliquez sur**utilisateurs**de l' **audioconférence** > , sélectionnez un utilisateur, puis, dans le volet action, sous **ID de conférence** , cliquez sur **Réinitialiser**.
    
2. Dans la fenêtre de **réinitialisation de l’ID de conférence ?** , cliquez sur **Oui**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Par défaut, les courriers électroniques sont envoyés aux utilisateurs, mais ils peuvent être désactivés.
    
> [!NOTE]
> Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce message est envoyé à l’adresse de messagerie principale, dans de nombreux cas, la boîte aux lettres Microsoft 365 ou Office 365. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone et les instructions d'utilisation de l'outil de mise à jour des réunions Skype Entreprise pour mettre à jour les réunions existantes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone à composer en cliquant sur **Envoyer les informations sur la Conférence par courrier électronique** pour l’utilisateur dans le volet action. Le code confidentiel n'est pas envoyé.
    
- Un ID de conférence contient sept chiffres, et vous ne pouvez pas modifier sa longueur dans le centre d’administration Skype entreprise ou à l’aide de Windows PowerShell.
    
- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.
    
- L’ID de conférence d’un utilisateur pour les conférences audio peut être affiché en bas du volet action sous **audioconférence** lorsque vous sélectionnez l’utilisateur dans la page **utilisateurs** .
    
- Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser l’outil de réunion Skype entreprise pour mettre à jour leurs réunions existantes. Pour découvrir comment télécharger, installer et exécuter l’outil de mise à jour de réunion Skype entreprise, reportez-vous aux ressources suivantes :
    
  - [Skype Entreprise (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Outil de migration de réunions Skype Entreprise Online (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Outil de migration de réunions Skype Entreprise Online (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Raisons pour lesquelles vous avez besoin d’utiliser Microsoft 365 ou Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Voir aussi

[Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin.md)
