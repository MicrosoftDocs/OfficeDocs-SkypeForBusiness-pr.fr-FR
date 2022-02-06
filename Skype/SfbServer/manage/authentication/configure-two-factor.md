---
title: Configurer l’authentification à deux facteurs dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Résumé : Configurez l’authentification à deux facteurs dans Skype Entreprise Server.'
---

# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Configurer l’authentification à deux facteurs dans Skype Entreprise Server

**Résumé :** Configurez l’authentification à deux facteurs dans Skype Entreprise Server.

Les sections suivantes décrivent les étapes nécessaires pour configurer l’authentification à deux facteurs pour votre déploiement. Pour plus d’informations sur l’authentification à deux facteurs, voir [Activation Office 365'authentification multifacteur pour les administrateurs en ligne - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurer une autorité de Enterprise racine pour prendre en charge l’authentification par carte à puce

Les étapes suivantes décrivent comment configurer une Enterprise racine pour prendre en charge l’authentification par carte à puce :

Pour plus d’informations sur l’installation d’Enterprise’autorité de certification racine, voir [Install an Enterprise Root Certification Authority](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10)).

1. Connectez-vous à l’Enterprise de l’ac à l’aide d’un compte d’administrateur de domaine.

2. Lancez system manager et vérifiez que le rôle d’inscription web de l’autorité de certification est installé.

3. Dans le menu **Outils d’administration** , ouvrez la console de gestion **de l’autorité** de certification.

4. Dans le volet de navigation, développez **Autorité de certification**.

5. Cliquez avec le bouton **droit sur Modèles de certificats**, **sélectionnez Nouveau**, puis **sélectionnez Modèle de certificat à émettre**.

6. Sélectionnez **Agent d’inscription**, **Utilisateur à puce** et **Logo par carte à puce**.

7. Cliquez sur **OK**.

8. Cliquez avec le bouton droit **sur Modèles de certificats**.

9. Sélectionnez **Gérer**.

10. Ouvrez les propriétés du modèle Utilisateur à puce.

11. Cliquez sur **l’onglet** Sécurité.

12. Modifiez les autorisations comme suit :

    - Ajouter des comptes AD d’utilisateur individuels avec des autorisations de lecture/inscription (autoriser) ou

    - Ajouter un groupe de sécurité contenant des utilisateurs de carte à puce avec des autorisations de lecture/inscription (autoriser) ou

    - Ajouter le groupe Utilisateurs du domaine avec des autorisations de lecture/inscription (autoriser)

## <a name="configure-windows-8-for-virtual-smart-cards"></a>Configurer les Windows 8 pour les cartes à puce virtuelles

Un facteur à prendre en compte lors du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce est le coût d’implémentation. Windows 8 offre un certain nombre de nouvelles fonctionnalités de sécurité, et l’une des nouvelles fonctionnalités les plus intéressantes est la prise en charge des cartes à puce virtuelles.

