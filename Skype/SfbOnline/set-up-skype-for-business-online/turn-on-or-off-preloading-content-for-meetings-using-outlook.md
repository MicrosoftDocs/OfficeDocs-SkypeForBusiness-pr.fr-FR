---
title: Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
- Setup
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 456b6a0a94aa2daf3a61b7ade00dcafdbcf3d371
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619240"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Les utilisateurs peuvent précharger du contenu, des fichiers ou des pièces jointes joints à une invitation à une réunion Outlook à une réunion Skype Entreprise Online, mais vous pouvez activer ou désactiver cette fonction. Elle est désactivée par défaut pour toutes les organisations qui utilisent Skype Entreprise Online. Découvrez comment [Préchargement des pièces jointes pour une réunion Skype Entreprise](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).
  
> [!NOTE]
> Actuellement, il n’existe aucune cmdlets disponibles dans Skype Entreprise Online pour définir ou afficher les valeurs en ligne pour _MaxContentStorageMB_ et _MaxUploadFileMB._ Elles ne sont disponibles que pour les déploiements locaux. Il est important de savoir que le contenu ne sera pas téléchargé dans une réunion si le contenu joint dépasse la limite  _MaxUploadFileSizeMB_ ou si la limite _maxContentStorageMB_ est atteinte.
  
## <a name="to-get-you-started"></a>Pour commencer

## <a name="start-windows-powershell"></a>Démarrer Windows PowerShell

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.
1. Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="turning-it-on-or-off"></a>Activation ou désactivation des applications intégrées

La possibilité de précharger du contenu joint à une invitation à une réunion Outlook pour des réunions Skype Entreprise Online est désactivée par défaut, mais vous devrez peut-être empêcher les utilisateurs de votre organisation de précharger du contenu dans leurs réunions.
  
> [!IMPORTANT]
> Ce paramètre peut uniquement être désactivé pour l’ensemble de votre organisation. vous ne pouvez pas l’activer ou le désactiver pour un seul utilisateur. 
  
 **Pour le désactiver, ouvrez Windows PowerShell et procédez comme suit :**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Si vous voulez le réactiver, ouvrez Windows PowerShell et procédez comme suit :**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365 ou des Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
