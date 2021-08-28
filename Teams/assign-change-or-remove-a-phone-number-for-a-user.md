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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Découvrez comment attribuer, modifier ou supprimer un numéro de téléphone privé pour vos utilisateurs Teams entreprise et clients externes.
ms.openlocfilehash: 938377f200d31ddaef2338f5c21811150571732e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595222"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Affectation, modification ou suppression du numéro de téléphone d’un utilisateur (forfaits d’appels)

Lorsque vous définissez des forfaits d’appels, vous affectez des numéros de téléphone à vos utilisateurs. Dans Microsoft Teams, le numéro de téléphone que vous affectez est répertorié lorsqu’un utilisateur clique sur **Appels.** Pour obtenir des instructions sur l’attribution, la modification ou la suppression du numéro de téléphone d’un utilisateur dans un scénario de routage direct, voir Activer le [routage direct,](./direct-routing-enable-users.md)la voix et la messagerie vocale pour les utilisateurs.

![Numéro de téléphone de l’utilisateur affiché dans Teams.](media/teams-phone-number.png)

Lorsque vous souhaitez que les utilisateurs peuvent effectuer et recevoir des appels téléphoniques, vous devez tout d’abord utiliser le Centre d’administration Microsoft Teams et attribuer un numéro de téléphone. Vous pouvez modifier ou supprimer le numéro de téléphone si nécessaire.
  
Pour savoir comment obtenir des forfaits d’appels Teams prix, consultez Teams [de licences de module supplémentaire.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
> [!NOTE]
> Pour savoir si une licence a été attribuée à un utilisateur, vous pouvez vous rendre dans le Centre d’administration Microsoft Teams d'> **utilisateurs.** Si une licence est attribuée, elle sera indiquée dans la page.  Vous pouvez également utiliser l’Centre d’administration Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Affectation d’un numéro de téléphone à un utilisateur
 
![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**
    
1. Dans le navigateur de gauche, cliquez **sur Numéros**  >  **Téléphone.**
2. Dans la page **Téléphone numéros** de téléphone, sélectionnez un numéro non modifié dans la liste, puis cliquez sur **Modifier.**  
3. Dans le **volet Édition,** sous **Affecté à,** recherchez l’utilisateur par nom d’affichage ou nom d’utilisateur, puis cliquez sur **Attribuer.**
4. Pour attribuer ou modifier l’emplacement d’urgence associé, sous Emplacement d’urgence, recherchez et sélectionnez l’emplacement.
5. Selon que vous voulez envoyer un courrier électronique à l’utilisateur avec ses informations de numéro de téléphone, désactiver ou activer l’utilisateur de courrier avec des **informations de numéro de téléphone.** Par défaut, c’est le cas. 
6. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, [voir Set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser)

> [!NOTE]
> En raison de la latence entre Microsoft 365 ou Office 365 et Teams, l’activé peut prendre jusqu’à 24 heures pour les utilisateurs. Si le numéro de téléphone n’est pas attribué correctement après 24 heures, contactez le support technique pour les produits pour les entreprises [- Aide de l’administrateur.](/microsoft-365/admin/contact-support-for-business-products) Nous sommes là pour vous aider !

  
## <a name="change-a-phone-number-for-a-user"></a>Modifier le numéro de téléphone d’un utilisateur
 
![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**
    
1. Dans la barre de navigation de gauche, cliquez sur Utilisateurs, localisez et double-cliquez sur l’utilisateur voulu, cliquez sur **Compte,** puis sous Informations générales, notez le numéro de téléphone attribué à l’utilisateur.
2. Dans le navigateur de gauche, cliquez **sur Numéros**  >  **Téléphone.**
3. Dans la page **Téléphone numéros** de téléphone, sélectionnez le numéro identifié à l’étape 1, puis cliquez sur **Modifier.**  
4. Dans le **volet Édition,** sous **Affecté à,** cliquez sur **le X** pour supprimer l’utilisateur.
5. Cliquez sur **Enregistrer**.
6. Dans la page **Téléphone numéros** de téléphone, sélectionnez un numéro non modifié dans la liste, puis cliquez sur **Modifier.**  
7. Dans le **volet Édition,** sous **Affecté à,** recherchez l’utilisateur par nom d’affichage ou nom d’utilisateur, puis cliquez sur **Attribuer.**
8. Pour attribuer ou modifier l’emplacement d’urgence associé, sous Emplacement d’urgence, recherchez et sélectionnez l’emplacement.
9. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, voir [Set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser)

## <a name="remove-a-phone-number-from-a-user"></a>Supprimer le numéro de téléphone d’un utilisateur
 
![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, cliquez sur Utilisateurs, localisez et double-cliquez sur l’utilisateur voulu, cliquez sur **Compte,** puis sous Informations générales, notez le numéro de téléphone attribué à l’utilisateur.
2. Dans le navigateur de gauche, cliquez **sur Numéros**  >  **Téléphone.**
3. Dans la page **Téléphone numéros** de téléphone, sélectionnez le numéro identifié à l’étape 2, puis cliquez sur **Modifier.**  
4. Dans le **volet Édition,** sous **Affecté à,** cliquez sur **le X** pour supprimer l’utilisateur.
5. Cliquez sur **Enregistrer**.

Pour obtenir un exemple PowerShell, voir [Set-CsOnlineVoiceUser.](/powershell/module/skype/set-csonlinevoiceuser)

## <a name="related-topics"></a>Rubriques connexes

[Qu’est-ce que la validation d’adresse ?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Étiquette d’exclusion de responsabilité d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)

[Forfaits d’appels Microsoft 365](./calling-plans-for-office-365.md)