Pour les ordinateurs équipés d’une puce de module de plateforme de confiance (TPM) qui répond aux spécifications de la version 1.2, les organisations peuvent désormais profiter des avantages de l’accès par carte à puce sans effectuer d’investissements supplémentaires en matériel. Pour plus d’informations, [voir Utilisation de cartes à puce virtuelles Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Pour configurer la Windows 8 pour les cartes à puce virtuelles

1. Connectez-vous à l Windows 8 à l’aide des informations d’identification d’Skype Entreprise utilisateur activé.

2. À l Windows 8 l’écran d’accueil, déplacez votre curseur dans le coin inférieur droit de l’écran.

3. Sélectionnez **l’option** Rechercher, puis recherchezCommand Prompt.

4. Cliquez avec le bouton droit **sur l’invite** de commandes, puis **sélectionnez Exécuter en tant qu’administrateur**.

5. Ouvrez la console de gestion du module de plateforme fiable (TPM) en exécutant la commande suivante :

   ```console
   Tpm.msc
   ```

6. À partir de la console de gestion du TPM, vérifiez que la version de spécification du TPM est au moins 1.2

    > [!NOTE]
    > Si vous recevez une boîte de dialogue indiquant qu’un module de plateforme de confiance compatible (TPM) est incohable, vérifiez que l’ordinateur dispose d’un module TPM compatible et qu’il est activé dans le BIOS système.

7. Fermer la console de gestion du TPM

8. À partir de l’invite de commandes, créez une carte à puce virtuelle à l’aide de la commande suivante :

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

   > [!NOTE]
   > Pour fournir une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez /pin prompt à la place.

9. À partir de l’invite de commandes, ouvrez la console gestion de l’ordinateur en exécutant la commande suivante :

  ```console
  CompMgmt.msc
  ```

10. Dans la console Gestion de l’ordinateur, sélectionnez **Gestion des périphériques**.

11. Développez **les lecteurs de carte à puce**.

12. Vérifiez que le nouveau lecteur de carte à puce virtuel a été créé avec succès.

## <a name="enroll-users-for-smart-card-authentication"></a>Inscrire des utilisateurs pour l’authentification par carte à puce

Il existe généralement deux méthodes pour inscrire des utilisateurs pour l’authentification par carte à puce. La méthode la plus simple consiste à faire en sorte que les utilisateurs s’inscrivent directement pour l’authentification par carte à puce à l’aide de l’inscription web, tandis que la méthode la plus complexe implique l’utilisation d’un agent d’inscription. Cette rubrique se concentre sur l’inscription automatique pour les certificats de carte à puce.

Pour plus d’informations sur l’inscription au nom des utilisateurs en tant qu’agent d’inscription, voir s’inscrire pour les [certificats au nom d’autres utilisateurs](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11)).

### <a name="to-enroll-users-for-smart-card-authentication"></a>Pour inscrire des utilisateurs pour l’authentification par carte à puce

1. Connectez-vous au Windows 8 de travail à l’aide des informations d’identification d’Skype Entreprise utilisateur activé.

2. Lancez Internet Explorer.

