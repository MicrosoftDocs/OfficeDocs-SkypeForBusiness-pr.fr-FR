---
title: "Définir l'ID d'appelant d'un utilisateur"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Le système téléphonique dans Office 365 fournit un ID de l’appelant par défaut qui est le numéro attribué à l’utilisateur. Vous pouvez modifier ou bloquer l’ID de l’appelant (également appelé une ID de ligne d’appel) pour un utilisateur. Pour plus d’informations sur l’utilisation des ID de l’appelant dans votre organisation en continu, ID de l’appelant utilisation dans votre organisation."
ms.openlocfilehash: d1f663ae0f440907d9ad0104ff2f8ecf7b171aaf
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-caller-id-for-a-user"></a>Définir l'ID d'appelant d'un utilisateur
Le système téléphonique dans Office 365 fournit un ID de l’appelant par défaut qui est le numéro attribué à l’utilisateur. Vous pouvez modifier ou bloquer l’ID de l’appelant (également appelé une ID de ligne d’appel) pour un utilisateur. Pour plus d’informations sur l’utilisation des ID de l’appelant dans votre organisation à partir de [l’ID de l’appelant utilisable dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> Vous ne pouvez pas bloquer les appels entrants actuellement dans Skype pour l’activité en ligne. 
  
Vous pouvez changer les paramètres suivants :
  
> [!NOTE]
> Ceci **n'est pas** destiné aux organisations sur site avec Lync ou Skype Entreprise Server.
  
- **Changer l'ID d'appelant sortant** Vous pouvez remplacer l'ID d'appelant d'un utilisateur, constitué par défaut par son numéro de téléphone, par un autre numéro de téléphone. Par exemple, vous pouvez redéfinir l'ID d'appelant de l'utilisateur constitué par son numéro de téléphone sur un numéro de téléphone principal de votre entreprise ou redéfinir son ID de ligne d'appel constitué par son numéro de téléphone sur un numéro de téléphone principal du service juridique. Vous pouvez remplacer le numéro d'ID d'appel par un numéro de **service** en ligne (payant ou gratuit).
    
    > [!NOTE]
    > Si vous souhaitez utiliser le paramètre  _Service_, vous devez spécifier un numéro de service valide.
  
- **Bloc de leur ID d’appelant sortant** Vous pouvez bloquer l’ID d’appelant sortants d’être envoyés sur les appels RTPC sortants d’un utilisateur. Cela bloque leur numéro de téléphone à partir de l’affichage sur le téléphone d’une personne appelée.
    
- **Bloc de leur ID de l’appelant entrant** Vous pouvez empêcher un utilisateur de recevoir des ID de l’appelant pour les appels entrants de n’importe quel RTPC.
    
> [!IMPORTANT]
> Les appels d'urgence envoient toujours le numéro de téléphone (ID d'appelant) de l'utilisateur. 
  
Par défaut, chacun de ces paramètres d'ID d'appelant est **désactivé**. Cela signifie que le numéro de téléphone de l'utilisateur de Skype Entreprise Online est visible lorsque l'utilisateur effectue un appel vers un téléphone RTC.
  
Pour en savoir plus sur ces paramètres et leur utilisation, cliquez [Comment utiliser un ID d'appelant dans votre organisation](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Définir vos paramètres de stratégie d'ID d'appelant

> [!NOTE]
> Pour tous les paramètres d’ID de l’appelant dans Skype pour professionnels en ligne, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype pour le centre d’administration commerciale**. 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
1. À partir du **Menu Démarrer**de > **de Windows PowerShell**.
    
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

Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [connexion à Skype pour entreprise en ligne à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Voir l'ensemble des paramètres de stratégie d'ID d'appelant de votre organisation

- Pour afficher tous les paramètres de stratégie de code appelant dans votre organisation, exécutez :

  ```
  Get-CsCallingLineIdentity |fl
  ```
Voir plus de détails et d’exemples de [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Créer une stratégie d'ID d'appelant pour votre organisation

- Pour créer une nouvelle stratégie d’ID de l’appelant qui définit l’ID d’appelant anonyme, exécutez :
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

  Voir plus de détails et d’exemples de [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).
    
- Pour appliquer la nouvelle stratégie que vous avez créé à Amos marbre, exécutez :
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l’applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) pour appliquer les paramètres de vos utilisateurs.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Définir la stratégie de manière à bloquer l'ID d'appelant

- Pour bloquer l’ID de l’appelant entrant, exécutez :
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Voir plus de détails et d’exemples de [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).
    
- Pour appliquer le paramètre de stratégie que vous avez créé à un utilisateur de votre organisation, exécutez :
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    En savoir plus sur l'applet de commande [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
### <a name="remove-a-caller-id-policy"></a>Stratégie de suppression dʼID dʼappelant

Pour supprimer une stratégie de votre organisation, exécutez :
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Pour supprimer une stratégie dʼun utilisateur, exécutez :
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Transfert de questions courantes des numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les Plans d’appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype pour Business Online : étiquette de décharge de responsabilité d’appel d’urgence](https://go.microsoft.com/fwlink/?LinkID=692099)
  

