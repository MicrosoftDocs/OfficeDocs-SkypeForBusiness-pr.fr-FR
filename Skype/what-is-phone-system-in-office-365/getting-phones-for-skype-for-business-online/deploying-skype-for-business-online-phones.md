---
title: "Déploiement de téléphones Skype Entreprise Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
description: "Learn the deployment steps to get the correct firmware, update it if needed, assign licences, and configure settings for Skype for Business online phones"
---

# Déploiement de téléphones Skype Entreprise Online

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](faa17eb3-7483-4984-87f2-815d981b68ae.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/faa17eb3-7483-4984-87f2-815d981b68ae). 
  
Ce guide de déploiement vous aidera à déployer des téléphones IP Skype Entreprise Online.
  
Dans tous les types d'activités, ayant un numéro de téléphone permet aux utilisateurs passer et obtenir des appels vocaux, et il est un impératif à travailler. Les utilisateurs qui ont des numéros de téléphone seront en mesure d'effectuer des appels vocaux sur tous les périphériques Skype Entreprise, y compris les téléphones IP, les PC et les appareils mobiles. Vous pouvez en savoir plus sur Skype pour les téléphones IP d'entreprise en lisant l'article [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).
  
## Étapes de déploiement pour les téléphones IP

### Étape 1 : télécharger les guides de l'administrateur et les manuels de téléphone du fabricant

Avant de commencer, il est pertinent de télécharger les guides d'administration et les manuels de téléphone du fabricant.
  
- Dans le cas de téléphones Polycom, consultez le guide [Polycom Deployment Guide](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl).
    
