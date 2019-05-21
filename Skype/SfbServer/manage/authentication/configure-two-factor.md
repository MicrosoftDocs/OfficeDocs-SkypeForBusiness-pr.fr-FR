---
title: Configurer l’authentification à deux facteurs dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Résumé: configuration de l’authentification à deux facteurs dans Skype entreprise Server.'
ms.openlocfilehash: 91a8929b89a584b116f1c7ec9313daa2fe679fd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283839"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurer l’authentification à deux facteurs dans Skype entreprise Server

**Résumé:** Configurer l’authentification à deux facteurs dans Skype entreprise Server.

Les sections ci-dessous décrivent la procédure de configuration de l’authentification à deux facteurs pour votre déploiement. Pour plus d’informations sur l’authentification à deux facteurs, voir [activation de l’authentification multifacteur Office 365 pour les administrateurs en ligne](https://go.microsoft.com/fwlink/p/?LinkId=313332)

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce

La procédure ci-dessous décrit la configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce :

Pour plus d’informations sur l’installation d’une autorité de certification racine d’entreprise, voir [installer une autorité de certification racine d’entreprise](https://go.microsoft.com/fwlink/p/?LinkID=313364).

1. Connectez-vous à l’ordinateur de l’autorité de certification d’entreprise à l’aide d’un compte d’administrateur de domaine.

2. Lancez le gestionnaire système, puis vérifiez que le rôle Inscription de l’autorité de certification par le biais du web est installé.

3. Dans le menu **Outils d’administration**, ouvrez la console de gestion **Autorité de certification**.

4. Dans le volet de navigation, développez **Autorité de certification**.

5. Cliquez avec le bouton droit sur **Modèles de certificat**, sélectionnez **Nouveau**, puis **Modèle de certificat à délivrer**.

6. Sélectionnez **Agent d’inscription**, **Utilisateur de carte à puce** et **Connexion par carte à puce**.

7. Cliquez sur **OK**.

8. Cliquez avec le bouton droit sur **Modèles de certificat**.

9. Sélectionnez **Gérer**.

10. Ouvrez les propriétés du modèle utilisateur de carte à puce.

11. Cliquez sur l’onglet **Sécurité**.

12. Modifiez les autorisations, comme suit :

    - Ajoutez des comptes Active Directory d’utilisateurs individuels avec les autorisations Lire/Inscrire (Autoriser) ou

    - Ajoutez un groupe de sécurité contenant des utilisateurs de carte à puce avec les autorisations Lire/Inscrire (Autoriser) ou

    - Ajoutez le groupe Utilisateurs du domaine avec les autorisations Lire/Inscrire (Autoriser).

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configuration de Windows 8 pour les cartes à puce virtuelles

Le coût de mise en œuvre est l’un des facteurs à prendre en compte dans le cadre du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce. Windows 8 fournit un certain nombre de nouvelles fonctionnalités de sécurité et l’une des nouvelles fonctionnalités les plus intéressantes est la prise en charge des cartes à puce virtuelles.

Pour les ordinateurs équipés d’une puce de module de plateforme sécurisée conforme à la spécification version 1.2, les organisations peuvent désormais tirer parti des avantages d’une ouverture de session par carte à puce sans investissement matériel supplémentaire. Pour plus d’informations, reportez-vous [à la rubrique utilisation de cartes à puce virtuelles avec Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Configuration de Windows 8 pour les cartes à puce virtuelles

1. Connectez-vous à l’ordinateur Windows 8 à l’aide des informations d’identification d’un utilisateur Skype entreprise.

2. Dans l’écran d’accueil de Windows 8, déplacez votre curseur dans le coin droit inférieur de l’écran.

3. Sélectionnez l’option **Rechercher** , puis cliquez sur Rechercher forCommand invite.

4. Cliquez avec le bouton droit sur **Invite de commandes**, puis sélectionnez **Exécuter en tant qu’administrateur**.

5. Ouvrez la console de gestion du module de plateforme sécurisée en exécutant la commande suivante :

  ```
  Tpm.msc
  ```

6. À partir de la console de gestion du module de plateforme sécurisée, vérifiez que la spécification du module de plateforme sécurisée correspond à la version 1.2 au minimum.

    > [!NOTE]
    > Si un message indiquant qu’aucun module de plateforme sécurisée compatible n’a été trouvé, vérifiez que l’ordinateur dispose d’un module de plateforme sécurisée compatible et que celui-ci est activé dans le BIOS système.

7. Fermez la console de gestion du module de plateforme sécurisée.

8. Dans l’invite de commandes, créez une carte à puce virtuelle à l’aide de la commande suivante :

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > Pour indiquer une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez plutôt l’invite /pin.

9. Dans l’invite de commandes, ouvrez la console de gestion de l’ordinateur en exécutant la commande suivante :

  ```
  CompMgmt.msc
  ```

10. Dans la console de gestion de l’ordinateur, sélectionnez **Gestion des périphériques**.

11. Développez **Lecteurs de cartes à puce**.

12. Vérifiez que le lecteur de cartes à puce virtuelles a bien été créé.

## <a name="enroll-users-for-smart-card-authentication"></a>Inscription d’utilisateurs pour l’authentification par carte à puce

Deux méthodes permettent d’inscrire les utilisateurs pour l’authentification par carte à puce. La méthode la plus simple consiste à faire s’inscrire directement les utilisateurs pour l’authentification par carte à puce par l’inscription par le biais du web. La méthode la plus complexe implique d’utiliser un agent d’inscription. Cette rubrique décrit l’inscription automatique pour les certificats de carte à puce.

Pour plus d’informations sur l’inscription au nom des utilisateurs en tant qu’agent d’inscription, voir [inscrire des certificats pour le compte d’autres utilisateurs](https://go.microsoft.com/fwlink/p/?LinkID=313367).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Inscription des utilisateurs pour l’authentification par carte à puce

1. Connectez-vous à la station de travail Windows 8 en utilisant les informations d’identification d’un utilisateur compatible Skype entreprise.

2. Lancez Internet Explorer.

3. Accédez à la page d’inscription sur le Web de l' **autorité** de https://MyCA.contoso.com/certsrv)certification (par exemple,.

    > [!NOTE]
    > Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site web en mode de compatibilité.

4. Dans la page **Bienvenue**, sélectionnez **Demander un certificat**.

5. Sélectionnez ensuite **Demande avancée**.

6. Sélectionnez **Créer et envoyer une demande de requête auprès de cette autorité de certification**.

7. Sélectionnez **Utilisateur de carte à puce** sous la section **Modèle de certificat**, puis remplissez la demande de certificat avancée avec les valeurs suivantes :

  - Sous **Options des clés**, vérifiez que les paramètres suivants sont sélectionnés :

    - Sélectionnez la case d’option **Créer un jeu de clés**.

    - Dans **Fournisseur de services de chiffrement**, sélectionnez **Fournisseur de services de chiffrement Microsoft pour carte à puce**.

    - Dans **Utilisation de la clé**, sélectionnez **Exchange** (seule option disponible).

    - Dans **Taille de la clé**, entrez 2048.

    - Vérifiez que l’option **Nom de conteneur de clé automatique** est sélectionnée.

    - Laissez les autres cases à cocher désactivées.

  - Sous **Options supplémentaires**, vérifiez que les valeurs suivantes sont sélectionnées :

    - Dans **Format de la demande**, sélectionnez **CMC**.

    - Dans **Algorithme de hachage**, sélectionnez **sha1**.

    - Pour **nom convivial** enterSmardcard certificat.

8. Si vous utilisez un lecteur de cartes à puces physiques, insérez la carte à puce dans l’appareil.

9. Cliquez sur **Envoyer** pour envoyer la demande de certificat.

10. Lorsque vous y êtes invité, entrez le code confidentiel utilisé pour créer la carte à puce virtuelle.

    > [!NOTE]
    > La valeur du code confidentiel de carte à puce virtuelle par défaut est «12345678».

11. Une fois le certificat émis, cliquez sur **Installer ce certificat** pour terminer la procédure d’inscription.

    > [!NOTE]
    >  Si votre demande de certificat échoue avec l’erreur «ce navigateur Web ne prend pas en charge la génération de demandes de certificat», il existe trois façons de résoudre le problème:

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configuration d’Active Directory Federation Services (AD FS 2.0)

Cette section décrit la configuration d’Active Directory Federation Services (AD FS 2.0) pour prendre en charge l’authentification multifacteur. Pour plus d’informations sur l’installation de la 2,0 AD FS, voir [instructions pas à pas sur AD fs 2,0 et guide](https://go.microsoft.com/fwlink/p/?LinkId=313374).

> [!NOTE]
> Lorsque vous installez AD FS 2.0, vous ne devez pas utiliser le Gestionnaire de serveur Windows pour ajouter le rôle Active Directory Federation Services. Au lieu de cela, téléchargez et installez le [package 2,0 de services ADFS (Active Directory Federation Services](https://go.microsoft.com/fwlink/p/?LinkId=313375)).

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Pour configurer AD FS pour l’authentification à deux facteurs

1. Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.

2. Lancez Windows PowerShell.

3. À partir de la ligne de commande Windows PowerShell, exécutez la commande suivante :

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Établissez un partenariat avec chaque serveur pour lequel l’authentification passive sera activée, en exécutant la commande ci-dessous, en remplaçant le nom du serveur propre à votre déploiement :

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Dans le menu Outils d’administration, lancez la console de gestion AD FS 2.0.

6. Développez **relations d’approbation** > de confiance entre les**parties**.

7. Vérifiez qu’une nouvelle approbation a été créée pour votre serveur Skype entreprise.

8. Créez et affectez une règle d’autorisation d’émission pour votre relation d’approbation de la partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Créez et affectez une règle de transformation d’émission pour votre relation d’approbation de la partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur votre relation d’approbation de la partie de confiance, puis sélectionnez **Modifier les règles de revendication**.

11. Sélectionnez l’onglet **Règles d’autorisation d’émission**, puis vérifiez que la règle d’autorisation a été correctement créée.

12. Sélectionnez l’onglet **Règles de transformation d’émission**, puis vérifiez que la règle de transformation d’émission a été créée correctement.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configuration d’AD FS 2.0 pour prendre en charge l’authentification du client

Deux types d’authentifications peuvent être configurés pour permettre à AD FS 2.0 de prendre en charge l’authentification à l’aide de cartes à puce :

- Authentification basée sur les formulaires

- Authentification de client TLS (Transport Layer Security)

L’authentification basée sur les formulaires permet de développer une page web permettant aux utilisateurs de s’authentifier à l’aide de leur nom d’utilisateur et de leur mot de passe ou de leur carte à puce et de leur code confidentiel. Cette rubrique décrit la mise en œuvre de l’authentification de client TLS (Transport Layer Security) avec AD FS 2.0. Pour plus d’informations sur les types d’authentifications 2,0 d’AD FS, voir [ad fs 2,0: Comment changer le type d’authentification locale](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Pour configurer AD FS 2.0 pour prendre en charge l’authentification du client

1. Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.

2. Lancez l’Explorateur Windows.

3. Accédez à C:\inetpub\adfs\ls.

4. Effectuez une copie de sauvegarde du fichier web.config existant.

5. Ouvrez le fichier web.config existant à l’aide du Bloc-notes.

6. Dans la barre de menus, sélectionnez **Edition**, puis **Rechercher**.

7. Recherchez \<localAuthenticationTypes\>.

    Quatre types d’authentification s’affichent (un par ligne).

8. Déplacez la ligne contenant le type d’authentification TLSClient au début de la liste dans la section.

9. Enregistrez et fermez le fichier web.config.

10. Lancez une invite de commandes avec des droits élevés.

11. Redémarrez IIS en exécutant la commande suivante :

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configuration de l’authentification passive Skype Entreprise Server

La section suivante décrit comment configurer Skype entreprise Server pour prendre en charge l’authentification passive. Dès qu’il est activé, les utilisateurs dotés de l’authentification à deux facteurs doivent utiliser une carte à puce physique ou virtuelle et un code confidentiel valide pour se connecter à l’aide du client Skype entreprise.

> [!NOTE]
> Il est vivement recommandé que les clients activent l’authentification passive pour les services Serveur d’inscriptions et web au niveau du service. L’activation au niveau global risquerait de provoquer des échecs d’authentification à l’échelle de l’organisation pour les utilisateurs qui ne se connectent pas avec le client de bureau pris en charge.

### <a name="web-service-configuration"></a>Configuration des services web

La procédure ci-dessous décrit la création d’une configuration de service web personnalisée pour les directeurs, les pools d’entreprise et les serveurs Standard Edition pour lesquels l’authentification passive sera activée.

### <a name="to-create-a-custom-web-service-configuration"></a>Pour créer une configuration de service web personnalisée

1. Connectez-vous à votre serveur frontal Skype entreprise Server à l’aide d’un compte d’administrateur Skype entreprise.

2. Lancez Skype entreprise Server Management Shell.

3. À partir de la ligne de commande de Skype entreprise Server Management Shell, créez une nouvelle configuration de service Web pour chaque directeur, pool d’entreprise et serveur Standard Edition qui sera activé pour l’authentification passive en exécutant la commande suivante:

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > La valeur du nom de domaine complet WsFedPassiveMetadataUri correspond au nom du service de fédération de votre serveur AD FS 2.0. Pour consulter la valeur Nom du service de fédération dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur **Service** dans le volet de navigation, puis sélectionnez **Modifier les propriétés du service de fédération**.

4. Vérifiez que les valeurs UseWsFedPassiveAuth et WsFedPassiveMetadataUri ont été définies correctement en exécutant la commande suivante :

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Pour les clients, l’authentification passive est la méthode d’authentification la moins privilégiée pour l’authentification de ticket web. Pour tous les directeurs, les pools d’entreprise et les serveurs Standard Edition qui seront activés pour l’authentification passive, tous les autres types d’authentification doivent être désactivés dans Skype entreprise Web services en exécutant l’applet de commande suivante:

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Vérifiez que tous les autres types d’authentification ont été désactivés correctement en exécutant l’applet de commande suivante :

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Configuration du serveur proxy

Lorsque l’authentification par certificat est désactivée pour les services Web Skype entreprise, le client Skype entreprise utilise un type d’authentification moins favori, tel que Kerberos ou NTLM, pour s’authentifier auprès du service d’inscription. Si l’authentification par certificat est toujours requise pour autoriser le client à extraire un ticket web, Kerberos et NTLM doivent tout de même être désactivés pour le service Serveur d’inscriptions.

La procédure ci-dessous décrit la création d’une configuration de proxy personnalisée pour les pools Edge, les pools d’entreprise et les serveurs Standard Edition pour lesquels l’authentification passive sera activée.

### <a name="to-create-a-custom-proxy-configuration"></a>Pour créer une configuration de proxy personnalisée

1. À partir de la ligne de commande de l’interpréteur de commandes de Skype entreprise Server Management Shell, créez une nouvelle configuration de proxy pour chaque pool de périphériques de type «pool d’entreprise» et serveur standard pour l’authentification passive en exécutant ce qui suit: disponibles

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Vérifiez que tous les autres types d’authentification proxy ont été désactivés correctement en exécutant la commande suivante :

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Voir aussi

[Gestion de l’authentification à deux facteurs dans Skype entreprise Server](two-factor-authentication.md)

[Utiliser l’authentification à deux facteurs avec le client Skype entreprise et Skype entreprise Server](use-two-factor.md)
