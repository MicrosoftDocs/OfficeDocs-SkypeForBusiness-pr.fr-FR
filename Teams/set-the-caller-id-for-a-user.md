---
title: Définir l'ID d'appelant d'un utilisateur
ms.author: tonysmit
author: tonysmit
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
description: En savoir plus sur l’ID de l’appelant par défaut d’Office 365 (le numéro de téléphone affecté à l’utilisateur), également connu sous le nom d’ID de ligne d’appel. Vous pouvez modifier ou bloquer l’ID d’appelant d’un utilisateur.
ms.openlocfilehash: c04fdfa7dc395f31eb3277fe0ab2f77aa92605c7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140907"
---
# <a name="set-the-caller-id-for-a-user"></a>Définir l'ID d'appelant d'un utilisateur
Le système téléphonique dans Office 365 fournit un ID d’appelant par défaut qui est le numéro de téléphone attribué. Vous pouvez modifier ou bloquer l'ID d'appelant (également appelé ID de ligne d'appel). Pour plus d’informations sur l’utilisation de l’identification de l’appelant au sein de votre organisation, voir utilisation [de l’ID d’appelant au sein de votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Vous ne pouvez actuellement pas bloquer les appels entrants dans Skype Entreprise Online. 
  
Vous pouvez changer les paramètres suivants :
  
> [!NOTE]
> Ceci **n'est pas** destiné aux organisations sur site avec Lync ou Skype Entreprise Server.
  
- **Changer l'ID d'appelant sortant** Vous pouvez remplacer l'ID d'appelant d'un utilisateur, constitué par défaut par son numéro de téléphone, par un autre numéro de téléphone. Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique. Vous pouvez remplacer le numéro d'ID d'appel par un numéro de **service** en ligne (payant ou gratuit).
    
    > [!NOTE]
    > Si vous souhaitez utiliser le paramètre  _Service_, vous devez spécifier un numéro de service valide.
  
- **Bloquer l’ID d’appelant sortant** Vous pouvez empêcher l’envoi de l’ID d’appelant sortant sur les appels RTC sortants d’un utilisateur. Ce faisant, vous empêchez son numéro de téléphone d'être affiché sur le téléphone d'une personne contactée.
    
- **Bloquer l’ID d’appelant entrant** Vous pouvez empêcher un utilisateur de recevoir l’ID d’appelant à chaque appel RTC entrant.
    
> [!IMPORTANT]
> Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur. 
  
Par défaut, chacun de ces paramètres d'ID d'appelant est **désactivé**. Cela signifie que le numéro de téléphone de l'utilisateur de Skype Entreprise Online est visible lorsque l'utilisateur effectue un appel vers un téléphone RTC.
  
Pour en savoir plus sur ces paramètres et leur utilisation, cliquez [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Définir vos paramètres de stratégie d'ID d'appelant

> [!NOTE]
> Pour tous les paramètres d’identification de l’appelant dans Skype entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration Skype entreprise**. 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
   > [!NOTE]
   > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Voir l'ensemble des paramètres de stratégie d'ID d'appelant de votre organisation

- Pour afficher tous les paramètres de stratégie d’ID d’appelant au sein de votre organisation, exécutez :

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Voir d’autres exemples et des informations supplémentaires sur [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Créer une stratégie d'ID d'appelant pour votre organisation


- Pour créer une nouvelle stratégie d’ID d’appelant qui définit l’ID d’appelant sur anonyme, exécutez :
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Dans tous les cas, le champ « Numéro » ne doit pas inclure le préfixe « + ».

  En savoir plus sur [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).
    
- Pour appliquer la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Définir la stratégie de manière à bloquer l'ID d'appelant

- Pour bloquer l’ID de l’appelant, exécutez :
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  En savoir plus sur [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).
    
- Pour appliquer le paramètre de stratégie que vous avez créé à un utilisateur de votre organisation, exécutez :
    
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

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d’utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
