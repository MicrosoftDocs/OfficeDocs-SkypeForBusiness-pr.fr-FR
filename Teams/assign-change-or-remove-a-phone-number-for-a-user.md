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
description: Découvrez comment affecter, modifier ou supprimer un numéro de téléphone professionnel pour vos utilisateurs Teams afin que les entreprises et les clients externes puissent appeler.
ms.openlocfilehash: d26df14f2f75e205c1824b66c9b8f2f394972d43
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551658"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Affectation, modification ou suppression du numéro de téléphone d’un utilisateur

Lorsque vous configurez des forfaits d’appels, Operator Connect ou Teams Phone Mobile, vous attribuez des numéros de téléphone à vos utilisateurs. Dans Microsoft Teams, le numéro de téléphone que vous attribuez est répertorié lorsqu’un utilisateur clique sur **Appels**.

Cet article s’applique aux forfaits d’appels, à Operator Connect et à Teams Phone Mobile. Pour plus d’informations sur l’attribution, la modification ou la suppression d’un numéro de téléphone d’un utilisateur dans un scénario de routage direct, consultez [Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale](./direct-routing-enable-users.md).

Avant d’attribuer un numéro pour un utilisateur forfait d’appels, Opérateur Connect ou Teams Phone Mobile, vous devez obtenir des numéros pour vos utilisateurs. Pour plus d’informations, consultez [Obtenir des numéros pour les utilisateurs du forfait d’appels](getting-phone-numbers-for-your-users.md), [configurer des numéros pour les utilisateurs d’Opérateur Connect](operator-connect-configure.md#set-up-phone-numbers) ou [configurer des numéros pour les utilisateurs Teams Phone Mobile](operator-connect-mobile-configure.md).

> [!NOTE]
> Une façon de voir si une licence est attribuée à un utilisateur consiste à accéder au Centre d’administration Microsoft Teams > **Utilisateurs**. Si une licence est attribuée, elle est indiquée sur la page.  Vous pouvez également utiliser le Centre d'administration Microsoft 365.

> [!NOTE]
> Cette note s’applique aux clients qui disposent d’un déploiement hybride avec un Active Directory local. Si vous souhaitez affecter un numéro de téléphone Forfait d’appel ou Connexion d’opérateur à un compte d’utilisateur ou de ressource, vous devez vous assurer que tout numéro de téléphone stocké dans l’attribut msRTCSIP-Line sur l’objet de compte d’utilisateur ou de ressource dans le Active Directory local a été supprimé et que la modification a été synchronisée avec Microsoft 365.

## <a name="assign-a-phone-number-to-a-user"></a>Affecter un numéro de téléphone à un utilisateur

Lorsque vous attribuez un numéro de téléphone à un utilisateur, assurez-vous que le numéro de téléphone et l’emplacement d’utilisation de l’utilisateur sont du même pays.

Pour attribuer un nombre à l’aide du Centre d’administration Teams :

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


Pour affecter des nombres à l’aide de PowerShell, utilisez l’applet de commande [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) comme suit :

Pour les numéros de plan d’appel :

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Pour les numéros Operator Connect :

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Pour les numéros de téléphone mobile Teams :

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

Par exemple :

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```







> [!NOTE]
> En raison de la latence entre Microsoft 365 et Teams, l’activation des utilisateurs peut prendre jusqu’à 24 heures. Si le numéro de téléphone n’est pas correctement attribué après 24 heures, consultez [le Centre de services de numéro de téléphone](https://pstnsd.powerappsportals.com/).

## <a name="change-a-phone-number-for-a-user"></a>Modifier un numéro de téléphone pour un utilisateur

Pour modifier un numéro de téléphone pour un utilisateur à l’aide du Centre d’administration Teams :

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, recherchez et double-cliquez sur l’utilisateur souhaité, cliquez sur **Compte**, puis, sous **Informations générales**, notez le numéro de téléphone affecté à l’utilisateur.

2. Dans le volet de navigation de gauche, cliquez sur **Numéros de téléphone** **vocal**\>.

3. Dans la page **Numéros de téléphone** , sélectionnez le numéro que vous avez identifié à l’étape 1, puis cliquez sur **Modifier**.

4. Dans le volet **Modifier** , sous **Affecté à**, cliquez sur le **X** pour supprimer l’utilisateur.

5. Cliquez sur **Enregistrer**.

6. Dans la page **Numéros de téléphone** , sélectionnez un numéro non attribué dans la liste, puis cliquez sur **Modifier**.

7. Dans le volet **Modifier** , sous **Affecté à**, recherchez l’utilisateur par nom d’affichage ou nom d’utilisateur, puis cliquez sur **Affecter**.

8. Pour affecter ou modifier l’emplacement d’urgence associé, sous **Emplacement d’urgence**, recherchez et sélectionnez l’emplacement.

      > [!NOTE]
      > Si vous modifiez des numéros pour les utilisateurs d’Opérateur Connect ou teams Phone Mobile, vous pouvez ou non être en mesure d’affecter ou de modifier l’emplacement d’urgence associé. Cette fonctionnalité dépend de votre opérateur. Pour plus d’informations, contactez votre opérateur.

9. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, consultez [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Supprimer un numéro de téléphone d’un utilisateur

Pour supprimer un numéro de téléphone à l’aide du Centre d’administration Teams :

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, recherchez et double-cliquez sur l’utilisateur souhaité, cliquez sur **Compte**, puis, sous **Informations générales**, notez le numéro de téléphone affecté à l’utilisateur.

2. Dans le volet de navigation de gauche, cliquez sur **Numéros de téléphone** **vocal**\>.

3. Dans la page **Numéros de téléphone** , sélectionnez le numéro que vous avez identifié à l’étape 2, puis cliquez sur **Modifier**.

4. Dans le volet **Modifier** , sous **Affecté à**, cliquez sur le **X** pour supprimer l’utilisateur.

5. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, consultez [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>Rubriques connexes

[Qu’est-ce que la validation d’adresse ?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
