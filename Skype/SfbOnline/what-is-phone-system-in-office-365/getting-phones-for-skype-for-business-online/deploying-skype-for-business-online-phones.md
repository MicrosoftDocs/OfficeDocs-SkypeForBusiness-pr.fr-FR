---
title: Déploiement de téléphones Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
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
description: Découvrez les étapes de déploiement pour obtenir le microprogramme correct, le mettre à jour si nécessaire, attribuer des licences et configurer les paramètres des téléphones Skype Entreprise Online
ms.openlocfilehash: b9724677a3217b73b727a72343f35ebe51a4de09
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011898"
---
# <a name="deploying-skype-for-business-online-phones"></a>Déploiement de téléphones Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

Ce guide de déploiement vous aidera à déployer des téléphones IP Skype Entreprise Online.
  
Dans tous les types d’entreprises, disposer d’un numéro de téléphone permet aux utilisateurs de passer et de passer des appels vocaux, et c’est une obligation essentielle pour effectuer des activités professionnelles. Les utilisateurs qui ont des numéros de téléphone pourront passer des appels vocaux sur tous les appareils Skype Entreprise, y compris les téléphones IP, les PC et les appareils mobiles. Pour en savoir plus sur les téléphones IP Skype Entreprise, lisez Obtenir des téléphones [pour Skype Entreprise Online.](getting-phones-for-skype-for-business-online.md)
  
## <a name="deployment-steps-for-ip-phones"></a>Étapes de déploiement pour les téléphones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Étape 1 : télécharger les guides de l'administrateur et les manuels de téléphone du fabricant

Avant de commencer, il est pertinent de télécharger les guides d'administration et les manuels de téléphone du fabricant.
  
