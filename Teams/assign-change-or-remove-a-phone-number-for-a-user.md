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
description: Découvrez comment attribuer, modifier ou supprimer un numéro de téléphone professionnel pour vos utilisateurs Teams afin que les entreprises et les clients externes puissent appeler.
ms.openlocfilehash: 0dd126f3aa19e0b65b7a0c789f769cef1803f8c8
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414682"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Affectation, modification ou suppression du numéro de téléphone d’un utilisateur

Lorsque vous configurez les forfaits d’appels, Operator Connect ou Teams Phone Mobile, vous attribuez des numéros de téléphone à vos utilisateurs. Dans Microsoft Teams, le numéro de téléphone que vous attribuez est répertorié lorsqu’un utilisateur clique sur **Appels**.

Cet article s’applique aux forfaits d’appels, à Operator Connect et à Teams Phone Mobile. Pour plus d’informations sur l’attribution, la modification ou la suppression d’un numéro de téléphone d’un utilisateur dans un scénario de routage direct, consultez [Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale](./direct-routing-enable-users.md).

Avant d’attribuer un numéro pour un utilisateur de forfait d’appels, de connexion d’opérateur ou de téléphone Mobile Teams, vous devez obtenir des numéros pour vos utilisateurs. Pour plus d’informations, consultez [Obtenir des numéros pour les utilisateurs du forfait d’appels](getting-phone-numbers-for-your-users.md), [Configurer des numéros pour les utilisateurs de connexion d’opérateur](operator-connect-configure.md#set-up-phone-numbers) ou [Configurer des numéros pour les utilisateurs de Téléphone Teams Mobile](operator-connect-mobile-configure.md).

> [!NOTE]
> Une façon de voir si un utilisateur dispose d’une licence est d’aller au centre d’administration Microsoft Teams > **Utilisateurs**. Si une licence est attribuée, elle est indiquée sur la page.  Vous pouvez également utiliser le Centre d'administration Microsoft 365.

> [!NOTE]
> Cette note s’applique aux clients qui ont un déploiement hybride avec un Active Directory local. Si vous souhaitez affecter un numéro de téléphone forfait d’appels ou connexion opérateur à un compte d’utilisateur ou de ressource, vous devez vous assurer que tout numéro de téléphone stocké dans l’attribut msRTCSIP-Line sur l’objet compte d’utilisateur ou de ressource dans le Active Directory local a été supprimé et que la modification a été synchronisée avec Microsoft 365.

## <a name="assign-a-phone-number-to-a-user"></a>Attribuer un numéro de téléphone à un utilisateur

Lorsque vous attribuez un numéro de téléphone à un utilisateur, assurez-vous que le numéro de téléphone et l’emplacement d’utilisation de l’utilisateur sont du même pays.

Pour attribuer un numéro à l’aide du centre d’administration Teams :

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


Pour attribuer des numéros à l’aide de PowerShell, utilisez l’applet de commande [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) comme suit :

Pour les numéros de forfait d’appels :

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Pour les numéros de connexion d’opérateur :

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Pour les numéros Teams Phone Mobile :

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
> En raison de la latence entre Microsoft 365 et Teams, l’activation des utilisateurs peut prendre jusqu’à 24 heures. Si le numéro de téléphone n’est pas attribué correctement après 24 heures, consultez [Phone Number Service Center](https://pstnsd.powerappsportals.com/).

> [!NOTE]
> Lorsque vous attribuez un numéro de téléphone, l’indicateur EnterpriseVoiceEnabled est automatiquement défini sur True.

## <a name="change-a-phone-number-for-a-user"></a>Modifier un numéro de téléphone pour un utilisateur

Pour modifier un numéro de téléphone d’un utilisateur à l’aide du centre d’administration Teams :

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, recherchez et double-cliquez sur l’utilisateur souhaité, cliquez sur **Compte**, puis sous **Informations générales**, notez le numéro de téléphone attribué à l’utilisateur.

2. Dans le volet de navigation de gauche, cliquez sur **Numéros de téléphone vocaux**\>.

3. Dans la page **Numéros de téléphone** , sélectionnez le numéro que vous avez identifié à l’étape 1, puis cliquez sur **Modifier**.

4. Dans le volet **Modifier** , sous **Affecté à**, cliquez sur le **X** pour supprimer l’utilisateur.

5. Cliquez sur **Enregistrer**.

6. Dans la page **Numéros de téléphone** , sélectionnez un numéro non attribué dans la liste, puis cliquez sur **Modifier**.

7. Dans le volet **Modifier** , sous **Affecté à**, recherchez l’utilisateur par nom d’affichage ou nom d’utilisateur, puis cliquez sur **Affecter**.

8. Pour affecter ou modifier l’emplacement d’urgence associé, sous **Emplacement d’urgence**, recherchez et sélectionnez l’emplacement.

      > [!NOTE]
      > Si vous modifiez des numéros pour les utilisateurs De connexion opérateur ou Téléphone mobile Teams, vous pouvez ou non être en mesure d’attribuer ou de modifier l’emplacement d’urgence associé. Cette fonctionnalité dépend de votre opérateur. Pour plus d’informations, contactez votre opérateur.

9. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, consultez [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Supprimer un numéro de téléphone d’un utilisateur

Pour supprimer un numéro de téléphone à l’aide du Centre d’administration Teams :

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, recherchez et double-cliquez sur l’utilisateur souhaité, cliquez sur **Compte**, puis sous **Informations générales**, notez le numéro de téléphone attribué à l’utilisateur.

2. Dans le volet de navigation de gauche, cliquez sur **Numéros de téléphone vocaux**\>.

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
