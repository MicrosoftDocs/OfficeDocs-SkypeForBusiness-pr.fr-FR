---
title: Affectation, modification ou suppression du numéro de téléphone d’un utilisateur
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Découvrez comment attribuer, modifier ou supprimer un numéro de téléphone pour les utilisateurs de Teams afin que les entreprises et clients externes peuvent appeler.
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589618"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Affectation, modification ou suppression du numéro de téléphone d’un utilisateur (forfaits d’appels)

Lorsque vous définissez des forfaits d’appels, vous affectez des numéros de téléphone à vos utilisateurs. Dans Microsoft Teams, le numéro de téléphone que vous affectez est répertorié lorsqu’un utilisateur clique sur **Appels.** Pour obtenir des instructions sur l’attribution, la modification ou la suppression du numéro de téléphone d’un utilisateur dans un scénario de routage direct, voir Activer le [routage direct,](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)la voix et la messagerie vocale des utilisateurs.

![Numéro de téléphone de l’utilisateur affiché dans Teams.](media/teams-phone-number.png)

Lorsque vous souhaitez que les utilisateurs peuvent effectuer et recevoir des appels téléphoniques, vous devez tout d’abord utiliser le Centre d’administration De Microsoft Teams et attribuer un numéro de téléphone. Vous pouvez modifier ou supprimer le numéro de téléphone si nécessaire.
  
Pour découvrir comment obtenir des forfaits d’appels dans Teams et leur prix, consultez la gestion [des licences de module supplémentaire Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
> [!NOTE]
> Pour savoir si une licence a été attribuée à un utilisateur, vous pouvez vous rendre dans le Centre d’administration Microsoft Teams > **utilisateurs.** Si une licence est attribuée, elle sera indiquée dans la page.  Vous pouvez également utiliser le Centre d’administration Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Affectation d’un numéro de téléphone à un utilisateur
 
![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**
    
1. Dans le groupe de navigation de gauche, cliquez **sur Numéros** de  >  **téléphone vocal.**
2. Dans la page **Numéros de** téléphone, sélectionnez un numéro non engagé dans la liste, puis cliquez sur **Modifier.**  
3. Dans le **volet Modifier,** sous **Affecté à,** recherchez l’utilisateur par nom d’affichage ou nom d’utilisateur, puis cliquez sur **Attribuer.**
4. Pour attribuer ou modifier l’emplacement d’urgence associé, sous Emplacement d’urgence, recherchez et sélectionnez l’emplacement.
5. Selon que vous voulez envoyer un courrier électronique à l’utilisateur avec ses informations de numéro de téléphone, désactiver ou activer l’utilisateur de courrier avec des **informations de numéro de téléphone.** Par défaut, c’est le cas. 
6. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, [voir Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Modifier le numéro de téléphone d’un utilisateur
 
![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**
    
1. Dans le groupe de navigation de gauche, cliquez sur Utilisateurs, localisez et double-cliquez sur l’utilisateur voulu, cliquez sur **Compte,** puis sous Informations générales, notez le numéro de téléphone attribué à l’utilisateur.
2. Dans le groupe de navigation de gauche, cliquez **sur Numéros** de  >  **téléphone vocal.**
3. Dans la page **Numéros de** téléphone, sélectionnez le numéro identifié à l’étape 1, puis cliquez sur **Modifier.**  
4. Dans le **volet Édition,** sous **Affecté à,** cliquez sur **le X** pour supprimer l’utilisateur.
5. Cliquez sur **Enregistrer**.
6. Dans la page **Numéros de** téléphone, sélectionnez un numéro non engagé dans la liste, puis cliquez sur **Modifier.**  
7. Dans le **volet Modifier,** sous **Affecté à,** recherchez l’utilisateur par nom d’affichage ou nom d’utilisateur, puis cliquez sur **Attribuer.**
8. Pour attribuer ou modifier l’emplacement d’urgence associé, sous Emplacement d’urgence, recherchez et sélectionnez l’emplacement.
9. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, voir [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="remove-a-phone-number-from-a-user"></a>Supprimer le numéro de téléphone d’un utilisateur
 
![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le groupe de navigation de gauche, cliquez sur Utilisateurs, localisez et double-cliquez sur l’utilisateur voulu, cliquez sur **Compte,** puis sous Informations générales, notez le numéro de téléphone attribué à l’utilisateur.
2. Dans le groupe de navigation de gauche, cliquez **sur Numéros** de  >  **téléphone vocal.**
3. Dans la page **Numéros de** téléphone, sélectionnez le numéro identifié à l’étape 2, puis cliquez sur **Modifier.**  
4. Dans le **volet Édition,** sous **Affecté à,** cliquez sur **le X** pour supprimer l’utilisateur.
5. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, voir [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="related-topics"></a>Sujets associés

[Qu’est-ce que la validation d’adresse ?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Étiquette d’exclusion de responsabilité pour les appels d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Forfaits d’appels pour Microsoft 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
