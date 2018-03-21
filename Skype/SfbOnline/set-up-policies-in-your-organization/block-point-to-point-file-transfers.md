---
title: "Point à point de bloquer les transferts de fichiers"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Dans Skype pour professionnels en ligne, vous avez la possibilité de contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie existants conférence. Toutefois, ce autorise ou bloque les transferts pour les utilisateurs ou non, ils sont transférer des fichiers à un utilisateur qui se trouve dans la même organisation ou à un utilisateur fédéré à partir d’une autre organisation de fichiers. Suivant la procédure décrite ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec les organisations fédérées ou de partenaires."
ms.openlocfilehash: e7b3542cfef3b4dd9b663db0aa056e52fccf021d
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="block-point-to-point-file-transfers"></a>Point à point de bloquer les transferts de fichiers

Dans Skype pour professionnels en ligne, vous avez la possibilité de contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie existants conférence. Toutefois, ce autorise ou bloque les transferts pour les utilisateurs ou non, ils sont transférer des fichiers à un utilisateur qui se trouve dans la même organisation ou à un utilisateur fédéré à partir d’une autre organisation de fichiers. Suivant la procédure décrite ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec les organisations fédérées ou de partenaires.
  
 Un scénario courant est lorsque vous souhaitez permettre aux utilisateurs internes d’utiliser P2P le transfert de fichiers, mais bloquer le transfert de fichiers avec les partenaires fédérés. Dans ce scénario, vous devez faire :
  
- Affecter une stratégie de conférence avec P2P transfert de fichiers activé (_EnableP2PFileTransfer_ la valeur _True_) pour les utilisateurs de votre organisation.
    
- Créer une stratégie de communication utilisateur externe global définie pour bloquer les transferts de fichiers P2P externes (_EnableP2PFileTransfer_ la valeur _False_) et l’affecter à un utilisateur de votre organisation. 
    
Vous trouverez plus d’informations sur ces paramètres [ici](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Si un utilisateur fédéré à l’extérieur de votre organisation essaie d’envoyer un fichier à un utilisateur, où la stratégie a été appliquée, ils recevront une erreur **Échec de transfert** . Et si un utilisateur tente d’envoyer un fichier, une erreur de **transfert de fichiers est désactivé** s’affiche.
  
Pour ce faire, l’utilisateur doit utiliser une version prise en charge d’un Skype clic de 2016 pour l’application d’entreprise qui prend en charge. La version minimale suivante de Skype pour client d’entreprise 2016-clic est nécessaire :
  
|**Type de**|**Date de publication**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|Première version pour canal d’en cours  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Canal de cours  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571.2072)  <br/> |
|Canal différée  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Les utilisateurs qui utilisent des versions antérieures de Skype pour les applications métier Windows ou Mac sera toujours en mesure de transférer des fichiers. 
  
## <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Vérifier la version en tapant _l’Obtention de l’hôte_ dans la fenêtre **Windows PowerShell** .
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [connexion à Skype pour entreprise en ligne à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Désactiver les transferts de fichiers P2P pour votre organisation

Par défaut, _EnableP2PFileTransfer_ est activé dans la stratégie globale de l’organisation. Lorsqu’elle a été créée, vos utilisateurs ont été affectés à la stratégie de _BposSAllModality_ .
  
Pour autoriser les transferts de P2P pour à l’intérieur de votre organisation tout en bloquant les transferts de fichiers externes à une autre organisation, il vous suffit de le modifier à un niveau global. Pour ce faire, exécutez la commande :
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Désactiver les transferts de fichiers P2P pour un utilisateur

Vous pouvez appliquer cette commande à un utilisateur en créant une nouvelle stratégie et de lui accorder à cet utilisateur. Pour ce faire, exécutez la commande : 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Définir des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

## <a name="feedback"></a>Commentaires ?
Pour fournir des commentaires sur le produit ou pour nous faire savoir comment nous faisons, consultez [Skype pour les commentaires de l’entreprise](https://www.skypefeedback.com).