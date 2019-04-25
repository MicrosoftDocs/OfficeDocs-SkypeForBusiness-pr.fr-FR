---
title: Configuration des téléphones de zone commune
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Découvrez les étapes de déploiement pour obtenir le microprogramme approprié, mettre à jour si nécessaire, attribuer des licences et configurer les paramètres pour les téléphones en zone commune.
ms.openlocfilehash: b92cef4234823c53faf6193d2e9e90fe3e5b60f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231154"
---
# <a name="set-up-common-area-phones"></a>Configuration des téléphones de zone commune
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>Conditions préalables pour les téléphones de la zone commune

La première chose à faire est de confirmer que vous avez :

- acheté une licence de téléphone de zone commune et un Forfait d'appels.
- recherché et acheté des téléphones approuvés (voir la liste [ici](deploying-skype-for-business-online-phones.md)).
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Téléphones Polycom VVX**: accéder aux **paramètres** > **état** > **plateforme** > **Application** > **principal**.
  - **Téléphones Yealink**: accédez à **l’état** sur l’écran du téléphone principal.
  - **Téléphones AudioCodes**: accédez au **Menu** > **État du périphérique** > **version de microprogramme** à partir de l’écran d’accueil.
  - **Téléphones Lync Phone Edition (LPE)**: accédez au **Menu** > **Informations système** à partir de l’écran d’accueil.

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>Configuration d’un téléphone de zone commune
Vous devrez suivre les étapes suivantes :

### <a name="step-1---buy-the-licenses"></a>Étape 1 - Acheter les licences
1. Dans le centre d’administration Office 365, accédez à **Facturation** > **Services d’achats**, et ajouter **D’autres forfaits**.

    ![CAP-license.png](../../images/cap-license.png)
2. Cliquer sur **Téléphone de zone commune** > **Acheter maintenant** > sur la page **Commande** cliquez sur **Acheter maintenant**.
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

Pour plus d’informations sur les licences, consultez la section [Licences complémentaires pour Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences
1. Dans le centre d’administration Office 365, accédez à **Utilisateurs** > **Utilisateurs actifs** > **Ajouter un utilisateur**.
2. Saisissez un **Nom d'utilisateur** comme « Réception » pour le prénom et « Principale » pour le nom.
3. Saisissez un **Nom d’affichage**, s’il n’est pas généré automatiquement, comme « Reception Principale ».
4. Saisissez un **Nom d'utilisateur** comme « RéceptionPrincipale » ou « HallPrincipal ».
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.
6. Si vous êtes toujours là, attribuez les licences à cet utilisateur. Sur la même page, cliquez pour développer **Licences produit**. Activez l’élément suivant :
   - Téléphone de zone commune
   - Ensuite, vous devez choisir soit un **Forfait d’appels nationaux** soit un **Forfait d’appels internationaux** et nationaux.

     L’attribution des licences ressemblera à :

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Juste pour information, Le Forfait Skype Entreprise 2 est inclus avec la licence **Téléphone de zone commune**.

Pour plus de détails, reportez-vous à la section [Ajouter un utilisateur](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Attribution d’un numéro de téléphone à l’utilisateur en utilisant le **Centre d’administration Skype Entreprise**

1. Dans la > de centre d’administration Office 365 **Admin centres** > **Skype pour les entreprises**.
2. Dans le **Centre d’administration Skype Entreprise** >  **Voix** > **Numéros de téléphone**.
3. Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.
4. Sur la page **Attribuer**, dans la zone **Utilisateur vocal**, entrez le nom de l’utilisateur utilisé pour le téléphone, puis sélectionnez l'utilisateur dans la liste déroulante **Sélectionner un utilisateur vocal**.
5. Pendant que vous êtes là, vous devrez ajouter une adresse d’urgence. Une fois la recherche effectuée, regardez sous **Sélectionner l’adresse d’urgence** pour choisir celle qui vous convient.
6. Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Les utilisateurs apparaîtront seulement s’ils possèdent une licence **Système téléphonique**. Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.

Pour plus de détails, reportez-vous à la section [Obtenir des numéros de téléphone pour vos utilisateurs](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Sachez que vous pouvez également prendre le numéro de téléphone que vous avez avec un autre opérateur et le « *Porter* » ou le transférer sur Office 365. Consultez [transfert des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>Étape 4 - Configuration de votre téléphone

**Réglage du mode sur un téléphone**

Le téléphone ou les téléphones que vous avez doivent avoir le **Mode de téléphone de zone commune** activé. Il serait interessant de vous assurer que ce mode soit bien activé.

**Voici un exemple de configuration d’un téléphone Polycom VVX**

- Activez le mode de téléphone de zone commune pour le Polycom VVX en procédant comme suit :
    1. Dans votre navigateur, connectez-vous à l’interface Web pour pouvoir activer le mode TZC.
    2. Ensuite aller sur **Réglage** et dans l’option **Paramètre Skype Entreprise**, sélectionnez **Téléphone de zone commune**.
    3. Cliquez sur **OK** pour enregistrer vos paramètres.

- Maintenant que le mode TZC est activé, configurez le téléphone en utilisant l’affichage du téléphone. L’affichage devrait montrer **TZC est activé**. Faites ensuite ceci :

    1. Cliquez sur **Paramètres**.
    2. Sélectionnez **Avancé**.
    3. Entrez le mot de passe.
    4. Dans **Paramètres d’administration**, sélectionnez **Paramètres du téléphone de zone commune**.
    5. Activer **TZC** et **Mode d’administration TZC**.
    6. Cliquez sur **Enregistrer la configuration**.

- Maintenant votre téléphone est prêt pour que vous puissiez vous connecter à partir de l’écran d’accueil.

    1. Connectez-vous en sélectionnant **Paramètres** > **Fonctionnalités** > **Skype Entreprises.**
    2. Sélectionnez **Informations d’identification de l’utilisateur**et sélectionnez **connexion Web (TZC)** pour générer un code.
    3. Aller sur le [portail de provisionnement](https://aka.ms/skypecap)et connectez-vous en tant qu’**administrateur**.
    4. Entrez le nom d’affichage (par exemple, Réception principale).

       > [!Note]
       > Si **Rechercher des téléphones de zone commune uniquement** est cochée, décochez la case et recommencez la recherche.

    5. Dans la fenêtre du code d'appariement, entrez le code affiché sur le téléphone et cliquez **Configurer**.

        Après cette dernière étape, le téléphone devrait se connecter automatiquement.


> [!NOTE]
> Le site d'attribution de privilèges d'accès CAP indique qu'il réinitialisera le mot de passe du compte CAP à un mot de passe aléatoire. Notez que le compte auquel fait référence le CAP est le compte Azure Active Directory (AAD). Si vous avez créé le compte dans AAD uniquement, le processus est simple. Si vous avez synchronisé un DAS Active Directory local et que vous utilisez un tiers IDP ou ADFS, mise en service du CAP échouera. Dans ce cas, vous devez utiliser un compte Active Directory uniquement (par exemple, un compte avec un domaine **onmicrosoft.com** ) Office 365/Azure pour délimiter mise en service pour fonctionner.


### <a name="related-topics"></a>Voir aussi

- En savoir plus sur les téléphones disponibles sur [Déploiement des téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).
- [Obtention des téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md)


