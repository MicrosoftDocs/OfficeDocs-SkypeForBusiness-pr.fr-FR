---
title: Bloquer les transferts de fichiers point à point
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: Dans Skype Entreprise Online, vous pouvez contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cela permet ou bloque les transferts de fichiers pour les utilisateurs, qu’ils transférent ou non des fichiers à un utilisateur de la même organisation ou à un utilisateur fédéré d’une autre organisation. En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.
ms.openlocfilehash: 75e7149d73b8693cf5acdeb08365965956da6ca0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569100"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquer les transferts de fichiers point à point

Dans Skype Entreprise Online, vous pouvez contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cela permet ou bloque les transferts de fichiers pour les utilisateurs, qu’ils transférent ou non des fichiers à un utilisateur de la même organisation ou à un utilisateur fédéré d’une autre organisation. En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.
  
 Un scénario très courant est celui où vous voulez autoriser les utilisateurs internes à utiliser le transfert de fichiers P2P mais bloquer le transfert de fichiers avec des partenaires fédérés. Dans ce scénario, vous devez :
  
- Affectez une stratégie de conférence avec le transfert de fichiers P2P activé _(EnableP2PFileTransfer_ définie sur _True)_ aux utilisateurs de votre organisation.
    
- Créez une stratégie de communication utilisateur externe globale définie pour bloquer les transferts de fichiers P2P externes _(EnableP2PFileTransfer_ définie sur _False)_ et l’affecter à un utilisateur de votre organisation. 
    
Pour en savoir plus sur ces paramètres, [cliquez ici.](https://technet.microsoft.com/library/mt228132.aspx)
  
Si un utilisateur fédéré extérieur à votre organisation tente d’envoyer un fichier à un utilisateur pour lequel la stratégie a été appliquée, il reçoit un message d’erreur « Échec **du** transfert ». Si un utilisateur tente d’envoyer un fichier, il reçoit une erreur **de transfert de** fichier désactivée.
  
Pour ce faire, l’utilisateur doit utiliser une version prise en charge d’une application Skype Entreprise « Exécuter en un clic » 2016 qui la prend en charge. La version minimale suivante du client Skype Entreprise 2016 « Click-to-Run ) est requise :
  
|**Type**|**Date de publication**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release pour Canal actuel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (build 7571.2006)  <br/> |
|Canal actuel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (build 7571.2072)  <br/> |
|Canal différé  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Les utilisateurs qui utilisent des versions antérieures des applications Windows skype Entreprise ou des clients Mac pourront toujours transférer des fichiers. 
  
## <a name="start-windows-powershell"></a>Démarrer Windows PowerShell

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.
1. Installez le [module Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Désactiver les transferts de fichiers P2P pour votre organisation

Par défaut, _EnableP2PFileTransfer_ est activé sur la stratégie globale de l’organisation. Lors de sa création, la stratégie _BposSAllModality_ a été affectée à vos utilisateurs.
  
Pour autoriser les transferts de fichiers P2P au sein de votre organisation, mais bloquer les transferts de fichiers externes vers une autre organisation, vous devez simplement le modifier au niveau global. Pour ce faire, exécutez :
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Désactiver les transferts de fichiers P2P pour un utilisateur

Vous pouvez l’appliquer à un utilisateur en créant une stratégie et en l’octroyant à cet utilisateur. Pour ce faire, exécutez : 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Pourquoi utiliser Microsoft 365 ou PowerShell Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Voir aussi
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
