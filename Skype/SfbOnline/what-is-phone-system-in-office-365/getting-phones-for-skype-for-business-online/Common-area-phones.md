---
title: Déploiement de téléphones Skype Entreprise Online
description: Découvrez les étapes de déploiement pour obtenir le microprogramme approprié, mettre à jour si nécessaire, attribuer des licences et configurer les paramètres pour les téléphones en zone commune.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
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
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a>Téléphones de partie commune
Un téléphone en zone commune ou délimiter, est généralement placée dans une zone partagée et non associé à un utilisateur individuel. Par exemple, un téléphone en zone réception, salle de réunion ou de téléphone porte le téléphone majuscules sont configurés en tant que périphériques plutôt que les utilisateurs et établir automatiquement une connexion au réseau. Dans les étapes suivantes, nous allons vous aider à configurer un compte pour le système téléphonique de Microsoft avec des Plans de l’appel, puis déployer une extrémité.

## <a name="prerequisites-for-common-area-phones"></a>Conditions requises pour les téléphones de partie commune

Vérifiez que vous disposez des éléments suivants :

    - Acheté téléphone en zone commune SKU 
    - Mise à jour de microprogramme (voir prise en charge du microprogramme dans la rubriquehttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
    - Téléphones approuvés (consulter la liste àhttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones) 


## <a name="check-the-firmware-for-your-phone"></a>Vérification du microprogramme de votre téléphone
- **les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.
- **les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.
- **les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil. 
- **les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.

Les mises à jour de microprogramme sont gérées par le service Skype Entreprise. Chaque microprogramme de téléphone certifié Skype Entreprise est chargé vers le serveur de mise à jour Skype Entreprise et la mise à jour de l'appareil est activée par défaut sur tous les téléphones. 

En fonction de la durée d'inactivité et des intervalles d'interrogation, les téléphones téléchargeront automatiquement les dernières versions certifiées. Vous pouvez désactiver les paramètres de mise à jour des périphériques à l’aide de l’applet de commande [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) et au paramètre _EnableDeviceUpdate_ `false`.

## <a name="create-cap"></a>Créer le point d’accès client
Vous créez le point d’accès client en configurant les paramètres avant de configurer le téléphone physique.

#### <a name="purchase-the-common-area-phone-sku"></a>Acheter un téléphone en zone commune SKU. 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a>Configurer le téléphone en zone commune<!-- this section could use a screen shot-->

**Création d’utilisateur** 
1. Affecter le téléphone en zone commune SKU
2. Affecter l’appel planifier (si vous utilisez le système téléphonique de Microsoft avec des Plans de l’appel). 
3. Affecter un numéro de téléphone disponibles dans le Skype entreprise centre d’administration, ou demander un nouveau numéro de téléphone.

**Créer un nouvel utilisateur**

1. Dans le volet Mise en service, vous pouvez entrer un prénom et le nom (par exemple, réception principal).
2. Entrez un nom d’affichage (obligatoire), par exemple, « réception principal ».
3. Entrez un nom d’utilisateur (obligatoire), par exemple « MainReception » @ » domaine » (nom de société ou entreprise)
4. Entrez l’emplacement (pays).

**Affecter le téléphone en zone commune SKU** Dans le centre d’administration Office 365, accédez à **facturation > Services d’achat** et ajoutez le **Téléphone en zone commune**

**Affecter le Plan d’appel dans CAP SKU**

1. Sélectionnez un Plan de l’appel pour activer le téléphone. 
2. Ajouter le point d’accès client pour activer le système téléphonique et Skype pour Business Online Plan 2 dans le point d’extrémité. <!-- odd order for step -->

**Affecter un numéro de téléphone**
1. Vérifier les numéros de téléphone disponibles sous **vocale > numéros de téléphone**.
2. Sélectionnez un numéro dans la liste numéro de téléphone numéros disponibles.
3. Confirmer votre sélection en sélectionnant la **voix** et les **Numéros de téléphone**.

    >[Note] Les utilisateurs de voix affichent uniquement s’ils disposent de la licence de système téléphonique appliquée, bien que même après avoir appliqué, peut prendre du temps pour actualiser. Permet de centre de soi à un moment rouvrir Skype pour administrateur d’entreprise.
    
## <a name="configure-phone"></a>Configurer le téléphone

**Préparer les téléphones physiques** 

Votre téléphone sélectionné doit avoir le mode de téléphone en zone commune. 

***Téléphone de Polycom VVX exemple***

Activer le Mode téléphone zone commune sur Polycom VVX en suivant ces étapes :
1. Dans votre navigateur, utilisez l’interface web pour activer le mode de point d’accès client sur le VVX
2. Accédez au **paramètre** et le Skype pour l’option de configuration d’entreprise, sélectionnez **Téléphone en zone commune**.
3. Cliquez sur **Enregistrer** pour enregistrer vos paramètres de configuration.

Maintenant que le mode de téléphone CAP est activé, vous pouvez configurer le téléphone à l’aide de l’affichage du téléphone.

1. Dans les paramètres, cliquez sur **Avancé**.
2. Entrez le mot de passe.
3. Dans les paramètres d’Administration, sélectionnez **Les paramètres de téléphonie zone commune**.
4. Activer le téléphone de partie commune et délimiter Admin
5. Sélectionnez **Enregistrer la configuration**.

Votre téléphone est prêt à être mis en service, ce qui vous serez amené à vous connecter sur l’écran d’accueil.

1. Se connecter en sélectionnant **Paramètres > fonctionnalités > Skype pour les entreprises.**
2. Sélectionnez les informations d’identification de l’utilisateur, puis sélectionnez Sélectionner **web reconnectez-vous (CAP)** pour générer un code...
3. Accédez à la mise en service portal http://aka.ms/skypecapet se connecter en tant **qu’administrateur**.
4. Entrez le nom complet (par exemple, principal réception) pour afficher votre point d’accès client.

>[Note] Si « Recherche pour seulement les téléphones de partie commune » est activée, désactivez la case à cocher et effectuez une nouvelle recherche.

5. Dans la fenêtre code jumelage, entrez le code affiché sur le téléphone, cliquez sur **mettre en service**.

RS cette dernière étape, le téléphone doit se connecter automatiquement.

Pour plus d’informations sur les téléphones disponibles à [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).