3. Accédez à **la page Inscription web de l’autorité** de certification (par exemple, https://MyCA.contoso.com/certsrv).

    > [!NOTE]
    > Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site web en mode de compatibilité.

4. Dans la page **d’accueil** , **sélectionnez Demander un certificat**.

5. Ensuite, sélectionnez **Demande avancée**.

6. **Sélectionnez Créer et envoyer une demande à cette ca**.

7. **Sélectionnez Utilisateur de carte à puce** sous **la section Modèle de** certificat et terminez la demande de certificat avancée avec les valeurs suivantes :

  - **Les options clés** confirment les paramètres suivants :

    - Sélectionnez la **bouton d’radio Créer un jeu de** touches

    - Pour **le fournisseur CSP**, sélectionnez **Microsoft Base Smart Card Crypto Provider**

    - Pour **l’utilisation** de **la clé, sélectionnez Exchange** (il s’agit de la seule option disponible).

    - Pour **la taille de clé**, entrez 2048

    - Confirmer que **le nom du conteneur de la clé automatique** est sélectionné

    - Laissez les autres cases désactivées.

  - Sous **Options supplémentaires,** confirmez les valeurs suivantes :

    - Pour **le format de demande,** **sélectionnez CMC**.

    - Pour **l’algorithme de hachage** , **sélectionnez sha1**.

    - For **Friendly Name** enterSmardcard Certificate.

8. Si vous utilisez un lecteur de carte à puce physique, insérez la carte à puce dans l’appareil.

9. Cliquez **sur Envoyer** pour envoyer la demande de certificat.

10. Lorsque vous y invitez, entrez le code confidentiel qui a été utilisé pour créer la carte à puce virtuelle.

    > [!NOTE]
    > La valeur par défaut du code confidentiel de carte à puce virtuelle est « 12345678 ».

11. Une fois le certificat émis, cliquez sur **Installer ce certificat** pour terminer le processus d’inscription.

    > [!NOTE]
    >  Si votre demande de certificat échoue avec l’erreur « Ce navigateur Web ne prend pas en charge la génération des demandes de certificat », il existe trois façons de résoudre le problème :
    >- Activer l’affichage de compatibilité dans Internet Explorer.
    >- Activez l’option Activer les paramètres intranet dans Internet Explorer.
    >- Sélectionnez le paramètre Réinitialiser toutes les zones au niveau par défaut sous l’onglet Sécurité dans le menu Options d’Internet Explorer.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Configurer les services de fédération Active Directory (AD FS 2.0)

La section suivante décrit comment configurer les services de fédération Active Directory (AD FS 2.0) pour prendre en charge l’authentification multifacteur. Pour plus d’informations sur l’installation d’AD FS 2.0, voir [AD FS 2.0 Step-by-Step and How To Guides](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).

> [!NOTE]
> Lors de l’installation d’AD FS 2.0, n’utilisez pas Windows Server Manager pour ajouter le rôle Services de fédération Active Directory. Téléchargez et installez plutôt les services [de fédération Active Directory](/troubleshoot/windows-server/identity/availability-description-afds).

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>Pour configurer AD FS pour l’authentification à deux facteurs

1. Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.

2. Démarrez Windows PowerShell.

3. À partir Windows PowerShell ligne de commande, exécutez la commande suivante :

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. Établissez un partenariat avec chaque serveur qui sera activé pour l’authentification passive en exécutant la commande suivante, en remplaçant le nom du serveur spécifique à votre déploiement :

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. Dans le menu Outils d’administration, lancez la console de gestion AD FS 2.0.

6. **Développez trust RelationshipsRelying** >  **Party Trusts**.

7. Vérifiez qu’une nouvelle confiance a été créée pour votre Skype Entreprise Server.

8. Créez et affectez une règle d’autorisation d’émission pour votre approbation de partie de confiance à l’Windows PowerShell en exécutant les commandes suivantes :

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Créez et affectez une règle de transformation d’émission pour votre confiance de partie de confiance à l’Windows PowerShell en exécutant les commandes suivantes :

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. Dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur votre confiance de partie de confiance, puis sélectionnez **Modifier les règles de revendication**.

11. Sélectionnez **l’onglet Règles d’autorisation** d’émission et vérifiez que la nouvelle règle d’autorisation a été correctement créée.

12. Sélectionnez **l’onglet Règles de transformation d’émission** et vérifiez que la nouvelle règle de transformation a été correctement créée.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>Configuration d’AD FS 2.0 pour prendre en charge l’authentification client

Il existe deux types d’authentification possibles qui peuvent être configurés pour permettre à AD FS 2.0 de prendre en charge l’authentification à l’aide de cartes à puce :

- Authentification basée sur les formulaires (FBA)

- Authentification du client transport Layer Security

À l’aide de l’authentification basée sur les formulaires, vous pouvez développer une page web qui permet aux utilisateurs de s’authentifier à l’aide de leur nom d’utilisateur/mot de passe ou de leur carte à puce et de leur code confidentiel. Cette rubrique se concentre sur l’implémenter l’authentification client de couche transport avec AD FS 2.0. Pour plus d’informations sur les types d’authentification AD FS 2.0, voir [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>Pour configurer AD FS 2.0 pour prendre en charge l’authentification client

1. Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.

2. Lancez Windows Explorer.

3. Accédez à C:\inetpub\adfs\ls

4. Effectuer une copie de sauvegarde du fichier web.config existant.

5. Ouvrez le fichier web.config existant à l’aide Bloc-notes.

6. Dans la barre de menus, **sélectionnez Modifier** , puis **Rechercher**.

7. Recherchez \<localAuthenticationTypes\>.

    Notez que quatre types d’authentification sont répertoriés, un par ligne.

8. Déplacez la ligne contenant le type d’authentification TLSClient en haut de la liste dans la section.

9. Enregistrez et fermez web.config fichier.

10. Lancez une invite de commandes avec des privilèges élevés.

11. Redémarrez les services Internet (IIS) en exécutant la commande suivante :

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Configuration de l Skype Entreprise Server passive

La section suivante décrit comment configurer les Skype Entreprise Server pour prendre en charge l’authentification passive. Une fois l’authentification activée, les utilisateurs activés pour l’authentification à deux facteurs doivent utiliser une carte à puce physique ou virtuelle et un code confidentiel valide pour se connecter à l’aide du client Skype Entreprise client.

> [!NOTE]
> Il est vivement recommandé que les clients activent l’authentification passive pour le serveur d’inscriptions et les services Web au niveau du service. Si l’authentification passive est activée pour le serveur d’inscriptions et les services Web au niveau global, elle entraîne probablement des échecs d’authentification à l’échelle de l’organisation pour les utilisateurs qui ne se sont pas signés avec le client de bureau pris en charge.

### <a name="web-service-configuration"></a>Web Service Configuration

Les étapes suivantes décrivent comment créer une configuration de service web personnalisée pour les directeurs, les pools Enterprise et les serveurs Édition Standard qui seront activés pour l’authentification passive.

### <a name="to-create-a-custom-web-service-configuration"></a>Pour créer une configuration de service web personnalisée

1. Connectez-vous à votre Skype Entreprise Server frontal à l’aide d’un Skype Entreprise administrateur.

2. Lancez le Skype Entreprise Server Management Shell.

3. À partir de la ligne de commande Skype Entreprise Server Management Shell, créez une configuration de service Web pour chaque directeur, pool Enterprise et serveur Édition Standard qui sera activé pour l’authentification passive en exécutant la commande suivante :

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

   > [!CAUTION]
   > La valeur du nom de domaine complet WsFedPassiveMetadataUri est le nom du service de fédération de votre serveur AD FS 2.0. La valeur Nom du service de fédération se trouve dans la console de gestion AD FS 2.0 en cliquant avec le bouton droit sur **Service** dans le volet de navigation, puis en sélectionnant Modifier les propriétés du **service** de fédération.

4. Vérifiez que les valeurs UseWsFedPassiveAuth et WsFedPassiveMetadataUri ont été définies correctement en exécutant la commande suivante :

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. Pour les clients, l’authentification passive est la méthode d’authentification la moins privilégiée pour l’authentification webticket. Pour tous les directeurs, pools Enterprise et serveurs Édition Standard qui seront activés pour l’authentification passive, tous les autres types d’authentification doivent être désactivés dans les services web Skype Entreprise en exécutant l’applet de la cmdlet suivante :

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. Vérifiez que tous les autres types d’authentification ont été correctement désactivés en exécutant l’cmdlet suivante :

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Proxy Configuration

Lorsque l’authentification par certificat est désactivée pour les services web Skype Entreprise, le client Skype Entreprise utilise un type d’authentification moins préféré, tel que Kerberos ou NTLM, pour s’authentifier auprès du service serveur d’inscriptions. L’authentification par certificat est toujours nécessaire pour permettre au client de récupérer un site webticket. Toutefois, Kerberos et NTLM doivent être désactivés pour le service serveur d’inscriptions.

Les étapes suivantes décrivent comment créer une configuration de proxy personnalisée pour les pools edge, les pools Enterprise et les serveurs Édition Standard qui seront activés pour l’authentification passive.

### <a name="to-create-a-custom-proxy-configuration"></a>Pour créer une configuration de proxy personnalisée

1. À partir de la ligne de commande Skype Entreprise Server Management Shell, créez une configuration de proxy pour chaque pool edge Skype Entreprise Server, pool Enterprise et serveur Édition Standard qui sera activé pour l’authentification passive en exécutant la commande suivante : commandes :

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. Vérifiez que tous les autres types d’authentification proxy ont été correctement désactivés en exécutant la commande suivante :

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>Voir aussi

[Gérer l’authentification à deux facteurs dans Skype Entreprise Server](two-factor-authentication.md)

[Utiliser l’authentification à deux facteurs Skype Entreprise client et Skype Entreprise Server](use-two-factor.md)
