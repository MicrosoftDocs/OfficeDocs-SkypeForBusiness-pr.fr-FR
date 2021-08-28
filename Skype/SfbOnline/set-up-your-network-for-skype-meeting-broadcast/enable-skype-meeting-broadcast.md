---
title: Activer une diffusion de réunion Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Pour que les membres de votre organisation Réunion Skype la diffusion de groupe, vous devez l’activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne connaissez pas Windows PowerShell, envisagez de demander l'aide d'un partenaire Microsoft pour effectuer cette étape pour vous.
ms.openlocfilehash: 4f16444a07c81b44e4078a2c294208f59e4d7775
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599669"
---
# <a name="enable-skype-meeting-broadcast"></a>Activer une diffusion de réunion Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Skype Entreprise Online prend fin le 31 juillet 2021, date à laquelle l’accès au service prendra fin. Nous encourageons les clients à commencer la mise à niveau vers Microsoft Teams, le client principal pour les communications et le travail d’équipe au Microsoft 365.

Pour que les membres de votre organisation Réunion Skype la diffusion de groupe, vous devez l’activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne connaissez pas Windows PowerShell, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.



> [!NOTE]
> Le Microsoft Teams d’administration a remplacé Skype Entreprise centre d’administration principal (portail hérité). Tous les paramètres de gestion des Skype Entreprise sont désormais dans le Centre Teams’administration. Le rôle d’administrateur [Azure AD](/azure/active-directory/roles/permissions-reference) de l’administrateur global ou de l’administrateur de Skype Entreprise vous doit être attribué pour gérer les fonctionnalités de gestion des Skype Entreprise dans le Teams d’administration. Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Activer la diffusion de réunion Skype au moyen du Centre d'administration de Skype Entreprise

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

1. Connectez-vous avec votre compte d’administrateur global ou Skype Entreprise compte d’administrateur à [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. Dans le Centre d’administration, allez sur Centres **d’administration**  >  **Teams.**
    
3. Dans le **Teams d’administration,** allez dans les réunions de diffusion de réunion du portail hérité, puis sélectionnez  >    >  Activer **Réunion Skype diffusion.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Activer la diffusion de réunion Skype avec PowerShell

1. Installez le [module Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Confirmez votre configuration Diffusion de réunion Skype actuelle en exécutant :
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Vérifiez que le paramètre  _EnableBroadcastMeeting_ est défini sur `False`.
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Activez Diffusion de réunion Skype pour votre organisation en exécutant :
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Vous pouvez vérifier que le paramètre est activé en le exécutant  `Get-CsBroadcastMeetingConfiguration` à nouveau.
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Une fois la modification effectuée, sa prise en compte sur le portail Diffusion de réunion Skype peut prendre jusqu'à une heure. 
  
10. Vos utilisateurs peuvent à présent organiser des réunions diffusées avec d'autres utilisateurs dans votre entreprise. Pour commencer, dirigez-les vers [Qu'est-ce qu'une diffusion de réunion Skype ?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d).
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurer votre réseau pour la diffusion de réunions à des participants externes

Si vous avez un pare-feu, et que vous souhaitez héberger des diffusions pour des personnes extérieures à votre entreprise (qui n'est pas une entreprise fédérée), vous devez configurer votre réseau avec les instructions suivantes : [Configurer votre réseau pour la Diffusion de réunion Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.
  
Pour ignorer cette étape et ajouter une autre entreprise à votre fédération, consultez [Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Rubriques connexes

[Présentation de Windows PowerShell et de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
