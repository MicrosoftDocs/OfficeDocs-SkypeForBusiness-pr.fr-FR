---
title: Définir l'ID d'appelant d'un utilisateur
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: En savoir plus sur Microsoft 365 et Office 365'ID d’appelant par défaut (le numéro de téléphone affecté d’un utilisateur), également appelé ID de ligne d’appel. Vous pouvez modifier ou bloquer l’ID d’appelant d’un utilisateur.
ms.openlocfilehash: 9a69cf864cbf57d7ebf82ae079f88a888d3fc9f0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613583"
---
# <a name="set-the-caller-id-for-a-user"></a>Définir l'ID d'appelant d'un utilisateur

Système téléphonique dans Microsoft 365 fournit un ID d’appelant par défaut, c’est-à-dire le numéro de téléphone affecté à l’utilisateur. Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé ID de ligne d'appel). Pour en savoir plus sur l’utilisation de l’ID d’appelant dans votre organisation, voir Comment utiliser [l’ID](how-can-caller-id-be-used-in-your-organization.md)d’appelant dans votre organisation .
  
Par défaut, les paramètres d’ID d’appelant suivants **sont désactivés.** Cela signifie que le Teams de téléphone de l’utilisateur peut être vu quand cet utilisateur appelle un téléphone PSTN. Vous pouvez modifier ces paramètres comme suit :
  
- **ID de l’appelant sortant** Vous pouvez remplacer l’ID d’appelant d’un utilisateur, qui est son numéro de téléphone par défaut, par un autre numéro de téléphone. Par exemple, vous pouvez modifier l’ID d’appelant de l’utilisateur de son numéro de téléphone en numéro de téléphone principal de votre entreprise ou en numéro de téléphone principal du service juridique. En outre, vous pouvez définir le numéro d’ID d’appel sur n’importe quel numéro de service en ligne (gratuit ou gratuit) ou sur un numéro de téléphone local via un routage direct affecté à un compte de ressource utilisé par une Standard automatique ou une file d’attente d’appels.
    
  > [!NOTE]
  > Si vous souhaitez utiliser le paramètre *Service,* vous devez spécifier un numéro de service valide.
  > Si ce n’est pas le cas, vous devez utiliser les cmdlets PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity du module Teams PowerShell 2.3.1 ou une date ultérieure.
  
- **Bloquer l’ID d’appelant sortant** Vous pouvez empêcher l’ID d’appelant sortant d’être envoyé lors des appels RSTN sortants d’un utilisateur. Ce faisant, vous empêchez son numéro de téléphone d'être affiché sur le téléphone d'une personne contactée.
    
- **Bloquer l’ID d’appelant entrant.** Vous pouvez empêcher un utilisateur de recevoir l’ID d’appelant à chaque appel RSTN entrant.

- **Définissez le nom de l’appelant (CNAM).** Pour vos Microsoft Teams utilisateurs, vous pouvez envoyer un CNAM dans les appels RSTN sortants.
    
> [!IMPORTANT]
> Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur. 
  

  
Pour en savoir plus sur ces paramètres et sur leur utilisation, consultez comment utiliser l’ID d’appelant [dans votre organisation.](how-can-caller-id-be-used-in-your-organization.md)
  
## <a name="set-your-caller-id-policy-settings"></a>Définir vos paramètres de stratégie d'ID d'appelant

> [!NOTE]
> Pour définir l’ID d’appelant sur un numéro de téléphone de compte de ressource et définir le nom de l’appelant, utilisez les cmdlets PowerShell New-CsCallingLineIdentity ou Set-CsCallingLineIdentity dans le module Teams PowerShell 2.3.1 ou une ultérieure. (Ces options ne sont actuellement pas disponibles dans le Microsoft Teams d’administration.) 

Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>Afficher, créer et appliquer des paramètres de stratégie

1. Pour afficher tous les paramètres de stratégie d’ID d’appelant dans votre organisation, exécutez :

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   Pour plus d’informations, [voir Get-CsCallingLineIdentity.](/powershell/module/skype/Get-CsCallingLineIdentity)
    
2. Pour créer une stratégie d’ID d’appelant pour votre organisation, utilisez l'New-CsCallingIdentity de la société :
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    Dans tous les cas, le champ « Numéro » ne doit pas inclure le préfixe « + ».

   Pour plus d’informations, [voir New-CsCallingLineIdentity.](/powershell/module/skype/New-CsCallingLineIdentity)
    
3. Appliquez la nouvelle stratégie que vous avez créée à l’aide Grant-CsCallingIdentity cmdlet. Par exemple, l’exemple suivant applique la nouvelle stratégie à l’utilisateur Amos Marble.
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   Pour plus d’informations, [voir la cmdlet Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)
    

4. Si vous souhaitez bloquer l’ID d’appelant entrant, exécutez :
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   Pour plus d’informations, [voir Set-CsCallingLineIdentity.](/powershell/module/skype/Set-CsCallingLineIdentity)
    
5. Pour appliquer le paramètre de stratégie que vous avez créé à un utilisateur de votre organisation, exécutez :
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   Pour plus d’informations, [voir Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)

6. Pour créer une stratégie d’ID d’appelant qui définit l’ID d’appelant sur le numéro de téléphone du compte de ressource spécifié et définit le nom de l’appelant sur Contoso :

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) pour appliquer les paramètres à vos utilisateurs.
    
### <a name="remove-a-policy-setting"></a>Supprimer un paramètre de stratégie

Pour supprimer une stratégie de votre organisation, exécutez :
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Pour supprimer une stratégie dʼun utilisateur, exécutez :
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365'aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
- [Présentation des Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
- [Les meilleures façons de gérer Microsoft 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](./phone-number-calling-plans/port-order-overview.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