- Pour les téléphones Yealink, voir [Yealink Skype entreprise HD SIP téléphones solution](http://www.yealink.com/solution_7.mdl).
    
- Dans le cas de téléphones AudioCodes, consultez le guide [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/products/ems).
    
### Étape 2 : vérifier que votre achat ou migration concerne un téléphone IP et un microprogramme pris en charge par Skype Entreprise

Un Skype entreprise Online pris en charge téléphone et microprogramme est également compatible pour Skype entreprise Server, mais l'inverse n'est pas toujours true. Pour vous assurer que vous achetez ou mise en service d'un téléphone pris en charge et microprogramme, consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).
  
### Étape 3 : vérifier que le microprogramme adéquat est installé et le mettre à jour si nécessaire

Vérifier la version de microprogramme sur votre téléphone. Pour :
  
- **les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.
    
- **les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.
    
- **les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil.
    
    > [!NOTE]
    > Pour l'accès distant au numéro de téléphone, reportez-vous aux guides d'administration fabricant. Consultez les liens ci-dessus pour les guides utilisateur et manuels de téléphone. 
  
- **les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.
    
### Étape 4 : remarques sur la mise à jour de l'appareil

> [!NOTE]
> Microprogramme Polycom avant 5.5.1.X avait mécanisme de verrouillage de périphérique spécifiques au fabricant qui a été remplacé par une Skype pour implémentation d'une activité « Téléphone-verrou. » Mettre à niveau un téléphone 5.4.X.X qui a été sécurisé avec « Appareil-verrou » vers 5.5.1.X avec « Téléphone-verrou » ne hérite le code secret de « Appareil-verrou, « qui peut laisser le téléphone non sécurisé. Les utilisateurs qui ont activé « Verrouillage de périphérique » ont besoin activer le paramètre de profil du périphérique Polycom suivant donner aux utilisateurs de contrôle du temps de mise à niveau (lync.deviceUpdate.popUpSK.enabled=1). 
  
Mises à jour sont gérés par le Skype pour le Service Business. Chaque Skype entreprise certified microprogramme du téléphone est téléchargé dans la Skype pour mettre à jour le serveur et la mise à jour de l'appareil est activé par défaut sur tous les téléphones. En fonction de la durée d'inactivité sur le téléphone et les intervalles d'interrogation, téléphones seront automatiquement télécharger et installer les dernières versions certifiées. Vous pouvez désactiver les paramètres de mise à jour de périphérique en utilisant l'applet de commande [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) et en attribuant au paramètre _EnableDeviceUpdate_ `false`.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quand un nouveau microprogramme est disponible et prêt pour télécharger et installer, le téléphone vous avertit de l'utilisateur. Téléphones Polycom seront avertir l'utilisateur et lui fournir une option pour **mettre à jour** ou **différer**.
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Dans le cas d'un téléphone Polycom, vous pouvez mettre à jour le microprogramme en sélectionnant **SwUpdate (Mise à jour logicielle)**.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Vous pouvez également gérer les mises à jour du microprogramme à l'aide d'un système de provisionnement partenaire. Pour plus d'informations sur la gestion de système de provisionnement partenaire, notamment la personnalisation de téléphone avancée, consultez les guide d'administration du fabricant.
  
> [!CAUTION]
> Veillez à disposer d'une seule autorité de mise à jour pour l'appareil (mise à jour intrabande ou serveur de provisionnement tiers) pour éviter toute boucle de mise à jour. 
  
### Étape 5 : paramètres de Configuration et infrastructure téléphone

Vous pouvez configurer les options et stratégies téléphoniques les plus utilisées à l'aide d'applets de commande Windows PowerShell de gestion intrabande pour Skype Entreprise. Consultez le lien [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) pour plus de détails sur ces paramètres.
  
Pour la planification de l'infrastructure réseau, voir [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### Étape 6 : préparation d'utilisateurs à se connecter

Pour permettre aux utilisateurs de se connecter à un Skype pour téléphone entreprise Online correctement et passer des appels, vous avez besoin pour vous assurer que les utilisateurs sont attribués les licences corrects. Au minimum, vous avez besoin d'attribuer une licence système téléphonique et un Plan d'appel. Pour plus d'informations, vous constatez [Skype pour les entreprises et Microsoft Teams module complémentaire licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) et[Attribuez Skype pour les entreprises et Microsoft Teams des licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Vous pouvez trouver plus d'informations sur l'appel d'offre en lisant [Quelle est l'appel d'offre dans Office 365 ?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
  
- Les **options de connexion** disponibles pour les utilisateurs Online sont les suivantes :
    
  - Les utilisateurs dotés des téléphones **VVX Polycom 5XX/6XX** seront affiche :
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Les utilisateurs dotés des téléphones **Yealink T48G/T46G** seront affiche :
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Pour plus d'informations sur les options de connexion pris en charge par le fabricant, consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).
    
- **ID d'utilisateur** À l'aide de leur clavier téléphonique ou de leur clavier visuel (le cas échéant), les utilisateurs peuvent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. : *amosm@contoso.com*  pour leur nom d'utilisateur.
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > L'authentification par code confidentiel n'est pas prise en charge par Skype Entreprise Online avec les téléphones LPE et PIP (Partner IP Phone). 
  
- **À l'aide d'un PC** Lorsque parfaite sur logiciel Ethernet (BToE) est installé sur l'ordinateur de l'utilisateur et activée, les utilisateurs peuvent se connecter à leur téléphone à l'aide de la fenêtre d'authentification sur leurs Windows Skype entreprise App. Pour plus d'informations, voir[Étape 7 : si vous disposez du couplage d'appareil et de Better Together over Ethernet (BToE) (facultatif)](faa17eb3-7483-4984-87f2-815d981b68ae.md#BK_BTOE) .
    
    > [!NOTE]
    > Les utilisateurs doivent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. :  *amosm@contoso.com*  pour leur nom d'utilisateur.
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **À l'aide une connexion WebPart**: il s'agit d'une nouvelle méthode pour les utilisateurs en ligne s'authentifier à l'aide d'un navigateur web standard. Les utilisateurs seront fournies dans un jeu d'instructions à suivre lorsqu'ils utilisent un navigateur pour vous connecter.
    
  - Les utilisateurs dotés des téléphones **VVX Polycom 5XX/6XX** seront affiche :
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Les utilisateurs dotés des téléphones **Yealink T48G/T46G** seront affiche :
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    Le code est généré va expirer en seulement 15 minutes. Lorsqu'il arrive à expiration, l'utilisateur a peut-être cliquer sur **recommencer** ou sur **OK** pour générer un nouveau code, selon le téléphone.
    
  - Les utilisateurs dotés des téléphones **VVX Polycom 5XX/6XX** seront affiche :
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Les utilisateurs dotés des téléphones **Yealink T48G/T46G** seront affiche :
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    À l'aide d'un navigateur, accédez à l'adresse affichée dans le téléphone et saisissez votre nom d'utilisateur Skype Entreprise.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Entrez le code qui s'affiche sur le téléphone.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Vérifiez que le site affiche « [nom du fabricant de téléphone] **Skype entreprise Certified Phone**, » et cliquez sur **Continuer**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Cliquez sur les informations de connexion de l'utilisateur ou sur **Use another account (Utiliser un autre compte)**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    La page suivante qui s'affiche, il est possible sans fermer le navigateur.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Les téléphones LPE pour Skype Entreprise Online prennent en charge la connexion via un périphérique USB uniquement. 
  
- **Déploiements pris en charge** Le tableau ci-après indique les types d'authentification pris en charge pour les modèles de déploiement actuellement pris en charge, y compris l'intégration d'Exchange, l'authentification moderne avec Multi-factor Authentication (MFA), et Skype Entreprise Online sur site.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype Entreprise** <br/> |**Exchange** <br/> |**Méthode de connexion au téléphone** <br/> |**Skype pour l'accès d'entreprise** <br/> |**Accès à Exchange avec Auth. moderne et MFA activées** <br/> |**Accès à Exchange avec Auth. moderne et MFA désactivées** <br/> |
|En ligne  <br/> |En ligne  <br/> |Connexion Web  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |
|En ligne  <br/> |En ligne  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|En ligne  <br/> |Sur site  <br/> |Connexion Web  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |
|En ligne  <br/> |Sur site  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |Non  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Authentification de code confidentiel  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Nom d'utilisateur/Mot de passe  <br/> |Oui  <br/> |Oui  <br/> |N/A  <br/> |
|Sur site  <br/> |En ligne/sur site  <br/> |Connexion via PC (BTOE)  <br/> |Oui  <br/> |Oui  <br/> |N/A  <br/> |
   
- **Fonctionnalités de téléphone** L'ensemble des fonctionnalités peut-être varier légèrement en fonction du partenaire téléphone IP. La fonctionnalité complète définissez et pour plus d'informations sur les fonctionnalités de chaque fabricant du téléphone, voir[Obtention de numéros de téléphone pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).
    
- **Téléphone verrou** est une fonctionnalité récemment introduite dans Skype entreprise certifié téléphones qui est utilisé pour sécuriser un téléphone. Si activé, les utilisateurs seront invités à créer un code confidentiel si celle-ci est réussie. Une fois créé, téléphones verrouille lorsque le délai d'inactivité que vous définissez arrive à expiration, un utilisateur verrouille manuellement leur téléphone ou qu'ils synchroniser leur téléphone-verrou avec leur verrou PC à l'aide de téléphone le jumelage. Si le code confidentiel téléphone verrou est entré incorrect plusieurs fois, le téléphone doit soit déconnexion de l'utilisateur ou code d'un administrateur nécessaire pour déverrouiller le téléphone, mais cette valeur peut varier selon le partenaire téléphone. Code confidentiel de l'utilisateur doit être comprise entre 6 et 15 chiffres.
    
    Vous pouvez désactiver le téléphone verrouiller pour votre organisation (qui est activée par défaut), modifier le d'inactivité et choisir si les utilisateurs peuvent effectuer des appels téléphoniques lorsqu'ils sont verrouillées ou pas à l'aide des intrabande-paramètres. Pour plus d'informations sur ces paramètres, voir [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) .
    
## Étape 7 : si vous disposez du couplage d'appareil et de Better Together over Ethernet (BToE) (facultatif)
<a name="BK_BTOE"> </a>

BToE est un téléphone paining mécanisme de partenaire IP téléphones que paires de téléphone d'un utilisateur avec leurs Skype Windows pour les entreprises App BToE permet aux utilisateurs de :
  
- Se connecter à leur téléphone IP à l'aide de leur Skype entreprise App bureau (en utilisant un PC)
    
- Synchroniser téléphone verrouiller avec verrouillage PC
    
- Cliquer pour appeler
    
BToE peut être configuré pour fonctionner de deux manières :  *automatique*  (par défaut) et *manuel*  . Il peut également être activée (valeur par défaut) / désactivé pour les utilisateurs à l'aide de Skype pour les paramètres des intrabande entreprise. Lorsqu'il fonctionne en mode *manuel*  , les utilisateurs devront effectuer une étape supplémentaire pour associer leur téléphone avec son application Windows.
  
 **Déploiement BToE aux utilisateurs**
  
1. Connectez leur PC à leur téléphone à l'aide du port du PC.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Téléchargez et installez la dernière version du logiciel BToE à partir du site Web du fabricant disponible en cliquant sur les liens ci-dessous. Pour une expérience utilisateur optimale, vous pouvez distribuer et installer le logiciel BToE à l'aide d'une solution de distribution d'administrateur, telle que System Center Configuration Manager (SCCM). Pour obtenir de l'aide pour utiliser SCCM, reportez-vous à la page [Packages et programmes dans System Center Configuration Manager](https://docs.microsoft.com/fr-fr/sccm/apps/deploy-use/packages-and-programs).
    
  - [Site de téléchargement du logiciel Polycom BToE](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl)
    
  - [Téléchargement du logiciel BToE pour Yealink](http://www.yealink.com/solution_info.aspx?ProductsCateID=1471&amp;parentcateid=1471&amp;cateid=1471&amp;BaseInfoCateId=1328&amp;Cate_Id=1471)
    
  - [Téléchargement du logiciel BToE pour AudioCodes](ftp://VoP-C12:IPPLync@ftp.audiocodes.com/Release/3.0.0.Beta/BToE_1.1.8/)
    
3. Le paramètre du serveur pour BToE est défini sur **activé** et **mode automatique** par défaut. Pour modifier ces paramètres, voir[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> BToE n'est actuellement pas disponible sur les plates-formes Mac et VDI. 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

