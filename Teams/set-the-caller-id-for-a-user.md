---
title: Définir l'ID d'appelant d'un utilisateur
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: En savoir plus sur l’ID d’appelant par défaut Microsoft 365 et Office 365 (le numéro de téléphone affecté d’un utilisateur), également appelé ID de ligne d’appel. Vous pouvez modifier ou bloquer l’ID d’appelant d’un utilisateur.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569416"
---
# <a name="set-the-caller-id-for-a-user"></a>Définir l'ID d'appelant d'un utilisateur
Le système téléphonique de Microsoft 365 et Office 365 fournit un ID d’appelant par défaut, qui est le numéro de téléphone affecté à l’utilisateur. Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé ID de ligne d'appel). Pour en savoir plus sur l’utilisation de l’ID d’appelant dans votre organisation, voir Comment utiliser [l’ID](how-can-caller-id-be-used-in-your-organization.md)d’appelant dans votre organisation .
  
> [!TIP]
> Vous ne pouvez actuellement pas bloquer les appels entrants dans Skype Entreprise Online. 
  
Vous pouvez changer les paramètres suivants :
  
> [!NOTE]
> Ceci **n'est pas** destiné aux organisations sur site avec Lync ou Skype Entreprise Server.
  
- **Changer l'ID d'appelant sortant** Vous pouvez remplacer l'ID d'appelant d'un utilisateur, constitué par défaut par son numéro de téléphone, par un autre numéro de téléphone. Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique. Vous pouvez remplacer le numéro d'ID d'appel par un numéro de **service** en ligne (payant ou gratuit).
    
    > [!NOTE]
    > Si vous souhaitez utiliser le paramètre  _Service_, vous devez spécifier un numéro de service valide.
  
- **Bloquer l’ID d’appelant sortant** Vous pouvez empêcher l’ID d’appelant sortant d’être envoyé lors des appels RSTN sortants d’un utilisateur. Ce faisant, vous empêchez son numéro de téléphone d'être affiché sur le téléphone d'une personne contactée.
    
- **Bloquer l’ID d’appelant entrant** Vous pouvez empêcher un utilisateur de recevoir l’ID d’appelant à chaque appel RSTN entrant.
    
> [!IMPORTANT]
> Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur. 
  
Par défaut, chacun de ces paramètres d'ID d'appelant est **désactivé**. Cela signifie que le numéro de téléphone de l'utilisateur de Skype Entreprise Online est visible lorsque l'utilisateur effectue un appel vers un téléphone RTC.
  
Pour en savoir plus sur ces paramètres et leur utilisation, cliquez [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Définir vos paramètres de stratégie d'ID d'appelant

> [!NOTE]
> Pour tous les paramètres **d’ID d’appelant** dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et le Centre d’administration **Skype Entreprise.** 
  
### <a name="start-powershell"></a>Démarrer PowerShell

- Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Voir l'ensemble des paramètres de stratégie d'ID d'appelant de votre organisation

- Pour afficher tous les paramètres de stratégie d’ID d’appelant de votre organisation, exécutez :

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Consultez plus d’exemples et de [détails pour Get-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793856.aspx)
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Créer une stratégie d'ID d'appelant pour votre organisation


- Pour créer une stratégie d’ID d’appelant qui définit l’ID d’appelant sur anonyme, exécutez :
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Dans tous les cas, le champ « Numéro » ne doit pas inclure le préfixe « + ».

  Consultez plus d’exemples et de [détails pour New-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793855.aspx)
    
- Pour appliquer la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Définir la stratégie de manière à bloquer l'ID d'appelant

- Pour bloquer l’ID d’appelant entrant, exécutez :
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Consultez plus d’exemples et de [détails pour Set-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793854.aspx)
    
- Pour appliquer le paramètre de stratégie que vous avez créé à un utilisateur de votre organisation, exécutez :
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
### <a name="remove-a-caller-id-policy"></a>Stratégie de suppression dʼID dʼappelant

Pour supprimer une stratégie de votre organisation, exécutez :
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Pour supprimer une stratégie dʼun utilisateur, exécutez :
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