- Pour les téléphones Polycom, voir la [bibliothèque de documentation Poly.](https://documents.polycom.com/category/voice)
    
- Pour les téléphones Yealink, consultez la [solution Yealink pour les téléphones SIP HD Skype Entreprise.](http://www.yealink.com/products_top_2.html)
    
- Dans le cas de téléphones AudioCodes, consultez le guide [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Étape 2 : vérifier que votre achat ou migration concerne un téléphone IP et un microprogramme pris en charge par Skype Entreprise

Un téléphone IP et un microprogramme pris en charge par Skype Entreprise Online sont également compatibles avec Skype Entreprise Server, mais l'inverse n'est pas toujours vrai. Pour vous assurer que vous achetez ou provisionniez un téléphone et microprogramme pris en charge, consultez Obtenir des téléphones [pour Skype Entreprise Online.](getting-phones-for-skype-for-business-online.md)
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Étape 3 : vérifier que le microprogramme adéquat est installé et le mettre à jour si nécessaire

Vérifiez la version du microprogramme sur votre téléphone. Pour :
  
- **les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.
    
- **les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.
    
- **les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil.
    
    > [!NOTE]
    > Pour obtenir des informations sur l’accès à distance des téléphones, reportez-vous aux guides d’administration du fabricant. Cliquez sur les liens vers les manuels d'utilisation et de téléphone indiqués plus haut. 
  
- **les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.
    
### <a name="step-4---device-update-considerations"></a>Étape 4 : remarques sur la mise à jour de l'appareil

> [!NOTE]
> Le microprogramme Polycom antérieur à la version 5.5.1.X avait un mécanisme de verrouillage de l’appareil spécifique au fabricant qui est remplacé par un « verrouillage téléphonique » mis en œuvre par Skype Entreprise. La mise à niveau d’un téléphone à partir de la mise à niveau 5.4.X.X sécurisée avec « Verrouillage de l’appareil » vers la 5.5.1.X avec le « Verrouillage du téléphone » n’héritera pas du code confidentiel du « Verrouillage de l’appareil », ce qui peut rendre le téléphone non sécurisé. Les utilisateurs qui ont activé le verrouillage de l’appareil doivent activer le paramètre de profil d’appareil Polycom suivant pour leur permettre de contrôler le temps de mise à niveau (lync.deviceUpdate.popUpSK.enabled=1). 
  
Les mises à jour de microprogramme sont gérées par le service Skype Entreprise. Chaque microprogramme de téléphone certifié Skype Entreprise est chargé vers le serveur de mise à jour Skype Entreprise et la mise à jour de l'appareil est activée par défaut sur tous les téléphones. En fonction de la durée d'inactivité et des intervalles d'interrogation, les téléphones téléchargeront automatiquement les dernières versions certifiées. Vous pouvez désactiver les paramètres de mise à jour de l’appareil à l’aide de l’cmdlet [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) et en activant le paramètre _EnableDeviceUpdate_ `false` sur.
  
![Capture d’écran montrant le déploiement de téléphones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Lorsqu'un nouveau microprogramme est disponible et prêt à être téléchargé et installé, le téléphone informera l'utilisateur. Les téléphones Polycom informeront l’utilisateur et fourniront une option de mise à jour **ou** **de** report.
  
![Capture d’écran montrant les options de mise à jour et de report.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Dans le cas d'un téléphone Polycom, vous pouvez mettre à jour le microprogramme en sélectionnant **SwUpdate (Mise à jour logicielle)**.
  
![Capture d’écran montrant l’option SwUpdate.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Vous pouvez également gérer les mises à jour du microprogramme à l'aide d'un système de provisionnement partenaire. Pour plus d'informations sur la gestion de système de provisionnement partenaire, notamment la personnalisation de téléphone avancée, consultez les guide d'administration du fabricant.
  
> [!CAUTION]
> Veillez à disposer d'une seule autorité de mise à jour pour l'appareil (mise à jour intrabande ou serveur de provisionnement tiers) pour éviter toute boucle de mise à jour. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Étape 5 : configuration et infrastructure des paramètres téléphoniques

Vous pouvez configurer les options et stratégies téléphoniques les plus utilisées à l'aide d'applets de commande Windows PowerShell de gestion intrabande pour Skype Entreprise. Consultez le lien [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) pour plus de détails sur ces paramètres.
  
Pour la planification de l’infrastructure réseau, [consultez Skype Operations Framework.](https://www.skypeoperationsframework.com/)
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Étape 6 : préparation de la inscription des utilisateurs

Pour permettre aux utilisateurs de se connecter avec succès à un téléphone Skype Entreprise Online et de téléphoner, vous devez vous assurer que les licences qui leur sont affectées sont correctes. Au minimum, vous devrez affecter une licence Phone System et un plan d’appels. Pour plus d’informations, vous pouvez consulter les licences des modules complémentaires Skype Entreprise et [Microsoft Teams,](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) ainsi que l’affectation de [licences Skype Entreprise et Microsoft Teams.](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)
  
Pour en savoir plus sur les forfaits d’appels, lisez [Phone System et Calling Plans](/microsoftteams/calling-plan-landing-page)
  
- Les **options de connexion** disponibles pour les utilisateurs Online sont les suivantes :
    
  - Les utilisateurs **de téléphones Polycom VVX 5XX/6XX** peuvent voir :
    
     ![Capture d’écran montrant l' logo des téléphones Polycom.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Les utilisateurs **de téléphones Yealink T48G/T46G** peuvent voir :
    
     ![Capture d’écran montrant l' logo des téléphones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Pour plus d’informations sur les options de personnalisation prise en charge par le fabricant, consultez Obtenir des téléphones [pour Skype Entreprise Online.](getting-phones-for-skype-for-business-online.md)
    
- **ID d'utilisateur** À l'aide de leur clavier téléphonique ou de leur clavier visuel (le cas échéant), les utilisateurs peuvent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. : <em>amosm@contoso.com</em>  pour leur nom d'utilisateur.
    
     ![Capture d’écran montrant l’écran de connexion.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'authentification par code confidentiel n'est pas prise en charge par Skype Entreprise Online avec les téléphones LPE et PIP (Partner IP Phone). 
  
- **Utilisation d’un PC** Lorsque le logiciel Better Together over Ethernet (BToE) est installé et activé sur le PC de l’utilisateur, il peut se connecter à son téléphone à l’aide de la fenêtre d’authentification de l’application Windows Skype Entreprise. Pour plus d’informations, consultez skype [Operations Framework (SOF)](https://techcommunity.microsoft.com/t5/skype-for-business-blog/what-is-skype-operations-framework-sof-and-skype-academy/ba-p/30506) et Skype Academy.
    
  > [!NOTE]
  > Les utilisateurs doivent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. :  <em>amosm@contoso.com</em>  pour leur nom d'utilisateur.
  
     ![Capture d’écran montrant l’écran de connexion.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Utilisation d’une authentification web**: il s’agit d’une nouvelle façon pour les utilisateurs en ligne de s’authentifier à l’aide d’un navigateur web standard. Les utilisateurs seront fournis avec un ensemble d’instructions à suivre lorsqu’ils utilisent un navigateur pour se connecter.
    
  - Les utilisateurs **de téléphones Polycom VVX 5XX/6XX** peuvent voir :
    
     ![Capture d’écran montrant les instructions polycom.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Les utilisateurs **de téléphones Yealink T48G/T46G** peuvent voir :
    
     ![Capture d’écran montrant les instructions pour Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    Le code généré expire dans les 15 minutes. Une fois expiré, l’utilisateur  devra cliquer sur Réessayer ou **SUR OK** pour générer un nouveau code, selon le téléphone.
    
  - Les utilisateurs **de téléphones Polycom VVX 5XX/6XX** peuvent voir :
    
     ![Capture d’écran montrant le code Polycom expiré.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Les utilisateurs **de téléphones Yealink T48G/T46G** peuvent voir :
    
     ![Capture d’écran montrant le code Yealink expiré.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    À l'aide d'un navigateur, accédez à l'adresse affichée dans le téléphone et saisissez votre nom d'utilisateur Skype Entreprise.
    
     ![Capture d’écran montrant la vérification du courrier électronique.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Entrez le code qui s'affiche sur le téléphone.
    
     ![Capture d’écran montrant la saisie du code à l’écran de connexion.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Vérifiez que le site indique « [nom du fabricant du téléphone] Téléphone certifié **Skype** Entreprise », puis cliquez **sur Continuer.**
    
     ![Capture d’écran montrant la vérification du nom.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Cliquez sur les informations de connexion de l'utilisateur ou sur **Use another account (Utiliser un autre compte)**:
    
     ![Capture d’écran montrant les options d’informations d’identification.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Lorsque la page suivante s’affiche, vous ne risquez pas de fermer le navigateur.
    
     ![Capture d’écran montrant un message de confirmation.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Les téléphones LPE pour Skype Entreprise Online prennent en charge la connexion via un périphérique USB uniquement. 
  
- **Déploiements pris en charge** Le tableau ci-après indique les types d'authentification pris en charge pour les modèles de déploiement actuellement pris en charge, y compris l'intégration d'Exchange, l'authentification moderne avec Multi-factor Authentication (MFA), et Skype Entreprise Online sur site.

  
 
 
|Skype Entreprise |Exchange |Méthode de connexion au téléphone |Accès à Skype Entreprise |Accès à Exchange avec Auth. moderne et MFA activées |Accès à Exchange avec Auth. moderne et MFA désactivées |
|:-----|:-----|:-----|:-----|:-----|:-----|
|En ligne   |En ligne   |Connexion Web   |Oui   |Oui   |Oui   |
|En ligne   |En ligne   |Nom d'utilisateur/Mot de passe   |Oui   |Oui   |Non   |
|En ligne   |Sur site   |Connexion Web   |Oui   |Non   |Non   |
|En ligne   |Sur site   |Nom d'utilisateur/Mot de passe   |Oui   |Oui   |Non   |
|Sur site   |En ligne/sur site   |Authentification de code confidentiel   |Oui   |Non   |Non   |
|Sur site   |En ligne/sur site   |Nom d'utilisateur/Mot de passe   |Oui   |Oui   |N/D   |
|Sur site   |En ligne/sur site   |Connexion via PC (BTOE)  |Oui   |Oui   |N/D   |
   
- **Fonctionnalités du téléphone** L’ensemble des fonctionnalités peut varier légèrement d’un partenaire de téléphone IP à l’autre. Pour obtenir l’ensemble complet des fonctionnalités et pour plus d’informations sur les fonctionnalités de chaque fabricant, consultez Obtenir des téléphones [pour Skype Entreprise Online.](getting-phones-for-skype-for-business-online.md)
    
- **Le verrouillage du** téléphone est une fonctionnalité récemment introduite dans les téléphones certifiés Skype Entreprise utilisé pour sécuriser un téléphone. Si l’authentification est activée, les utilisateurs sont invités à créer un code confidentiel à l’authentification réussie. Une fois créés, les téléphones sont verrouillés à l’expiration du délai d’inactivité que vous définissez, lorsqu’un utilisateur verrouille manuellement son téléphone ou lorsqu’il synchronise son verrouillage du téléphone avec son PC à l’aide du jumelage de téléphone. Si le code confidentiel de verrouillage du téléphone n’est pas entré à plusieurs reprises, le téléphone déverrouille l’utilisateur ou nécessite un code d’administrateur pour déverrouiller le téléphone, mais cela peut varier en fonction du partenaire téléphonique. Le code confidentiel de l’utilisateur doit être entre 6 et 15 chiffres.
    
    Vous pouvez désactiver les Phone-Lock pour votre organisation (option activée par défaut), modifier le délai d’inactivité et choisir si les utilisateurs peuvent effectuer des appels téléphoniques lorsqu’ils sont verrouillés ou non à l’aide des paramètres de bandeau. Pour plus d’informations sur ces paramètres, voir [Set-CsUCPhoneConfiguration.](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Étape 7 : si vous disposez du couplage d'appareil et de Better Together over Ethernet (BToE) (facultatif)
<a name="BK_BTOE"> </a>

BToE est un mécanisme de coupage pour les téléphones IP partenaires qui couple le téléphone d’un utilisateur avec son application Windows Skype Entreprise. BToE permet aux utilisateurs d'effectuer les actions suivantes :
  
- Se connectez à leur téléphone IP à l’aide de leur application de bureau Skype Entreprise (à l’aide d’un PC)
    
- Synchroniser Phone-Lock avec le verrouillage du PC
    
- Cliquer pour appeler
    
BToE peut être configuré pour fonctionner en deux modes : *Automatique* (par défaut) et *Manuel.* Il peut également être activé (par défaut)/désactivé pour les utilisateurs utilisant les paramètres intrabande de Skype Entreprise. En mode *manuel*  , les utilisateurs doivent réaliser une étape supplémentaire pour coupler leur téléphone avec leur application Windows.
  
 **Pour déployer BToE vers des utilisateurs**
  
1. Connectez leur PC à leur téléphone à l'aide du port du PC.
    
     ![Capture d’écran montrant la connexion à un PC.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Téléchargez et installez la dernière version du logiciel BToE à partir du site Web du fabricant disponible en cliquant sur les liens ci-dessous. Pour une meilleure expérience utilisateur, vous pouvez distribuer et installer le logiciel BToE à l’aide d’une solution de distribution d’administrateur telle que Microsoft Endpoint Configuration Manager. Pour obtenir de l’aide sur l’utilisation de Configuration Manager, voir [Packages et programmes dans Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)
    
   - [Site de téléchargement du logiciel BToE pour Polycom](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Téléchargement du logiciel BToE pour Yealink](http://www.yealink.com/products_list_10.html)
    
   - [Téléchargement du logiciel BToE pour AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. Par défaut, le paramètre serveur  de BToE est activé et **le mode** automatique. Pour modifier ces paramètres, voir [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).
    
> [!NOTE]
> BToE n'est actuellement pas disponible sur les plates-formes Mac et VDI. 
  
## <a name="related-topics"></a>Rubriques connexes
[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Voici les avantages du système téléphonique](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

