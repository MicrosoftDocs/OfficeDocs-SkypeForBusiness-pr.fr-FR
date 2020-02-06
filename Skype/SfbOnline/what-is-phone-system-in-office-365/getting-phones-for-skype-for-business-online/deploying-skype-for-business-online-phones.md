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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Découvrez les étapes de déploiement pour obtenir le microprogramme approprié, le mettre à jour si nécessaire, affecter des licences et configurer des paramètres pour des téléphones Skype entreprise online.
ms.openlocfilehash: efcea04a454d846c0140e9d1dba561da228df1de
ms.sourcegitcommit: a61d33fe15982bd8a34f1759b6b89be5aa699fe3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "41784751"
---
# <a name="deploying-skype-for-business-online-phones"></a>Déploiement de téléphones Skype Entreprise Online

Ce guide de déploiement vous aidera à déployer des téléphones IP Skype Entreprise Online.
  
In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Étapes de déploiement pour les téléphones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Étape 1 : télécharger les guides de l'administrateur et les manuels de téléphone du fabricant

Avant de commencer, il est pertinent de télécharger les guides d'administration et les manuels de téléphone du fabricant.
  
- Pour les téléphones Polycom, reportez-vous à la [bibliothèque de documentation de poly](https://documents.polycom.com/category/voice).
    
- Pour les téléphones Yealink, reportez-vous à la rubrique [solution de téléphone SIP HD Yealink Skype entreprise](http://www.yealink.com/products_top_2.html).
    
- Dans le cas de téléphones AudioCodes, consultez le guide [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Étape 2 : vérifier que votre achat ou migration concerne un téléphone IP et un microprogramme pris en charge par Skype Entreprise

A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Étape 3 : vérifier que le microprogramme adéquat est installé et le mettre à jour si nécessaire

Check the firmware version on your phones. For:
  
- **les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.
    
- **les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.
    
- **les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil.
    
    > [!NOTE]
    > For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals. 
  
- **les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.
    
### <a name="step-4---device-update-considerations"></a>Étape 4 : remarques sur la mise à jour de l'appareil

> [!NOTE]
> Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1). 
  
Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.
  
![Capture d’écran montrant le déploiement de téléphones](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.
  
![Capture d’écran montrant les options de mise à jour et de report.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Dans le cas d'un téléphone Polycom, vous pouvez mettre à jour le microprogramme en sélectionnant **SwUpdate (Mise à jour logicielle)**.
  
![Capture d’écran montrant l’option SWupdate (](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Vous pouvez également gérer les mises à jour du microprogramme à l'aide d'un système de provisionnement partenaire. Pour plus d'informations sur la gestion de système de provisionnement partenaire, notamment la personnalisation de téléphone avancée, consultez les guide d'administration du fabricant.
  
> [!CAUTION]
> Veillez à disposer d'une seule autorité de mise à jour pour l'appareil (mise à jour intrabande ou serveur de provisionnement tiers) pour éviter toute boucle de mise à jour. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Étape 5 : paramètres du téléphone de configuration et d’infrastructure

Vous pouvez configurer les options et stratégies téléphoniques les plus utilisées à l'aide d'applets de commande Windows PowerShell de gestion intrabande pour Skype Entreprise. Consultez le lien [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) pour plus de détails sur ces paramètres.
  
Pour la planification de l’infrastructure réseau, voir [infrastructure d’opérations Skype](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Étape 6 : préparation de la connexion des utilisateurs

To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Pour en savoir plus sur les offres d’appel, consultez la documentation relative au [système téléphonique et aux offres d’appels](/microsoftteams/calling-plan-landing-page) .
  
- Les **options de connexion** disponibles pour les utilisateurs Online sont les suivantes :
    
  - Les utilisateurs de téléphones **Polycom VVX 5xx/6xx** verront :
    
     ![Capture d’écran montrant la connexion de téléphones Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Les utilisateurs de téléphones **YEALINK VVX t48g/t46g verront** verront :
    
     ![Capture d’écran montrant la connexion de téléphones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Pour plus d’informations sur les options de connexion prises en charge par le fabricant, consultez la rubrique [réception de téléphones pour Skype entreprise Online](getting-phones-for-skype-for-business-online.md).
    
- **ID d'utilisateur** À l'aide de leur clavier téléphonique ou de leur clavier visuel (le cas échéant), les utilisateurs peuvent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. : <em>amosm@contoso.com</em>  pour leur nom d'utilisateur.
    
     ![Capture d’écran montrant l’écran de connexion](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'authentification par code confidentiel n'est pas prise en charge par Skype Entreprise Online avec les téléphones LPE et PIP (Partner IP Phone). 
  
- **Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.
    
  > [!NOTE]
  > Les utilisateurs doivent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. :  <em>amosm@contoso.com</em>  pour leur nom d'utilisateur.
  
     ![Capture d’écran montrant l’écran de connexion](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.
    
  - Les utilisateurs de téléphones **Polycom VVX 5xx/6xx** verront :
    
     ![Capture d’écran montrant les instructions Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Les utilisateurs de téléphones **YEALINK VVX t48g/t46g verront** verront :
    
     ![Capture d’écran montrant les instructions de Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.
    
  - Les utilisateurs de téléphones **Polycom VVX 5xx/6xx** verront :
    
     ![Capture d’écran montrant le code Polycom expiré](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Les utilisateurs de téléphones **YEALINK VVX t48g/t46g verront** verront :
    
     ![Capture d’écran montrant le code Yealink expiré](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    À l'aide d'un navigateur, accédez à l'adresse affichée dans le téléphone et saisissez votre nom d'utilisateur Skype Entreprise.
    
     ![Capture d’écran montrant la vérification de l’e-mail](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Entrez le code qui s'affiche sur le téléphone.
    
     ![Capture d’écran montrant le code de saisie sur l’écran de connexion](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Vérifiez que le site indique « [nom du fabricant du téléphone] **téléphone certifié Skype entreprise**» et cliquez sur **Continuer**.
    
     ![Capture d’écran montrant la vérification du nom](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Cliquez sur les informations de connexion de l'utilisateur ou sur **Use another account (Utiliser un autre compte)**:
    
     ![Capture d’écran montrant les options d’information d’identification](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Lorsque la page suivante s’affiche, vous pouvez fermer le navigateur en toute sécurité.
    
     ![Capture d’écran montrant un message de confirmation](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Les téléphones LPE pour Skype Entreprise Online prennent en charge la connexion via un périphérique USB uniquement. 
  
- **Déploiements pris en charge** Le tableau ci-après indique les types d'authentification pris en charge pour les modèles de déploiement actuellement pris en charge, y compris l'intégration d'Exchange, l'authentification moderne avec Multi-factor Authentication (MFA), et Skype Entreprise Online sur site.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype Entreprise** <br/> |**Exchange** <br/> |**Méthode de connexion au téléphone** <br/> |**Accès à Skype entreprise** <br/> |**Accès à Exchange avec Auth. moderne et MFA activées** <br/> |**Accès à Exchange avec Auth. moderne et MFA désactivées** <br/> |
|En ligne  <br/> |En ligne  <br/> |Connexion Web  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|En ligne  <br/> |En ligne  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|En ligne  <br/> |Sur site  <br/> |Connexion Web  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |
|En ligne  <br/> |Sur site  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Authentification par code confidentiel  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |N/D  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Connexion via PC (BTOE)  <br/> |Oui  <br/> |Oui  <br/> |N/D  <br/> |
   
- **Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.
    
    You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. Pour plus d’informations sur ces paramètres [, voir Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) .
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Étape 7 : si vous disposez du couplage d'appareil et de Better Together over Ethernet (BToE) (facultatif)
<a name="BK_BTOE"> </a>

BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:
  
- Se connecter à leur téléphone IP à l’aide de leur application de bureau Skype entreprise (à l’aide d’un PC)
    
- Synchroniser le verrouillage du téléphone avec le verrouillage de l’ordinateur
    
- Cliquer et appeler
    
BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.
  
 **Pour déployer BToE pour les utilisateurs**
  
1. Connectez leur PC à leur téléphone à l'aide du port du PC.
    
     ![Capture d’écran montrant la connexion à un PC](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Téléchargez et installez la dernière version du logiciel BToE à partir du site Web du fabricant à partir des liens ci-dessous. Pour une meilleure expérience utilisateur, vous pouvez distribuer et installer le logiciel BToE à l’aide d’une solution de distribution d’administration telle que Microsoft Endpoint Configuration Manager. Pour obtenir de l’aide sur la Configuration Manager, voir [packages et programmes dans Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).
    
   - [Site de téléchargement du logiciel BToE Polycom](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Téléchargement du logiciel BToE pour Yealink](http://www.yealink.com/products_list_10.html)
    
   - [Téléchargement du logiciel BToE pour AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).
    
> [!NOTE]
> BToE n'est actuellement pas disponible sur les plates-formes Mac et VDI. 
  
## <a name="related-topics"></a>Rubriques connexes
[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
