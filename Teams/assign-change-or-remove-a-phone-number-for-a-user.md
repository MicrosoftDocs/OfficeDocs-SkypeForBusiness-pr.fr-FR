---
title: Affectation, modification ou suppression du numéro de téléphone d’un utilisateur
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Découvrez comment attribuer, modifier ou supprimer un numéro de téléphone Teams vos utilisateurs professionnels pour que les entreprises et clients externes peuvent appeler.
ms.openlocfilehash: 6341b6c3242eafad7039b210995ee7c56613442e
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456907"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Affectation, modification ou suppression du numéro de téléphone d’un utilisateur

Lorsque vous définissez des forfaits d’appels ou des Connecter, vous affectez des numéros de téléphone à vos utilisateurs. Dans Microsoft Teams, le numéro de téléphone que vous affectez est répertorié lorsqu’un utilisateur clique sur **Appels**. 

Cet article s’applique aux forfaits d’appels et aux Connecter. Pour plus d’informations sur l’attribution, la modification ou la suppression du numéro de téléphone d’un utilisateur dans un scénario de routage direct, voir Activer le routage direct, la voix et la [messagerie vocale pour les utilisateurs](./direct-routing-enable-users.md).

Avant d’affecter un numéro pour un plan d’appels ou un Connecter un utilisateur, vous devez obtenir des numéros pour vos utilisateurs. Pour plus d’informations, voir Obtenir des numéros pour les utilisateurs [d’un plan](getting-phone-numbers-for-your-users.md) d’appels ou Configurer des numéros pour les utilisateurs [Connecter utilisateurs](operator-connect-configure.md#set-up-phone-numbers).

  
> [!NOTE]
> Pour savoir si une licence a été attribuée à un utilisateur, vous pouvez vous rendre dans le Microsoft Teams centre d’administration > **utilisateurs**. Si une licence est attribuée, elle sera indiquée dans la page.  Vous pouvez également utiliser l’Centre d'administration Microsoft 365.

> [!NOTE]
> Cette remarque s’applique aux clients qui ont un déploiement hybride avec un Active Directory local. Si vous voulez affecter un plan d’appels ou un numéro de téléphone d’opérateur Connecter à un compte d’utilisateur ou de ressource, vous devez vous assurer que tout numéro de téléphone stocké dans l’attribut msRTCSIP-Line sur l’objet compte d’utilisateur ou de ressource dans l’active Directory local a été supprimé, et que la modification a été synchronisée avec Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Affectation d’un numéro de téléphone à un utilisateur

Lors de l’attribution d’un numéro de téléphone à un utilisateur, assurez-vous que le numéro de téléphone et l’emplacement d’utilisation de l’utilisateur sont dans le même pays.

Pour attribuer un numéro à l’aide du Teams d’administration :
    
1. Dans le groupe de navigation de gauche, **cliquez** >  **Téléphone des numéros**.

2. Dans la page **Téléphone numéros** de téléphone, sélectionnez un numéro non modifié dans la liste, puis cliquez sur **Modifier**.  

3. Dans le **volet Édition** , sous **Affecté à**, recherchez l’utilisateur par nom d’affichage ou nom d’utilisateur, puis cliquez sur **Attribuer**.

4. Pour affecter ou modifier l’emplacement d’urgence associé, sous Emplacement d’urgence **,** recherchez et sélectionnez l’emplacement.

   > [!NOTE]
   > Si vous affectez des numéros à l’opérateur Connecter utilisateurs, il est possible que vous ne soyez pas en mesure d’affecter ou de modifier l’emplacement d’urgence associé. Cette fonctionnalité dépend de votre opérateur. Pour plus d’informations, contactez votre opérateur.

5. Selon que vous voulez envoyer un courrier électronique à l’utilisateur avec ses informations de numéro de téléphone, désactiver ou activer l’utilisateur de courrier avec des **informations de numéro de téléphone**. Par défaut, c’est le cas. 

6. Cliquez sur **Enregistrer**.

Pour attribuer des nombres à l’aide de PowerShell, utilisez la cmdlet [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) comme suit :

Pour les numéros de forfait d’appels
```PowerShell
Set-CsPhoneNumberAssignment -Identity <user>  -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Pour les numéros d Connecter opérateur
```PowerShell
Set-CsPhoneNumberAssignment -Identity <user>  -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Par exemple :

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
```

> [!NOTE]
> En raison de la latence entre Microsoft 365 et Teams, l’activé peut prendre jusqu’à 24 heures pour les utilisateurs. Si le numéro de téléphone n’est pas attribué correctement après 24 heures, consultez Téléphone [Centre de services de numéro.](https://pstnsd.powerappsportals.com/) 

  
## <a name="change-a-phone-number-for-a-user"></a>Modifier le numéro de téléphone d’un utilisateur

Pour modifier le numéro de téléphone d’un utilisateur à l’aide du Teams d’administration :
    
1. Dans le groupe de navigation de gauche, cliquez sur Utilisateurs **,** localisez et double-cliquez sur l’utilisateur voulu, cliquez sur **Compte, puis** sous Informations générales **,** notez le numéro de téléphone attribué à l’utilisateur.

2. Dans le groupe de navigation de gauche, **cliquez** >  **Téléphone des numéros**.

3. Dans la page **Téléphone numéros** de téléphone, sélectionnez le numéro identifié à l’étape 1, puis cliquez sur **Modifier**.  

4. Dans le **volet Édition** , sous **Affecté à**, cliquez sur **le X** pour supprimer l’utilisateur.

5. Cliquez sur **Enregistrer**.

6. Dans la page **Téléphone numéros** de téléphone, sélectionnez un numéro non modifié dans la liste, puis cliquez sur **Modifier**.  

7. Dans le **volet Édition** , sous **Affecté à**, recherchez l’utilisateur par nom d’affichage ou nom d’utilisateur, puis cliquez sur **Attribuer**.

8. Pour affecter ou modifier l’emplacement d’urgence associé, sous Emplacement d’urgence **,** recherchez et sélectionnez l’emplacement.

      > [!NOTE]
      > Si vous changez de numéro pour l’opérateur Connecter utilisateurs, il est possible que vous ne soyez pas en mesure d’affecter ou de modifier l’emplacement d’urgence associé. Cette fonctionnalité dépend de votre opérateur. Pour plus d’informations, contactez votre opérateur.

9. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, [voir Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Supprimer le numéro de téléphone d’un utilisateur

Pour supprimer un numéro de téléphone à l’aide du Teams d’administration :

1. Dans le groupe de navigation de gauche, cliquez sur Utilisateurs **,** localisez et double-cliquez sur l’utilisateur voulu, cliquez sur **Compte, puis** sous Informations générales **,** notez le numéro de téléphone attribué à l’utilisateur.

2. Dans le groupe de navigation de gauche, **cliquez** >  **Téléphone des numéros**.

3. Dans la page **Téléphone numéros** de téléphone, sélectionnez le numéro identifié à l’étape 2, puis cliquez sur **Modifier**.  

4. Dans le **volet Édition** , sous **Affecté à**, cliquez sur **le X** pour supprimer l’utilisateur.

5. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, [voir Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>Sujets associés

[Qu’est-ce que la validation d’adresse ?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)

