---
title: Bloquer les transferts de fichiers point à point
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Dans Skype pour Business Online, vous avez capacité à contrôler les transferts de fichiers point à point (P2P) dans le cadre des paramètres de stratégie de conférence existante. Toutefois, ceci permet ou bloque pour les utilisateurs si elles sont transfert de fichiers à un utilisateur qui se trouve dans la même organisation ou à un utilisateur fédéré à partir d’une autre organisation, les transferts de fichiers. Suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec les organisations fédérées ou des partenaires.
ms.openlocfilehash: 3ae7bce22a99858af36696e1fde41bb614f2c008
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858490"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquer les transferts de fichiers point à point

Dans Skype pour Business Online, vous avez capacité à contrôler les transferts de fichiers point à point (P2P) dans le cadre des paramètres de stratégie de conférence existante. Toutefois, ceci permet ou bloque pour les utilisateurs si elles sont transfert de fichiers à un utilisateur qui se trouve dans la même organisation ou à un utilisateur fédéré à partir d’une autre organisation, les transferts de fichiers. Suivant les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec les organisations fédérées ou des partenaires.
  
 Un scénario très fréquent est lorsque vous souhaitez autoriser les utilisateurs internes à utiliser P2P le transfert de fichiers, mais le transfert de fichiers bloquées avec les partenaires fédérés. Dans ce scénario, vous devez faire :
  
- Affecter une stratégie de conférence P2P transfert de fichiers activé (_EnableP2PFileTransfer_ la valeur _True_) pour les utilisateurs de votre organisation.
    
- Créer une stratégie de communication utilisateur externe globale définie pour bloquer les transferts de fichiers externes P2P (_EnableP2PFileTransfer_ définie sur _False_) et l’affecter à un utilisateur de votre organisation. 
    
Vous trouverez plus d’informations sur ces paramètres [ici](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Si un utilisateur fédéré à l’extérieur de votre organisation tente d’envoyer un fichier à un utilisateur dont la stratégie a été appliquée, ils recevront une erreur **Échec de transfert** . Et si un utilisateur tente d’envoyer un fichier, ils reçoivent une erreur de **transfert de fichiers est désactivé** .
  
Pour ce faire, l’utilisateur doit utiliser une version prise en charge d’un Skype de Click-to-Run 2016 pour l’application de gestion qui prend en charge. La version minimale suivante Skype pour Business 2016 Click-to-Run client est requise :
  
|**Type**|**Date de publication**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|Première version de canal en cours  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (version 7571.2006)  <br/> |
|Canal actuel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (version 7571.2072)  <br/> |
|Canal différée  <br/> |22/2/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (version 7369.2118)  <br/> |
   
> [!CAUTION]
> Les utilisateurs qui utilisent des versions antérieures de Skype pour les applications métiers Windows ou Mac pourront transférer des fichiers. 
  
## <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Vérifier la version en tapant _l’Obtention de l’hôte_ dans la fenêtre **Windows PowerShell** .
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
1. Depuis le **Menu Démarrer** > **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Désactiver les transferts de fichiers P2P pour votre organisation

Par défaut, _EnableP2PFileTransfer_ est activée sur la stratégie globale de l’organisation. Lors de sa création, vos utilisateurs ont été affectés à la stratégie _BposSAllModality_ .
  
Pour autoriser les transferts P2P pour à l’intérieur de votre organisation, mais bloquer les transferts de fichiers externes à une autre organisation, il vous suffit de la modifier à un niveau global. Pour cela, exécutez :
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Désactiver les transferts de fichiers P2P pour un utilisateur

Vous pouvez appliquer cette à un utilisateur en créant une nouvelle stratégie et lui accorder à cet utilisateur. Pour cela, exécutez : 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
 