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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Apprenez les étapes de déploiement pour obtenir le microprogramme correct, le mettre à jour si nécessaire, affecter les licences, et configurer les paramètres des téléphones Skype Entreprise Online
ms.openlocfilehash: 4237e1cb32204a3d87d639710a2829c1111cc354
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780061"
---
# <a name="deploying-skype-for-business-online-phones"></a>Déploiement de téléphones Skype Entreprise Online

Ce guide de déploiement vous aidera à déployer des téléphones IP Skype Entreprise Online.
  
Dans tous les types d'entreprises, disposer d'un numéro de téléphone permet aux utilisateurs de passer et de recevoir des appels vocaux, ce qui est une condition importante pour faire des affaires. Les utilisateurs disposant de numéros de téléphone pourront passer des appels vocaux vers tous les appareils Skype Entreprise y compris les téléphones IP, les PC et les appareils mobiles. Vous pouvez en apprendre plus sur les téléphones IP Skype Entreprise en lisant [Obtention de téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Étapes de déploiement des téléphones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Étape 1 : télécharger les guides de l'administrateur et les manuels de téléphone du fabricant

Avant de commencer, il est pertinent de télécharger les guides d'administration et les manuels de téléphone du fabricant.
  
- Pour les téléphones Polycom, voir le [Guide de déploiement Polycom]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Pour les téléphones Yealink, voir [Solution de téléphones HD SIP Skype Entreprise Yealink](http://www.yealink.com/products_top_2.html).
    
- Dans le cas de téléphones AudioCodes, consultez le guide [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Étape 2 : assurez-vous que vous achetez ou que vous faites migrer un téléphone IP et un microprogramme pris en charge par Skype Entreprise

Un téléphone IP et un microprogramme pris en charge par Skype Entreprise Online sont également compatibles avec Skype Entreprise Server, mais l'inverse n'est pas toujours vrai. Pour vous assurer que vous achetez ou que vous approvisionnez un téléphone et un microprogramme pris en charge, voir [Obtention de téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Étape 3 : vérification du fait que le microprogramme adéquat est installé et mettre à jour le microprogramme si nécessaire

Vérifiez la version du microprogramme sur vos téléphones. Pour :
  
- **les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.
    
- **les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.
    
- **les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil.
    
    > [!NOTE]
    > Pour l'accès à distance aux détails des téléphones, reportez-vous aux guides d'administration du fabricant. Voir les liens ci-dessus pour les modes d'emploi et les manuels des téléphones. 
  
- **les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.
    
### <a name="step-4---device-update-considerations"></a>Étape 4 : remarques sur la mise à jour des appareils

> [!NOTE]
> Le microprogramme Polycom antérieur à la version 5.5.1.X disposait d'un mécanisme de verrouillage de l'appareil spécifique au fabricant qui est remplacé par une implémentation "Phone-Lock" de Skype Entreprise. La mise à jour d'un téléphone depuis la version 5.4.X.X qui était sécurisée par "Device-Lock" vers la version 5.5.1.X avec "Phone-Lock" n'héritera pas du code confidentiel du "Device-Lock", ce qui peut laisser le téléphone non sécurisé. Les utilisateurs qui ont activé la fonction "Device-Lock" doivent activer le paramètre suivant du Profil d'appareil Polycom pour donner le contrôle aux utilisateurs du moment de la mise à niveau (lync.deviceUpdate.popUpSK.enabled=1). 
  
Les mises à jour de microprogramme sont gérées par le service Skype Entreprise. Chaque microprogramme de téléphone certifié Skype Entreprise est chargé sur le serveur de mise à jour Skype Entreprise, et la mise à jour de l'appareil est activée par défaut sur tous les téléphones. En fonction de la durée d'inactivité sur le téléphone et des intervalles d'interrogation, les téléphones téléchargeront et installeront automatiquement les versions certifiées les plus récentes. Vous pouvez désactiver les paramètres de mise à jour des appareils en utilisant le cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) et en définissant le paramètre _EnableDeviceUpdate_ à `false`.
  
![Déploiement de téléphones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Lorsqu'un nouveau microprogramme sera disponible et prêt à être téléchargé et installé, le téléphone en informera l'utilisateur. Les téléphones Polycom en informeront l'utilisateur et lui fourniront une option pour **Mettre à jour**, ou **Reporter**.
  
![Déploiement de téléphones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Dans le cas d'un téléphone Polycom, vous pouvez mettre à jour le microprogramme en sélectionnant **SwUpdate (Mise à jour logicielle)**.
  
![Déploiement de téléphones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Vous pouvez également gérer les mises à jour du microprogramme à l'aide d'un système de provisionnement partenaire. Pour plus d'informations sur la gestion de système de provisionnement partenaire, notamment la personnalisation de téléphone avancée, consultez les guide d'administration du fabricant.
  
> [!CAUTION]
> Veillez à disposer d'une seule autorité de mise à jour pour l'appareil (mise à jour intrabande ou serveur de provisionnement tiers) pour éviter toute boucle de mise à jour. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Étape 5 : paramètres de téléphone de configuration et d’infrastructure

Vous pouvez configurer les options et stratégies téléphoniques les plus utilisées à l'aide d'applets de commande Windows PowerShell de gestion intrabande pour Skype Entreprise. Consultez le lien [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) pour plus de détails sur ces paramètres.
  
Pour la planification de l’infrastructure réseau, voir [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Étape 6 : préparation de la connexion des utilisateurs

Pour permettre aux utilisateurs de se connecter à un téléphone Skype Entreprise Online et de passer des appels, vous devez vous assurer que les licences adéquates ont été affectées aux utilisateurs. Au minimum, vous devez leur affecter une licence Système téléphonique et un Plan d'appels. Pour plus d'informations, vous pouvez voir [Octroi de licences de modules complémentaires Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) et[Affecter des licences Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Vous pouvez trouver plus d’informations sur les Plans d'appels en lisant [Quels sont les Plans d’appels dans Office 365 ?](/microsoftteams/what-are-calling-plans-in-office-365)
  
- Les **options de connexion** disponibles pour les utilisateurs Online sont les suivantes :
    
  - Les utilisateurs de téléphones **Polycom VVX 5XX/6XX** verront :
    
     ![Déploiement de téléphones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Les utilisateurs de téléphones **Yealink T48G/T46G** verront :
    
     ![Ouverture de session des téléphones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Pour des détails sur les options de connexion prises en charge par le fabricant, voir [Obtention de téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).
    
- **ID d'utilisateur** À l'aide de leur clavier téléphonique ou de leur clavier visuel (le cas échéant), les utilisateurs peuvent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. : *amosm@contoso.com*  pour leur nom d'utilisateur.
    
     ![Déploiement de téléphones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'authentification par code confidentiel n'est pas prise en charge par Skype Entreprise Online avec les téléphones LPE et PIP (Partner IP Phone). 
  
- **Utilisation d'un PC** Quand le logiciel Better Together over Ethernet (BToE) est installé et activé sur le PC d'un utilisateur, les utilisateurs peuvent se connecter à leur téléphone en utilisant la fenêtre d'authentification de leur application Skype Entreprise Windows. Voir [Étape 7 (facultative) : si vous avez le couplage d'appareil et Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) pour plus d'informations.
    
    > [!NOTE]
    > Les utilisateurs doivent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. :  *amosm@contoso.com*  pour leur nom d'utilisateur.
  
     ![Déploiement de téléphones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Utilisation d'une connexion par web** : il s'agit d'une nouvelle méthode pour les utilisateurs en ligne pour s'authentifier en utilisant un navigateur web standard. Les utilisateurs recevront un ensemble d'instructions à suivre lorsqu'ils utilisent un navigateur pour se connecter.
    
  - Les utilisateurs de téléphones **Polycom VVX 5XX/6XX** verront :
    
     ![Déploiement de téléphones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Les utilisateurs de téléphones **Yealink T48G/T46G** verront :
    
     ![Ouverture de session des téléphones Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    Le code généré expirera dans 15 minutes. Quand il aura expiré, l'utilisateur devra cliquer sur **Réessayer** ou sur **OK** pour générer un nouveau code, en fonction du téléphone.
    
  - Les utilisateurs de téléphones **Polycom VVX 5XX/6XX** verront :
    
     ![Code confidentiel expiré.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Les utilisateurs de téléphones **Yealink T48G/T46G** verront :
    
     ![Ouverture de session des téléphones Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    À l'aide d'un navigateur, accédez à l'adresse affichée dans le téléphone et saisissez votre nom d'utilisateur Skype Entreprise.
    
     ![Déploiement de téléphones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Entrez le code qui s'affiche sur le téléphone.
    
     ![Déploiement de téléphones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Vérifiez que le site affiche "[nom du fabricant du téléphone] **Téléphone certifié Skype Entreprise**", et cliquez sur **Continuer**.
    
     ![Déploiement de téléphones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Cliquez sur les informations de connexion de l'utilisateur ou sur **Use another account (Utiliser un autre compte)**:
    
     ![Déploiement de téléphones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Lorsque la page suivante est affichée, vous pouvez fermer le navigateur en toute sécurité.
    
     ![Déploiement de téléphones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Les téléphones LPE pour Skype Entreprise Online prennent en charge la connexion via un périphérique USB uniquement. 
  
- **Déploiements pris en charge** Le tableau ci-après indique les types d'authentification pris en charge pour les modèles de déploiement actuellement pris en charge, y compris l'intégration d'Exchange, l'authentification moderne avec Multi-factor Authentication (MFA), et Skype Entreprise Online sur site.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype Entreprise** <br/> |**Exchange** <br/> |**Méthode de connexion au téléphone** <br/> |**Accès à Skype Entreprise** <br/> |**Accès à Exchange avec Auth. moderne et MFA activées** <br/> |**Accès à Exchange avec Auth. moderne et MFA désactivées** <br/> |
|En ligne  <br/> |En ligne  <br/> |Connexion Web  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|En ligne  <br/> |En ligne  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|En ligne  <br/> |Sur site  <br/> |Connexion Web  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |
|En ligne  <br/> |Sur site  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Authentification par code confidentiel  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |N/D  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Connexion via PC (BTOE)  <br/> |Oui  <br/> |Oui  <br/> |N/D  <br/> |
   
- **Fonctionnalités de téléphonie** Le jeu des fonctionnalités peut varier légèrement selon le partenaire de téléphonie IP. Pour le jeu complet des fonctionnalités et pour plus d’informations sur les fonctionnalités de chaque fabricant de téléphone, voir [Obtention de téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** est une fonction récemment introduite dans les téléphones certifiés Skype Entreprise, qui est utilisée pour sécuriser un téléphone. Si elle est activée, les utilisateurs seront invités à créer un code confidentiel lors d'une authentification réussie. Une fois créé, les téléphones se verrouilleront lorsque le délai d'inactivité que vous aurez défini arrive à expiration, un utilisateur pourra verrouiller manuellement son téléphone, ou synchroniser le verrouillage de son téléphone avec son PC en utilisant le couplage de téléphone. Si le code confidentiel de verrouillage est saisi plusieurs fois de manière incorrecte, soit le téléphone déconnectera l'utilisateur, soit il demandera le code d'un administrateur pour déverrouiller le téléphone ; mais cela variera en fonction du partenaire de téléphonie. Le code confidentiel de l'utilisateur doit comprendre entre 6 et 15 chiffres.
    
    Vous pouvez désactiver Phone-Lock (qui est activé par défaut) pour votre organisation, modifier le délai d'inactivité, et décider si les utilisateurs peuvent ou non passer des appels lorsqu'ils sont verrouillés, en utilisant les paramètres intrabande. Voir [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) pour plus de détails sur ces paramètres.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Étape 7 (facultative) : si vous disposez du couplage d'appareil et de Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE est un mécanisme de couplage pour les téléphones IP d'un partenaire, qui couple le téléphone d'un utilisateur avec son application Skype Entreprise Windows. BToE permet aux utilisateurs de :
  
- Se connecter à leur téléphone IP en utilisant leur application de bureau Skype Entreprise (sur un PC)
    
- Synchroniser Phone-Lock avec le verrouillage de leur PC
    
- Cliquer pour appeler
    
BToE peut être configuré pour fonctionner en deux modes :  *Auto*  (par défaut) et *Manuel*. Il peut également être activé (par défaut)/désactivé pour les utilisateurs utilisant les paramètres intrabande de Skype Entreprise. Lorsqu'ils travaillent en mode *Manuel*, les utilisateurs devront effectuer une étape supplémentaire pour coupler leur téléphone avec leur application Windows.
  
 **Pour déployer BToE pour les utilisateurs**
  
1. Connectez leur PC à leur téléphone à l'aide du port du PC.
    
     ![Déploiement de téléphones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Téléchargez et installez la dernière version du logiciel BToE à partir du site Web du fabricant disponible en cliquant sur les liens ci-dessous. Pour une expérience utilisateur optimale, vous pouvez distribuer et installer le logiciel BToE à l'aide d'une solution de distribution d'administrateur, telle que System Center Configuration Manager (SCCM). Pour obtenir de l'aide pour utiliser SCCM, reportez-vous à la page [Packages et programmes dans System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).
    
  - [Site de téléchargement du logiciel BToE Polycom](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Téléchargement du logiciel BToE pour Yealink](http://www.yealink.com/products_list_10.html)
    
  - [Téléchargement du logiciel BToE pour AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. Le paramètre du serveur pour BToE est défini par défaut comme **Activé** et **Mode auto**. Pour modifier ces paramètres, voir [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> BToE n'est pas actuellement supporté sur les plates-formes Mac et VDI. 
  
## <a name="related-topics"></a>Rubriques connexes
[Obtention de numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Ce dont vous disposerez avec le Système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilité par pays et par région de l'Audioconférence et des Plans d'appels](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
