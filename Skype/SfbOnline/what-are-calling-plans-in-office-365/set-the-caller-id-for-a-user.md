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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Le système téléphonique dans Office 365 fournit une identification de l’appelant par défaut qui est le numéro de téléphone affecté. Vous pouvez modifier ou bloquer l’identification de l’appelant (également appelé une identification de ligne d’appel) pour un utilisateur. Pour plus d’informations sur l’utilisation des identification de l’appelant dans votre organisation consultez Comment l’identification de l’appelant peut-elle être utilisée dans votre organisation.
ms.openlocfilehash: cf6f1aab6f865a87186b7acb793e5aa7829907aa
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780816"
---
# <a name="set-the-caller-id-for-a-user"></a>Définir l’identification de l’appelant d’un utilisateur
Le système téléphonique dans Office 365 fournit une identification de l’appelant par défaut qui est le numéro de téléphone affecté. Vous pouvez modifier ou bloquer l’identification de l’appelant (également appelé une identification de ligne d’appel) pour un utilisateur. Pour plus d’informations sur l’utilisation des identification de l’appelant dans votre organisation consultez [Comment l’identification de l’appelant peut-elle être utilisée dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Vous ne pouvez actuellement pas bloquer les appels entrants dans Skype Entreprise Online. 
  
Vous pouvez changer les paramètres suivants :
  
> [!NOTE]
> Ceci **n'est pas** destiné aux organisations sur site avec Lync ou Skype Entreprise Server.
  
- **Changer l'ID d'appelant sortant** Vous pouvez remplacer l'ID d'appelant d'un utilisateur, constitué par défaut par son numéro de téléphone, par un autre numéro de téléphone. Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique. Vous pouvez remplacer le numéro d'ID d'appel par un numéro de **service** en ligne (payant ou gratuit).
    
    > [!NOTE]
    > Si vous souhaitez utiliser le paramètre _Service_, vous devez spécifier un numéro de service valide.
  
- **Bloquer l’identification de l’appelant sortant** Vous pouvez empêcher l’identification de l’appelant sortant d’être envoyé lors des appels RTC sortants d’un utilisateur. Ce faisant, vous empêchez son numéro de téléphone d’être affiché sur le téléphone d’une personne appelée.
    
- **Bloquer l’identification de l’appelant entrant** Vous pouvez empêcher l’utilisateur de recevoir l’identification de l’appelant de tous les appels RTC entrants.
    
> [!IMPORTANT]
> Les appels d’urgence envoient toujours le numéro de téléphone (identification de l’appelant) de l’utilisateur. 
  
Par défaut, chacun de ces paramètres d'ID d'appelant est **désactivé**. Cela signifie que le numéro de téléphone de l'utilisateur de Skype Entreprise Online est visible lorsque l'utilisateur effectue un appel vers un téléphone RTC.
  
Pour en savoir plus sur ces paramètres et leur utilisation, cliquez [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Définir vos paramètres de politique d’identification de l’appelant

> [!NOTE]
> Pour tous les paramètres d’identification de l’appelant dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration de Skype Entreprise**. 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
1. Depuis le **Menu Démarrer** > **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
> 
  ```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```
> 
  ```
  $credential = Get-Credential
  ```
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```
> 
  ```
  Import-PSSession $session
  ```

Pour plus d’informations sur le démarrage de Windows PowerShell, consultez la rubrique [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connexion à Skype Entreprise Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Voir l’ensemble des paramètres de politique d’identification de l’appelant de votre organisation

- Pour afficher l’ensemble des paramètres de politique d’identification de l’appelant de votre organisation, exécutez :

  ```
  Get-CsCallingLineIdentity |fl
  ```
Consulter plus d’exemples et de détails sur [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Créer une politique d’identification de l’appelant pour votre organisation


- Pour créer une politique d’identification de l’appelant qui définit l’identification de l’appelant sur anonyme, exécutez :
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Dans tous les cas, le champ « Numéro » ne doit pas inclure le préfixe « + ».

  Consulter plus d’exemples et de détails sur [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).
    
- Pour appliquer la nouvelle politique créée pour Amos Marble, exécutez :
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  En savoir plus sur l’applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
Si vous avez déjà créé une politique, vous pouvez utiliser l’applet de commande [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) pour apporter des modifications à la politique existante, puis utiliser l’applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Définir la politique de manière à bloquer l’identification de l’appelant

- Pour bloquer l’identification de l’appelant entrant, exécutez :
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Consulter plus d’exemples et de détails sur [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).
    
- Pour appliquer le paramètre de politique créé à un utilisateur de votre organisation, exécutez :
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    En savoir plus sur l’applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
### <a name="remove-a-caller-id-policy"></a>Stratégie de suppression dʼID dʼappelant

Pour supprimer une stratégie de votre organisation, exécutez :
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Pour supprimer une stratégie dʼun utilisateur, exécutez :
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu’ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Plus d’information sur l’identification de ligne d’appel et le nom du tiers appelant](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
