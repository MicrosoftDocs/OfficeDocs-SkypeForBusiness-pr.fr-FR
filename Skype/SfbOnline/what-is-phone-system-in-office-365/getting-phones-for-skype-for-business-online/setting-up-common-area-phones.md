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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Découvrez les étapes de déploiement pour obtenir le microprogramme correct, le mettre à jour si nécessaire, attribuer des licences et configurer les paramètres des téléphones de zone commune.
ms.openlocfilehash: cbf1c5f211eba09ee90a0358b175332fa64de4e2
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726973"
---
# <a name="set-up-common-area-phones"></a>Configuration des téléphones de zone commune

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]
Un téléphone de zone commune (TZC) est généralement placé dans une zone comme un hall ou toute autre zone accessible à beaucoup de personnes. Les TZC, comme par exemple, un téléphone de zone de réception, un interphone ou un téléphone de salle de réunion, sont configurés comme des dispositifs plutôt que comme des utilisateurs et se connectent automatiquement à un réseau. Dans les étapes ci-dessous, nous vous aiderons à configurer un compte pour le Système téléphonique avec des Forfaits d'appels pour que vous puissiez déployer ces types de téléphones dans votre organisation.

## <a name="prerequisites-for-common-area-phones"></a>Conditions préalables pour les téléphones de la zone commune

La première chose à faire est de confirmer que vous avez :

- acheté une licence de téléphone de zone commune et un Forfait d'appels.
- recherché et acheté des téléphones approuvés (voir la liste [ici](deploying-skype-for-business-online-phones.md)).
- mis à jour le microprogramme de vos téléphones (voir les microprogrammes pris en charge [dans ce sujet](getting-phones-for-skype-for-business-online.md)).  Vous pouvez vérifier le microprogramme de votre téléphone de cette manière :
  - **Téléphones Polycom VVX**: allez sur le **Paramètres** application principale de la plateforme  >    >    >    >  **d’état.**
  - **Téléphones Yealink :** accès au **statut** sur l’écran principal du téléphone.
  - **Téléphones AudioCodes :** allez à la version du microprogramme **de** l’état du périphérique  >    >  **du menu** à partir de l’écran d’accueil.
  - **Téléphones Lync Téléphone (LPE)**: Aller à la System Information **menu** à partir de  >   l’écran d’accueil.

    Les mises à jour de microprogramme sont gérées par le service Skype Entreprise. Chaque microprogramme de téléphone certifié Skype Entreprise est chargé vers le serveur de mise à jour Skype Entreprise et la mise à jour de l'appareil est activée par défaut sur tous les téléphones.

    En fonction de la durée d'inactivité et des intervalles d'interrogation, les téléphones téléchargeront automatiquement les dernières versions certifiées. Vous pouvez désactiver les paramètres de mise à jour de l’appareil à l’aide de l’cmdlet  [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) et en activant le paramètre *EnableDeviceUpdate* `false` sur.

## <a name="setting-up-a-common-area-phone"></a>Configuration d’un téléphone de zone commune
Vous devrez suivre les étapes suivantes :

### <a name="step-1---buy-the-licenses"></a>Étape 1 - Acheter les licences
1. Dans le Centre d’administration, allez aux   >  **services d’achat de** facturation et ajoutez **d’autres plans.**

    ![Capture d’écran de la zone Téléphone licence.](../../images/cap-license.png)
2. Cliquer sur **Téléphone de zone commune** > **Acheter maintenant** > sur la page **Commande** cliquez sur **Acheter maintenant**.
3. Cliquez pour développer **Abonnements supplémentaires** puis cliquez pour acheter un Forfait d’appels. Sélectionnez le **plan Appels nationaux ou** le plan Appels **nationaux et internationaux.**

> [!Note]
> Vous n’avez pas besoin d’une licence de Système téléphonique. Il est inclus dans la licence **Téléphone de zone commune**.

