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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Découvrez les étapes du déploiement pour obtenir le microprogramme approprié, mettre à jour si nécessaire, attribuer des licences et configurer les paramètres pour Skype pour les téléphones en ligne Business
ms.openlocfilehash: 809cec268ac2a086a01fc00cf043759a326a34f5
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531815"
---
# <a name="deploying-skype-for-business-online-phones"></a>Déploiement de téléphones Skype Entreprise Online

Ce guide de déploiement vous aidera à déployer des téléphones IP Skype Entreprise Online.
  
Dans tous les types d’entreprises, un numéro de téléphone permet aux utilisateurs de créer et obtenir des appels vocaux et il est un élément important à travailler. Les utilisateurs qui ont des numéros de téléphone sera en mesure d’effectuer des appels vocaux sur tous les Skype pour les appareils métier, y compris les téléphones IP, PC et appareils mobiles. Vous pouvez en savoir plus sur Skype pour les téléphones IP de l’entreprise en lisant les [téléphones de mise en route pour Skype pour Business Online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Étapes de déploiement pour les téléphones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Étape 1 : télécharger les guides de l'administrateur et les manuels de téléphone du fabricant

Avant de commencer, il est pertinent de télécharger les guides d'administration et les manuels de téléphone du fabricant.
  
- Pour les téléphones Polycom, voir [Guide de déploiement de Polycom] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Pour les téléphones Yealink, voir [Yealink Skype pour Business HD SIP téléphones](http://www.yealink.com/products_top_2.html).
    
- Dans le cas de téléphones AudioCodes, consultez le guide [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Étape 2 : vérifier que votre achat ou migration concerne un téléphone IP et un microprogramme pris en charge par Skype Entreprise

Un téléphone IP et un microprogramme pris en charge par Skype Entreprise Online sont également compatibles avec Skype Entreprise Server, mais l'inverse n'est pas toujours vrai. Vérifiez que vous achetez ou un téléphone pris en charge et le microprogramme de mise en service, voir [Getting téléphones pour Skype pour Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Étape 3 : vérifier que le microprogramme adéquat est installé et le mettre à jour si nécessaire

Vérifiez la version du microprogramme sur votre téléphone. Pour :
  
- **les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.
    
- **les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.
    
- **les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil.
    
    > [!NOTE]
    > Pour l’accès distant au numéro de téléphone, reportez-vous aux guides de l’administration du fabricant. Consultez les liens ci-dessus pour les guides de l’utilisateur et les manuels de téléphone. 
  
- **les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.
    
### <a name="step-4---device-update-considerations"></a>Étape 4 : remarques sur la mise à jour de l'appareil

> [!NOTE]
> Microprogramme Polycom avant 5.5.1.X a rencontré un mécanisme de verrouillage de périphérique fabricant est remplacé par une Skype pour l’implémentation d’entreprise « Phone-Lock ». Mise à niveau d’un téléphone de 5.4.X.X qui a été sécurisé avec « Périphérique-Lock » à 5.5.1.X avec « Verrouillage de téléphone », le code PIN à partir de « Périphériques verrouillage de « laisser le téléphone non sécurisé ne hérite. Les utilisateurs qui vous ont activé « Périphérique-Lock » doivent activer le paramètre de profil de périphérique Polycom suivant donner le contrôle du temps de mise à niveau (lync.deviceUpdate.popUpSK.enabled=1) les utilisateurs. 
  
Les mises à jour de microprogramme sont gérées par le service Skype Entreprise. Chaque microprogramme de téléphone certifié Skype Entreprise est chargé vers le serveur de mise à jour Skype Entreprise et la mise à jour de l'appareil est activée par défaut sur tous les téléphones. En fonction de la durée d'inactivité et des intervalles d'interrogation, les téléphones téléchargeront automatiquement les dernières versions certifiées. Vous pouvez désactiver les paramètres de mise à jour des périphériques à l’aide de l’applet de commande [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) et au paramètre _EnableDeviceUpdate_ `false`.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Lorsqu’un nouveau microprogramme est disponible et prêt pour télécharger et installer, le téléphone avertit l’utilisateur. Téléphones Polycom vous avertir l’utilisateur et leur fournir une option de mise à **jour** ou **différer**.
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Dans le cas d'un téléphone Polycom, vous pouvez mettre à jour le microprogramme en sélectionnant **SwUpdate (Mise à jour logicielle)**.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Vous pouvez également gérer les mises à jour du microprogramme à l'aide d'un système de provisionnement partenaire. Pour plus d'informations sur la gestion de système de provisionnement partenaire, notamment la personnalisation de téléphone avancée, consultez les guide d'administration du fabricant.
  
> [!CAUTION]
> Veillez à disposer d'une seule autorité de mise à jour pour l'appareil (mise à jour intrabande ou serveur de provisionnement tiers) pour éviter toute boucle de mise à jour. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Étape 5 : paramètres de Configuration et l’infrastructure téléphonique

Vous pouvez configurer les options et stratégies téléphoniques les plus utilisées à l'aide d'applets de commande Windows PowerShell de gestion intrabande pour Skype Entreprise. Consultez le lien [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) pour plus de détails sur ces paramètres.
  
Pour la planification de l’infrastructure réseau, voir [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Étape 6 : préparation pour les utilisateurs à se connecter

Pour permettre aux utilisateurs de se connecter à un Skype pour téléphone professionnel en ligne et émettre des appels avec succès, vous devez pour vous assurer que les utilisateurs reçoivent les licences appropriés. Au minimum, vous devez attribuer une licence de système téléphonique et un Plan d’appel. Pour plus d’informations, vous pouvez voir [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestion des licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) et [Affecter les Skype pour les professionnels et les équipes Microsoft de licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Vous pouvez trouver plus d’informations sur les Plans d'appels en lisant [Quels sont les Plans d’appels dans Office 365 ?](/microsoftteams/what-are-calling-plans-in-office-365)
  
- Les **options de connexion** disponibles pour les utilisateurs Online sont les suivantes :
    
  - Avec les téléphones **Polycom VVX 5XX/6XX** s’affiche :
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Avec les téléphones **Yealink T48G/T46G** s’affiche :
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Pour plus d’informations sur les options de connexion pris en charge par le fabricant, voir [Getting téléphones pour Skype pour Business Online](getting-phones-for-skype-for-business-online.md).
    
- **ID d'utilisateur** À l'aide de leur clavier téléphonique ou de leur clavier visuel (le cas échéant), les utilisateurs peuvent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. : <em>amosm@contoso.com</em>  pour leur nom d'utilisateur.
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'authentification par code confidentiel n'est pas prise en charge par Skype Entreprise Online avec les téléphones LPE et PIP (Partner IP Phone). 
  
- **À l’aide d’un PC** Lorsque Better Together sur logiciel Ethernet (BToE) est installé sur l’ordinateur de l’utilisateur et activée, les utilisateurs peuvent ouvrir sur leur téléphone à l’aide de la fenêtre d’authentification sur leurs Skype Windows pour l’application de gestion. Pour plus d’informations, consultez [étape 7 (facultatif) - si vous avez appariement des périphériques et Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) .
    
  > [!NOTE]
  > Les utilisateurs doivent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. :  <em>amosm@contoso.com</em>  pour leur nom d'utilisateur.
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **À l’aide d’une connexion Web**: il s’agit d’une nouvelle façon pour les utilisateurs en ligne pour s’authentifier à l’aide d’un navigateur web standard. Les utilisateurs seront fournies avec un ensemble d’instructions à suivre lorsqu’ils utilisent un navigateur pour vous connecter.
    
  - Avec les téléphones **Polycom VVX 5XX/6XX** s’affiche :
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Avec les téléphones **Yealink T48G/T46G** s’affiche :
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    Le code généré va expirer dans 15 minutes. Lorsqu’il arrive à expiration, l’utilisateur aura à cliquer sur **Réessayer** ou sur **OK** pour générer un nouveau code, en fonction du téléphone.
    
  - Avec les téléphones **Polycom VVX 5XX/6XX** s’affiche :
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Avec les téléphones **Yealink T48G/T46G** s’affiche :
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    À l'aide d'un navigateur, accédez à l'adresse affichée dans le téléphone et saisissez votre nom d'utilisateur Skype Entreprise.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Entrez le code qui s'affiche sur le téléphone.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Vérifiez que le site affiche « [nom du fabricant du téléphone] **Skype pour le numéro de téléphone professionnel certifié**, » et cliquez sur **Continuer**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Cliquez sur les informations de connexion de l'utilisateur ou sur **Use another account (Utiliser un autre compte)**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Lorsque la page suivante s’affiche, il est fiable fermer le navigateur.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Les téléphones LPE pour Skype Entreprise Online prennent en charge la connexion via un périphérique USB uniquement. 
  
- **Déploiements pris en charge** Le tableau ci-après indique les types d'authentification pris en charge pour les modèles de déploiement actuellement pris en charge, y compris l'intégration d'Exchange, l'authentification moderne avec Multi-factor Authentication (MFA), et Skype Entreprise Online sur site.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype Entreprise** <br/> |**Exchange** <br/> |**Méthode de connexion au téléphone** <br/> |**Skype pour l’accès de l’entreprise** <br/> |**Accès à Exchange avec Auth. moderne et MFA activées** <br/> |**Accès à Exchange avec Auth. moderne et MFA désactivées** <br/> |
|En ligne  <br/> |En ligne  <br/> |Connexion Web  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|En ligne  <br/> |En ligne  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|En ligne  <br/> |Sur site  <br/> |Connexion Web  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |
|En ligne  <br/> |Sur site  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Authentification par code confidentiel  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |N/D  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Connexion via PC (BTOE)  <br/> |Oui  <br/> |Oui  <br/> |N/D  <br/> |
   
- **Fonctionnalités de téléphonie** Le jeu de fonctionnalités peut-être varier légèrement selon le partenaire de téléphone IP. Pour la fonctionnalité complète défini et pour plus d’informations sur les fonctionnalités pour chaque fournisseur, voir [Getting téléphones pour Skype pour Business Online](getting-phones-for-skype-for-business-online.md).
    
- **-Verrouillage du téléphone** est une fonctionnalité récemment introduite dans Skype pour les entreprises certifié téléphones qui est utilisé pour sécuriser un téléphone. Si activé, les utilisateurs devront créer un code confidentiel lorsque l’authentification réussit. Une fois créée, téléphones verrouillera lors de l’expiration du délai d’inactivité que vous définissez, un utilisateur verrouille manuellement son téléphone ou synchronisation leur verrouillage de téléphone avec leur verrouillage de PC à l’aide de jumelage de téléphone. Si le téléphone-verrouiller le code confidentiel est entré incorrect plusieurs fois, le téléphone sera déconnecter l’utilisateur ou code l’administrateur du nécessaire pour déverrouiller le téléphone, mais cette valeur peut varier selon le partenaire de téléphone. Code confidentiel de l’utilisateur doit être entre 6 et 15 chiffres.
    
    Vous pouvez désactiver verrouillage de téléphone pour votre organisation (qui est activée par défaut), modifier le délai d’inactivité et choisir si les utilisateurs peuvent effectuer des appels téléphoniques pendant qu’ils sont des paramètres intrabande verrouillés ou non à l’aide. Pour plus de détails sur ces paramètres, consultez [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Étape 7 : si vous disposez du couplage d'appareil et de Better Together over Ethernet (BToE) (facultatif)
<a name="BK_BTOE"> </a>

BToE est un téléphone paining mécanisme pour les téléphones IP partenaire qui associe le téléphone d’un utilisateur avec leurs Skype Windows pour l’application de gestion. BToE permet aux utilisateurs d'effectuer les actions suivantes :
  
- Se connecter à leur téléphone IP à l’aide de leur Skype pour l’application de gestion du bureau (à l’aide d’un PC)
    
- Synchroniser verrouillage de téléphone avec verrouillage PC
    
- Cliquer pour appeler
    
BToE peut être configuré pour fonctionner en deux modes : *manuel* et *automatique* (par défaut). Il peut également être activé (par défaut)/désactivé pour les utilisateurs utilisant les paramètres intrabande de Skype Entreprise. En mode *manuel*  , les utilisateurs doivent réaliser une étape supplémentaire pour coupler leur téléphone avec leur application Windows.
  
 **Pour déployer BToE aux utilisateurs**
  
1. Connectez leur PC à leur téléphone à l'aide du port du PC.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Téléchargez et installez la dernière version du logiciel BToE à partir du site Web du fabricant disponible en cliquant sur les liens ci-dessous. Pour une expérience utilisateur optimale, vous pouvez distribuer et installer le logiciel BToE à l'aide d'une solution de distribution d'administrateur, telle que System Center Configuration Manager (SCCM). Pour obtenir de l'aide pour utiliser SCCM, reportez-vous à la page [Packages et programmes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).
    
   - [Site de téléchargement de logiciels Polycom BToE](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Téléchargement du logiciel BToE pour Yealink](http://www.yealink.com/products_list_10.html)
    
   - [Téléchargement du logiciel BToE pour AudioCodes](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. Le paramètre du serveur pour BToE est défini sur **activé** et **mode automatique** par défaut. Pour modifier ces paramètres, voir [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> BToE n'est actuellement pas disponible sur les plates-formes Mac et VDI. 
  
## <a name="related-topics"></a>Rubriques connexes
[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Voici les avantages du système téléphonique dans Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
