---
title: Activer ou désactiver les commentaires client sur Skype Entreprise
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: Vous pouvez permettre à vos utilisateurs Skype Entreprise d’utiliser l’outil de commentaires intégré à l’application Skype Entreprise pour permettre aux utilisateurs de signaler des problèmes et de faire part de leurs commentaires directement à Microsoft sur leur expérience.
ms.openlocfilehash: 9382c19c5abf78dc47dcaa3de33841a64e96f490
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728283"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Activer ou désactiver les commentaires client sur Skype Entreprise

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Vous pouvez permettre aux utilisateurs de Skype Entreprise Online d’utiliser l’outil de commentaires intégré à l’application Skype Entreprise pour permettre aux utilisateurs de signaler des problèmes et de faire part de leurs commentaires directement à Microsoft sur leur expérience. 
  
![Icône Fournir des commentaires.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
Cet outil permet à un utilisateur de copier les journaux de l’application sur son appareil pour aider Microsoft à mieux étudier et résoudre les problèmes qu’il peut avoir. 
  
![Signalez un problème à l’aide Paramètres’icône.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
Vous pouvez également utiliser le paramètre  _EnableOnlineFeedbackScreenshot_, qui permet d'inclure une capture d'écran du périphérique lors de l'envoi des commentaires.
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> Les journaux collectés par l’outil de commentaires de l’application seront stockés pendant 90 jours au maximum aux États-Unis pendant que le problème est en cours d’examen. Pour cette raison, n'activez pas cet outil de commentaires si cela enfreint la politique de protection des données de votre organisation. 
  
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
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>Activer l'outil de commentaires client de l'application pour tous les utilisateurs au sein de votre organisation

Pour activer la déclaration de commentaires pour les utilisateurs de votre organisation et leur permettre d’envoyer des captures d’écran d’appareil, exécutez :
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
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

  
