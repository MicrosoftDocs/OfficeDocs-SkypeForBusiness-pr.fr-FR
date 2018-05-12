---
title: Configurer des téléphones de partie commune
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a>Configurer des téléphones de partie commune
Un téléphone en zone commune (CAP) est généralement placé dans une zone comme une salle d’attente ou une autre zone qui est disponible pour un grand nombre de personnes. Par exemple, un téléphone en zone réception, salle de réunion ou de téléphone porte le téléphone majuscules sont configurés en tant que périphériques plutôt que les utilisateurs et établir automatiquement une connexion à un réseau. Dans les étapes suivantes, nous allons vous aider à configurer un compte de système téléphonique avec des Plans de l’appel afin que vous pouvez déployer ces types de téléphones pour votre organisation.

## <a name="prerequisites-for-common-area-phones"></a>Conditions requises pour les téléphones de partie commune

La première chose à faire consiste à vérifier que vous disposez des éléments suivants :

 - Acheter des licences téléphone en zone commune et un Plan d’appel.
 - Rechercher et téléphones approuvé (afficher la liste [ici](deploying-skype-for-business-online-phones.md)).         
 - Mettre à jour du microprogramme de vos téléphones (voir prise en charge du microprogramme [dans cette rubrique](getting-phones-for-skype-for-business-online.md).  Vous pouvez vérifier le microprogramme sur le téléphone vous en procédant ainsi :       
    - **Téléphones Polycom VVX**: accéder aux **paramètres** > **état** > **plateforme** > **Application** > **principal**.
    - **Téléphones Yealink**: accédez à **l’état** sur l’écran du téléphone principal.
    - **Téléphones AudioCodes**: accédez au **Menu** > **État du périphérique** > **version de microprogramme** à partir de l’écran d’accueil. 
    - **Téléphones Lync Phone Edition (LPE)**: accédez au **Menu** > **Informations système** à partir de l’écran d’accueil.

    Les mises à jour de microprogramme sont gérées par le service Skype Entreprise. Chaque microprogramme de téléphone certifié Skype Entreprise est chargé vers le serveur de mise à jour Skype Entreprise et la mise à jour de l'appareil est activée par défaut sur tous les téléphones. 

    En fonction de la durée d'inactivité et des intervalles d'interrogation, les téléphones téléchargeront automatiquement les dernières versions certifiées. Vous pouvez désactiver les paramètres de mise à jour des périphériques à l’aide de l’applet de commande [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) et au paramètre *EnableDeviceUpdate* `false`.

## <a name="setting-up-a-common-area-phone"></a>Configuration d’un téléphone en zone commune
Vous devez procéder comme suit :

### <a name="set-up-your-user-account-for-the-phone"></a>Configurer votre compte d’utilisateur pour le téléphone

#### <a name="step-1---buy-the-licenses"></a>Étape 1 : acheter les licences
1. Dans le centre d’administration Office 365, accédez à la **facturation** > **services d’achat**, et ajouter **d’autres plans**.

    ![CAP-license.png](../../images/cap-license.png)
2. Cliquez sur **Téléphone en zone commune** > **acheter** > sur la page **Checkout** , cliquez sur **Acheter maintenant**.
3. Cliquez sur pour les **abonnements de module complémentaire** , puis cliquez sur acheter un Plan de l’appel. Choisissez **l’intérieur de l’appel de Plan** ou **appel nationale et International planifier**.

> [!Note]
> Vous n’avez pas besoin une licence de système téléphonique. Il est inclus avec la licence de **Téléphone en zone commune** .

Pour plus d’informations sur les licences, voir [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Étape 2 : créer un nouveau compte d’utilisateur pour le téléphone et attribuer les licences
1. Dans le centre d’administration Office 365, accédez aux **utilisateurs** > **Utilisateurs actifs** > **Ajouter un utilisateur**.
2. Placez dans un **nom d’utilisateur** comme « Main » pour le prénom et le « Réception » pour le nom du deuxième.
3. Placez dans un **nom d’affichage** si elle n’est pas générer automatiquement comme « Réception principal ».
4. Placez dans un **nom d’utilisateur** , tel que « MainReception » ou « Mainlobby ».
5. Pour les téléphones de partie commune, vous souhaitez définir un mot de passe manuellement ou ont le même mot de passe pour tous les téléphones de partie commune. En outre, pensez à désélection **faire de cet utilisateur de modifier leur mot de passe lorsqu’ils se connectent tout d’abord**.

    > [!Tip]
    > ATTENDEZ ! Ne cliquez sur **Ajouter**. Euh, si vous n’avez cliqué sur **Ajouter** ne ceci : centre d’administration Office 365 > **utilisateurs** > **utilisateurs** et Active puis rechercher l’utilisateur. Cliquez sur page de propriétés de l’utilisateur, **les licences de produit** , puis sur **Modifier**. Dans la page **licences de produits** , activez le **Téléphone en zone commune** et choisir soit un **Intérieur appelant planifier** ou une national et **International appelant planifier**.

6. Si vous êtes toujours là, attribuer les licences à cet utilisateur. Sur la même page, cliquez pour développer des **licences de produits**. Activer les éléments suivants :
    - Téléphone de partie commune
    - Vous devez choisir soit un **Intérieur appelant planifier** ou une national et **International appelant planifier**.
     
    Attribution de licences ressemblera à :

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > Ça, Skype pour Business Plan 2 est inclus dans la licence de **Téléphone en zone commune** .

Pour plus d’informations, voir [Ajouter un utilisateur](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

#### <a name="step-3---assign-a-phone-number-to-the-user"></a>Étape 3 : attribuer un numéro de téléphone à l’utilisateur
![SFB-logo-30x30.png](../../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
1. Dans le centre d’administration Office 365 > **centres d’administration** > **Skype pour les entreprises**.
2. Dans la **Skype pour le centre d’administration Business** >  **vocale** > **numéros de téléphone**.
3. Sélectionnez un numéro dans la liste des numéros de téléphone, cliquez sur **affecter**.
4. Dans la page **affecter** , dans la zone **utilisateur vocale** , entrez le nom de l’utilisateur qui est utilisé pour le téléphone puis sélectionnez l’utilisateur dans **Sélectionner un utilisateur vocal** de liste déroulante. 
5. Lorsque vous y êtes, vous devez ajouter une adresse d’urgence. Une fois que vous recherchez, examinez le **Sélectionnez adresse en cas d’urgence** à choisir celle de droite pour vous.
6. Cliquez sur **Enregistrer** et l’utilisateur doit se présenter comme suit :

    ![Cap-utilisateur-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Les utilisateurs seront affichent uniquement s’ils disposent d’une licence de **Système téléphonique** appliquée. Si vous avez effectué uniquement cette, puis parfois nécessaire un peu de l’utilisateur s’affiche dans la liste.

Pour d’autres objets, voir [mise en route des numéros de téléphone pour vos utilisateurs](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Si vous vous demandez, vous pouvez également tirer votre numéro de téléphone que vous avez avec un autre transporteur et «*port*» ou leur transfert sur vers Office 365. Consultez [transfert des numéros de téléphone vers Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

## <a name="step-4---setting-up-your-phone"></a>Étape 4 : configuration de votre téléphone

**Définir le mode sur un téléphone**

Le téléphone ou des téléphones que vous avez doivent avoir le mode de téléphone en zone commune activé. Vous voudrez peut-être vérifier que pour vous assurer de que leur. 

**Voici un exemple expliquant comment configurer un téléphone Polycom VVX**

- Activer le mode de téléphone en zone commune pour le VVX Polycom en suivant ces étapes :
    1. Dans votre navigateur, connectez-vous à l’interface web afin que vous pouvez activer le mode de point d’accès client.
    2. Accédez au **paramètre** et dans l’option **Skype pour la configuration d’entreprise** , sélectionnez **Téléphone en zone commune**.
    3. Cliquez sur **Oui** pour enregistrer vos paramètres.

- Maintenant que le mode de cache est activé, vous pouvez configurer le téléphone à l’aide de l’affichage du téléphone. L’affichage doit contenir **CaAP est activé**. Procédez comme suit :

    1. Cliquez sur **paramètres**.
    2. Sélectionnez **Avancé**.
    3. Entrez le mot de passe.
    4. Dans les **paramètres d’Administration**, sélectionnez **Les paramètres de téléphonie zone commune**.
    5. Activer **CAP** et **en Mode Admin CAP**.
    6. Cliquez sur **Enregistrer la configuration**.

- OK, maintenant votre téléphone étant prêt pouvoir vous connecter sur l’écran d’accueil.

    1. Se connecter en sélectionnant **paramètres** > **fonctionnalités** > **Skype pour les entreprises.**
    2. Sélectionnez les **Informations d’identification de l’utilisateur**et sélectionnez **web reconnectez-vous (CAP)** pour générer un code.
    3. Accédez au [portail de mise en service](http://aka.ms/skypecap)et connectez-vous en tant **qu’administrateur**.
    4. Entrez le nom complet (par exemple, principal réception).

       > [!Note]
       > Si vous **Recherchez des téléphones en zone commune uniquement** est activée, désactivez la case à cocher et rechercher à nouveau. »

    5. Dans la fenêtre code jumelage, entrez le code affiché sur le téléphone, cliquez sur **mettre en service**.

        La suite de cette dernière étape, le téléphone doit se connecter automatiquement.

### <a name="related-topics"></a>Rubriques connexes

- En savoir plus sur les téléphones disponibles au [Déploiement de Skype pour les téléphones en ligne Business](deploying-skype-for-business-online-phones.md).
- [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md)


