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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Vous pouvez permettre aux utilisateurs de Skype Entreprise d’utiliser l’outil de commentaires intégré de l’application Skype Entreprise pour permettre aux utilisateurs de signaler des problèmes et de faire part de leurs commentaires directement à Microsoft sur leur expérience.
ms.openlocfilehash: 0c9045a899905e1e09176d086a70bc820267643d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106580"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>Activer ou désactiver les commentaires client sur Skype Entreprise

Vous pouvez permettre à vos utilisateurs Skype Entreprise Online d’utiliser l’outil de commentaires intégré de l’application Skype Entreprise pour permettre aux utilisateurs de signaler des problèmes et de faire part de leurs commentaires directement à Microsoft sur leur expérience. 
  
![Icône Fournir des commentaires](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
Cet outil permet à un utilisateur de copier les journaux de l’application sur son appareil pour aider Microsoft à mieux étudier et résoudre les problèmes qu’il peut avoir. 
  
![Signaler un problème à l’aide de l’icône Paramètres](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
Vous pouvez également utiliser le paramètre  _EnableOnlineFeedbackScreenshot_, qui permet d'inclure une capture d'écran du périphérique lors de l'envoi des commentaires.
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> Les journaux collectés par l’outil de commentaires de l’application seront stockés pendant 90 jours au maximum aux États-Unis pendant que le problème est en cours d’examen. Pour cette raison, n'activez pas cet outil de commentaires si cela enfreint la politique de protection des données de votre organisation. 
  
## <a name="start-windows-powershell"></a>Démarrer Windows PowerShell

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.
1. Installez le [module Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>Activer l'outil de commentaires client de l'application pour tous les utilisateurs au sein de votre organisation

Pour activer la déclaration de commentaires pour les utilisateurs de votre organisation et leur permettre d’envoyer des captures d’écran d’appareil, exécutez :
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
