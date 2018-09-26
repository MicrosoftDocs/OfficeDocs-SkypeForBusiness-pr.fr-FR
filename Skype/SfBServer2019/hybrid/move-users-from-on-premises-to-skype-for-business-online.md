---
title: Déplacer les utilisateurs vers Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Résumé : Découvrez comment migrer les paramètres utilisateur et de déplacer des utilisateurs vers Skype pour Business Online.'
ms.openlocfilehash: 9fd51c55be35e55be6ca837ccb72413043283ac7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030748"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Déplacer les utilisateurs vers Skype Entreprise Online

**Résumé :** Découvrez comment migrer les paramètres utilisateur et de déplacer des utilisateurs vers Skype pour Business Online.

Avant de déplacer réellement un utilisateur vers Office 365, vous devez tout d’abord vérifier que les comptes d’utilisateur sont synchronisées avec le nuage et leur attribuer une licence. À cet effet, vous devez utiliser le Centre d’administration Office 365.

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>Pour confirmer qu’un compte d’utilisateur local a été synchronisé avec Office 365

1. À l’aide d’un compte d’administrateur de client, ouvrez le centre d’administration Office 365 pour votre client.  Comptes d’administrateur client doivent être accordés à la fois le Skype pour le rôle d’administrateur d’entreprise et le rôle de gestion d’utilisateur (ou le rôle d’administrateur Global) effectuer cette fonction dans Office 365.

2. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis cliquez sur **Utilisateurs actifs**.

3. Cliquez sur **Rechercher un utilisateur** et tapez le nom de l’utilisateur.

4. Vérifiez que vous voyez l’utilisateur et que leur statut est **Synched avec Active Directory**.

    Si l’utilisateur n’est pas encore synchronisé, la synchronisation automatique doit avoir lieu dans les trois heures. Vous pouvez également forcer une synchronisation plus tôt. Pour plus d’informations, voir [Forcer la synchronisation d’annuaires](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).

Pour affecter la licence dans Office 365, voir [attribuer des licences aux utilisateurs dans Office 365 pour entreprises](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="migrate-user-settings-to-skype-for-business-online"></a>Migration des paramètres utilisateur à Skype pour Business Online

Avant de migrer les utilisateurs vers Skype pour Business Online, vous devez sauvegarder les données utilisateur associées à déplacer. Les données utilisateur ne sont pas toutes déplacées avec le compte d’utilisateur. Pour plus d’informations, voir [besoins de sauvegarde et restauration : données](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).

Les paramètres utilisateur sont déplacés en même temps que le compte d’utilisateur. Certains paramètres locaux ne sont pas déplacés avec le compte d’utilisateur.

## <a name="move-pilot-users-to-skype-for-business-online"></a>Déplacer des utilisateurs du pilote vers Skype pour Business Online

Avant de déplacer les utilisateurs vers Skype pour Business Online, vous souhaiterez peut-être déplacer certains utilisateurs du pilote pour vérifier que votre environnement est configuré correctement. Vous pouvez alors vérifier que les fonctionnalités et les services fonctionnent comme prévu avant d’essayer de déplacer d’autres utilisateurs.

Pour déplacer un utilisateur local vers votre Skype pour client Business Online, exécutez les cmdlets suivantes dans le Skype pour Business Server Management Shell, en utilisant les informations d’identification d’administrateur pour votre client Microsoft Office 365. Remplacez « username@contoso.com » avec les informations de l’utilisateur que vous souhaitez déplacer.

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a>Déplacement des utilisateurs vers Skype Entreprise Online

Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) avec le paramètre - Filter pour sélectionner les utilisateurs avec une propriété spécifique affectée aux comptes d’utilisateur, tel que RegistrarPool. Vous pouvez ensuite canaliser renvoyées aux utilisateurs de l’applet de commande [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , comme illustré dans l’exemple suivant :

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

Vous pouvez également utiliser le paramètre - unité d’organisation pour récupérer tous les utilisateurs dans l’unité d’organisation spécifiée, comme illustré dans l’exemple suivant :

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