Pour plus d’informations sur les licences, consultez la section [Licences complémentaires pour Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences
1. Dans le Centre d’administration, voir **Utilisateurs**  >  **actifs Ajouter** un  >  **utilisateur.**
2. Saisissez un **Nom d'utilisateur** comme « Réception » pour le prénom et « Principale » pour le nom.
3. Saisissez un **Nom d’affichage**, s’il n’est pas généré automatiquement, comme « Reception Principale ».
4. Saisissez un **Nom d'utilisateur** comme « RéceptionPrincipale » ou « HallPrincipal ».
5. Pour les téléphones de zone commune, vous pouvez définir manuellement un mot de passe ou avoir le même mot de passe pour tous les téléphones de zone commune. Vous pouvez aussi désélectionner **Faire en sorte que cet utilisateur change son mot de passe lors de sa première connexion**.
6. Si vous êtes toujours là, attribuez les licences à cet utilisateur. Sur la même page, cliquez pour développer **Licences produit**. Activez l’élément suivant :
   - Téléphone de zone commune
   - Ensuite, vous devez choisir soit un **Forfait d’appels nationaux** soit un **Forfait d’appels internationaux** et nationaux.

     L’attribution des licences ressemblera à :

     ![TurnOnCapLicense.png.](../../images/cap-license-turn-on.png)

     > [!Note]
     > Juste pour information, Le Forfait Skype Entreprise 2 est inclus avec la licence **Téléphone de zone commune**.

Pour plus de détails, reportez-vous à la section [Ajouter un utilisateur](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune

![Icône représentant le logo Skype Entreprise’affichage.](../../images/sfb-logo-30x30.png) Attribuer un numéro de téléphone à l’utilisateur à l’aide du **Centre Skype Entreprise’administration**

1. Dans le Centre d’administration > **centres d’administration**  >  **Skype Entreprise.**
2. Dans le **Centre d’administration Skype Entreprise** >  **Voix** > **Numéros de téléphone**.
3. Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.
4. Sur la page **Attribuer**, dans la zone **Utilisateur vocal**, entrez le nom de l’utilisateur utilisé pour le téléphone, puis sélectionnez l'utilisateur dans la liste déroulante **Sélectionner un utilisateur vocal**.
5. Pendant que vous êtes là, vous devrez ajouter une adresse d’urgence. Une fois la recherche effectuée, regardez sous **Sélectionner l’adresse d’urgence** pour choisir celle qui vous convient.
6. Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :

    ![Capture d’écran du numéro de téléphone de l’utilisateur.](../../images/cap-user-number.png)

   > [!Note]
   > Les utilisateurs apparaîtront seulement s’ils possèdent une licence **Système téléphonique**. Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.

Pour plus de détails, reportez-vous à la section [Obtenir des numéros de téléphone pour vos utilisateurs](/microsoftteams/getting-phone-numbers-for-your-users).

Si vous vous demandez, vous pouvez également prendre votre numéro de téléphone avec un autre opérateur et le «*port*» ou le transférer vers Microsoft 365 ou Office 365. Consultez, [Transférer des numéros de téléphone vers Teams.](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

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
    2. Sélectionnez **Avancé.**
    3. Entrez le mot de passe.
    4. Dans **Paramètres d’administration**, sélectionnez **Paramètres du téléphone de zone commune**.
    5. Activer **TZC** et **Mode d’administration TZC**.
    6. Cliquez sur **Enregistrer la configuration**.

- Maintenant votre téléphone est prêt pour que vous puissiez vous connecter à partir de l’écran d’accueil.

    1. Connectez-vous en sélectionnant **Paramètres** > **Fonctionnalités** > **Skype Entreprises.**
    2. Sélectionnez **Informations d’identification de l’utilisateur** et sélectionnez **connexion Web (TZC)** pour générer un code.
    3. Aller sur le [portail de provisionnement](https://aka.ms/skypecap)et connectez-vous en tant qu’**administrateur**.
    4. Entrez le nom d’affichage (par exemple, Réception principale).

       > [!Note]
       > Si **Rechercher des téléphones de zone commune uniquement** est cochée, décochez la case et recommencez la recherche.

    5. Dans la fenêtre du code d'appariement, entrez le code affiché sur le téléphone et cliquez **Configurer**.

        Après cette dernière étape, le téléphone devrait se connecter automatiquement.


> [!NOTE]
> Le site d'attribution de privilèges d'accès CAP indique qu'il réinitialisera le mot de passe du compte CAP à un mot de passe aléatoire. Notez que le compte auquel fait référence le CAP est le compte Azure Active Directory (AAD). Si vous avez créé le compte dans AAD uniquement, le processus est simple. Si vous avez synchronisé une annuaire Active Directory local avec AAD et que vous utilisez un IDP ou ADFS tiers, la mise en service cap échoue. Dans ce cas, vous devez utiliser un compte Microsoft 365 ou Office 365/Azure Active Directory uniquement (par exemple, un compte avec un domaine **onmicrosoft.com)** pour que l’approvisionnement en CAP fonctionne.


### <a name="related-topics"></a>Sujets associés

- En savoir plus sur les téléphones disponibles sur [Déploiement des téléphones Skype Entreprise Online](deploying-skype-for-business-online-phones.md).
- [Obtention des téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md)
