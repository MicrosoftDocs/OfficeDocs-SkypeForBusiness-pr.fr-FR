---
title: Déplacer les utilisateurs vers Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 'Résumé : Découvrez comment migrer les paramètres utilisateur et de déplacer des utilisateurs vers Skype pour Business Online.'
ms.openlocfilehash: 4c6a54bf5d197e4836c733975b60242c0fd3d431
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Déplacer les utilisateurs vers Skype Entreprise Online
 
**Résumé :** Découvrez comment migrer les paramètres utilisateur et de déplacer des utilisateurs vers Skype pour Business Online.
  
Avant de déplacer l’utilisateur vers Office 365, vous devez d’abord confirmer que les comptes utilisateur sont synchronisés avec le cloud et vous devez lui attribuer une licence. À cet effet, vous devez utiliser le Centre d’administration Office 365.
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>Pour confirmer qu’un compte d’utilisateur local a été synchronisé avec Office 365

1. À l’aide d’un compte d’administrateur client, ouvrez le [Centre d’administration Office 365](https://portal.office.com/) pour votre client.  Comptes d’administrateur client doivent avoir les deux Skype le rôle d’administrateur d’entreprise et le rôle de gestion d’utilisateur (ou le rôle d’administrateur Global) effectuer cette fonction dans Office 365
    
2. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Utilisateurs actifs**.
    
3. Cliquez sur **Rechercher un utilisateur** et tapez le nom de l’utilisateur.
    
4. Vérifiez que l’utilisateur s’affiche et que son statut est **Synchronisé avec Active Directory**.
    
    Si l’utilisateur n’est pas encore synchronisé, la synchronisation automatique doit avoir lieu dans les trois heures. Vous pouvez également forcer une synchronisation plus tôt. Pour plus d’informations, voir [Forcer la synchronisation d’annuaires](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).
    
Pour affecter la licence dans Office 365, voir [l’attribution de licences pour Office 365 pour entreprises](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a>Migration des paramètres utilisateur à Skype pour Business Online

Avant de commencer la migration des utilisateurs vers Skype pour Business Online, vous devez sauvegarder les données utilisateur associées à déplacer. Les données utilisateur ne sont pas toutes déplacées avec le compte d’utilisateur. Pour plus d’informations, voir [besoins de sauvegarde et restauration : données](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).
  
Les paramètres utilisateur sont déplacés en même temps que le compte d’utilisateur. Certains paramètres locaux ne sont pas déplacés avec le compte d’utilisateur.
  
## <a name="move-pilot-users-to-skype-for-business-online"></a>Déplacer des utilisateurs du pilote vers Skype pour Business Online

Avant de commencer à déplacer les utilisateurs vers Skype pour Business Online, vous souhaiterez peut-être déplacer certains utilisateurs du pilote pour vérifier que votre environnement est configuré correctement. Vous pouvez alors vérifier que les fonctionnalités et les services fonctionnent comme prévu avant d’essayer de déplacer d’autres utilisateurs.
  
Pour déplacer un utilisateur local vers votre Skype pour client Business Online, exécutez les cmdlets suivantes dans le Skype pour Business Server Management Shell, en utilisant les informations d’identification d’administrateur pour votre client Microsoft Office 365. Remplacez « nomutilisateur@contoso.com » par les informations de l’utilisateur à déplacer.
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a>Déplacement des utilisateurs vers Skype Entreprise Online

Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) avec le paramètre - Filter pour sélectionner les utilisateurs avec une propriété spécifique affectée aux comptes d’utilisateur, tel que RegistrarPool. Vous pouvez ensuite canaliser renvoyées aux utilisateurs de l’applet de commande [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , comme illustré dans l’exemple suivant.
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

Vous pouvez également utiliser le paramètre - unité d’organisation pour récupérer tous les utilisateurs dans l’unité d’organisation spécifiée, comme illustré dans l’exemple suivant.
  
```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds 
```

## <a name="verify-online-user-settings-and-features"></a>Vérification des paramètres utilisateur et des fonctionnalités en ligne

Vous pouvez vérifier que le déplacement d’un utilisateur a réussi des deux manières suivantes :
  
- Affichez le statut de l’utilisateur dans le Panneau de configuration de Skype Entreprise Online. L’indicateur visuel des utilisateurs locaux et des utilisateurs en ligne est différent.
    
- Exécutez l’applet de commande suivante :
    
  ```
  Get-CsUser -Identity
  ```


