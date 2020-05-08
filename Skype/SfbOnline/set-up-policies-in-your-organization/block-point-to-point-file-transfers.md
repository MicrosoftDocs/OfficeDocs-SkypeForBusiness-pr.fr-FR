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
description: Dans Skype entreprise Online, vous pouvez contrôler les transferts de fichiers point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cela permet à un utilisateur de transférer des fichiers ou d’en bloquer les transferts de fichiers à des utilisateurs au sein de la même organisation ou à un utilisateur fédéré d’une autre organisation. En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.
ms.openlocfilehash: 773feaa97a888bd2063710de9e72f8c7b465a813
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164723"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquer les transferts de fichiers point à point

Dans Skype entreprise Online, vous pouvez contrôler les transferts de fichiers point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cela permet à un utilisateur de transférer des fichiers ou d’en bloquer les transferts de fichiers à des utilisateurs au sein de la même organisation ou à un utilisateur fédéré d’une autre organisation. En suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations ou partenaires fédérés.
  
 Le scénario le plus courant est que vous souhaitez autoriser les utilisateurs internes à utiliser le transfert de fichiers P2P, mais bloquer le transfert de fichiers avec des partenaires fédérés. Pour ce scénario, vous devez effectuer les opérations suivantes :
  
- Assigner une stratégie de conférence avec le transfert de fichiers P2P activée (_EnableP2PFileTransfer_ défini sur _true_) aux utilisateurs de votre organisation.
    
- Créer une stratégie de communication utilisateur externe globale définie pour bloquer les transferts de fichiers P2P externes (_EnableP2PFileTransfer_ défini sur _false_) et l’affecter à un utilisateur de votre organisation. 
    
Vous pouvez en savoir plus sur [ces paramètres.](https://technet.microsoft.com/library/mt228132.aspx)
  
Si un utilisateur fédéré extérieur à votre organisation tente d’envoyer un fichier à un utilisateur dans lequel la stratégie a été appliquée, il reçoit une erreur de **transfert** . Si un utilisateur tente d’envoyer un fichier, il recevra une erreur de **transfert de fichier** .
  
Pour ce faire, l’utilisateur doit utiliser une version prise en charge d’une application Skype entreprise « démarrer en un clic » de 2016. La version minimum suivante du client « démarrer en un clic » Skype entreprise 2016 est requise :
  
|**Type**|**Date de publication**|**Version**|**Appui**|
|:-----|:-----|:-----|:-----|
|First Release pour canal actuel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571,2006)  <br/> |
|Canal actuel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571,2072)  <br/> |
|Canal différé  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369,2118)  <br/> |
   
> [!CAUTION]
> Les utilisateurs qui utilisent des versions plus anciennes de Skype entreprise Windows ou les clients Mac pourront toujours transférer des fichiers. 
  
## <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
    1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
        
    2. Vérifiez la version en entrant _Get-Host_ dans la fenêtre **Windows PowerShell** .
        
    3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.
        
    4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :
    
        > [!NOTE]
        > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Désactiver les transferts de fichiers P2P pour votre organisation

Par défaut, _EnableP2PFileTransfer_ est activé sur la politique globale de l’organisation. Lors de la création de ce dernier, vos utilisateurs ont reçu la stratégie _BposSAllModality_ .
  
Pour autoriser les transferts P2P au sein de votre organisation, mais bloquer les transferts de fichiers externes vers une autre organisation, il vous suffit de le modifier à un niveau global. Pour cela, exécutez :
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Désactiver le transfert de fichiers P2P pour un utilisateur

Vous pouvez l’appliquer à un utilisateur en créant une nouvelle stratégie et en l’accordant à cet utilisateur. Pour cela, exécutez : 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Raisons pour lesquelles vous avez besoin d’utiliser Microsoft 365 ou Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Voir aussi
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configuration des stratégies de conférence au sein de votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
