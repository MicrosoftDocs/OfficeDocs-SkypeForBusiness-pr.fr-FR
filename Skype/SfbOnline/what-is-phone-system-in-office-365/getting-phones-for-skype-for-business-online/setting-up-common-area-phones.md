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
ms.openlocfilehash: 3faa66235f3c3364a0da6560a6dc52daa252915b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370674"
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

    > [!Tip]
    > WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.

6. If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:
   - Téléphone de zone commune
   - Ensuite, vous devez choisir soit un **Forfait d’appels nationaux** soit un **Forfait d’appels internationaux** et nationaux.

     L’attribution des licences ressemblera à :

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Juste pour information, Le Forfait Skype Entreprise 2 est inclus avec la licence **Téléphone de zone commune**.

Pour plus de détails, reportez-vous à la section [Ajouter un utilisateur](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Attribution d’un numéro de téléphone à l’utilisateur en utilisant le **Centre d’administration Skype Entreprise**

1. Dans le centre d’administration Office 365 > **centres d’administration** > **Skype pour les entreprises**.
2. Dans le **Centre d’administration Skype Entreprise** >  **Voix** > **Numéros de téléphone**.
3. Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.
4. Sur la page **Attribuer**, dans la zone **Utilisateur vocal**, entrez le nom de l’utilisateur utilisé pour le téléphone, puis sélectionnez l'utilisateur dans la liste déroulante **Sélectionner un utilisateur vocal**.
5. While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.
6. Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.

Pour plus de détails, reportez-vous à la section [Obtenir des numéros de téléphone pour vos utilisateurs](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>Étape 4 - Configuration de votre téléphone

**Réglage du mode sur un téléphone**

The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.

**Voici un exemple de configuration d’un téléphone Polycom VVX**

- Activez le mode de téléphone de zone commune pour le Polycom VVX en procédant comme suit :
    1. Dans votre navigateur, connectez-vous à l’interface Web pour pouvoir activer le mode TZC.
    2. Ensuite aller sur **Réglage** et dans l’option **Paramètre Skype Entreprise**, sélectionnez **Téléphone de zone commune**.
    3. Cliquez sur **OK** pour enregistrer vos paramètres.

- Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:

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
> The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.


### <a name="related-topics"></a>Rubriques connexes

- En savoir plus sur les téléphones disponibles sur [Déploiement des téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).
- [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md)


