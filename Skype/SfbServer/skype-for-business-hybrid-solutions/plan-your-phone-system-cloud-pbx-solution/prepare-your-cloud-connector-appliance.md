---
title: Préparation de votre appliance Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Découvrez comment préparer votre appliance Cloud Connector pour le déploiement et l’utilisation avec le système téléphonique (PBX Cloud).
ms.openlocfilehash: 74c4885a25b4176f4d5eb3ac27926bd9528387c6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358940"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Préparation de votre appliance Cloud Connector

> [!Important]
> La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online. Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Découvrez comment préparer votre appliance Cloud Connector pour le déploiement et l’utilisation avec le système téléphonique (PBX Cloud).

Cette section décrit comment obtenir les fichiers d’installation de Skype entreprise version Cloud Connector, installer le logiciel Cloud Connector et préparer votre appliance Cloud Connector pour le déploiement. Une fois que vous avez effectué toutes les étapes de cette section, vous serez prêt à déployer Cloud Connector pour un ou plusieurs sites. Si vous disposez d’un déploiement Cloud Connector existant et que vous n’avez pas encore effectué la mise à niveau vers la version 2,1 de Cloud Connector, consultez [la rubrique Upgrade to a New version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft prend en charge la version actuelle de la version 2,1 de Cloud Connector Edition. Si vous avez configuré la mise à jour automatique, Cloud Connector est automatiquement mis à jour. Si vous avez configuré la mise à jour manuelle, vous devrez effectuer une mise à niveau vers la version 2,1 dans 60 jours après sa publication. Microsoft prendra en charge la version précédente pendant 60 jours après la publication de la version 2,1 pour vous laisser le temps de mettre à niveau. 

> [!NOTE]
> Pour la version 2,1 et les versions ultérieures de Cloud Connector, l’appliance hôte doit avoir installé .NET Framework 4.6.1 ou une version ultérieure. 

> [!IMPORTANT]
> Pour réussir le déploiement, lorsque vous exécutez les applets de commande pour configurer Skype entreprise version Cloud Connector, utilisez toujours la même session de console que celle que vous avez démarrée dans. Évitez de basculer vers différentes sessions lors du déploiement et de la configuration. 

> [!NOTE]
> Il existe des étapes que vous devez effectuer uniquement pour la première appliance de votre déploiement : la création d’un partage pour l’annuaire de sites, le téléchargement des fichiers bits et la préparation d’un fichier VHDX à partir de l’image ISO de Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Télécharger le programme d’installation de Skype entreprise, version Cloud Connector

1. Sur le serveur hôte sur lequel seront exécutées les machines virtuelles Cloud Connector, téléchargez les fichiers d’installation : [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > Le serveur hôte doit pouvoir accéder à Internet lors de l’installation de Cloud Connector car d’autres fichiers sont téléchargés pendant l’installation. 

2. Exécutez le programme d’installation et acceptez les valeurs par défaut lors de l’installation.

3. Vérifiez que l’installation s’est correctement déroulée.

## <a name="verify-the-installation-and-configure-the-environment"></a>Vérifier l’installation et configurer l’environnement

1. Ouvrez une console PowerShell en tant qu’administrateur et vérifiez que les applets de commande Skype entreprise, version Cloud Connector sont disponibles à l’aide de l’applet de commande suivante :

   ```powershell
   Get-Command *-Cc*
   ```

    La commande doit renvoyer une liste d’applets de commande pour Skype entreprise, version Cloud Connector.

2. Les fichiers VHD, SfBBits et VersionInfo seront stockés dans l’annuaire de **sites**.

    Vous pouvez trouver l’emplacement de l' **Annuaire de sites** à l’aide de l’applet de commande suivante :

   ```powershell
   Get-CcSiteDirectory
   ```

    La commande doit renvoyer un emplacement dans votre système de fichiers. L’emplacement peut être un dossier local ou un partage de fichiers. L’emplacement par défaut de l' **Annuaire de sites** est le suivant :%UserProfile%\CloudConnector\SiteRoot. L’emplacement par défaut doit être remplacé par un partage de fichiers sur la première Appliance créée dans chaque site.

    L’emplacement que vous sélectionnez doit être :

   - Créé sur la première Appliance créée dans chaque site.

   - Un dossier partagé accessible par les autres serveurs hôtes (appliances) dans le même site.

     Pour définir l' **Annuaire de sites** sur un emplacement différent de celui par défaut, exécutez l’applet de commande suivante :

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Si vous déployez High Availability (HA) pour le site, veillez à exécuter l’applet de commande pour définir l' **Annuaire de sites** sur le même emplacement sur chaque serveur hôte dans le site.

    Lorsque vous vous connectez et déployez chaque appliance dans le site, vérifiez que votre compte d’ouverture de session actuel dispose de l’accès approprié à l' **Annuaire de sites**.

3. L' **Annuaire d’équipement** est le répertoire racine de travail local de Skype entreprise, version Cloud Connector, ainsi que l’emplacement où sont enregistrés les certificats externes, les instances et les journaux. L’emplacement par défaut est :%USERPROFILE%\CloudConnector\ApplianceRoot.

    Pour Rechercher l’emplacement de l' **Annuaire d’appliances**, exécutez l’applet de commande suivante :

   ```powershell
   Get-CcApplianceDirectory
   ```

    Pour définir le **répertoire d’équipements** sur un emplacement différent de celui par défaut, exécutez l’applet de commande suivante :

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    Le répertoire de l’appliance doit être défini sur un dossier local sur l’appliance. Vous ne devez définir le **répertoire** de l’équipement qu’avant de démarrer le déploiement de Skype entreprise, version Cloud Connector. Si vous le modifiez après le déploiement, vous devrez redéployer le serveur hôte.

    > [!IMPORTANT]
    > Le chemin d’accès au répertoire de l' **Appliance** ne doit pas contenir d’espaces.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Définir le chemin d’accès du certificat de serveur Edge externe

- Exécutez l’applet de commande suivante pour définir le chemin d’accès, y compris le nom de fichier, vers le certificat de serveur Edge externe. Par exemple : C:\certs\cce\ap.contoso.com.pfx. Le certificat doit contenir des clés privées.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Notez que le paramètre-Target est propre aux versions 1.4.2 et ultérieures. 

    Spécifiez le chemin d’accès complet au certificat externe, y compris le nom de fichier. Le certificat peut être stocké localement ou sur un partage de fichiers. Si le certificat est stocké dans un dossier partagé, le dossier partagé doit être créé sur la première appliance de chaque site et doit être accessible à d’autres Appliances appartenant au même site. Cette applet de commande copie le certificat externe vers l’annuaire de l' **Appliance**.

    > [!IMPORTANT]
    > **Si vous avez effectué une mise à jour vers la version 1.4.2 de Cloud Connector ou une version ultérieure**, vérifiez que votre certificat externe préparé contient des clés privées et la chaîne de certificats complète, y compris le certificat de l’autorité de certification racine et les certificats de l’autorité de certification intermédiaire. **Si vous n’avez pas encore effectué la mise à jour vers la version 1.4.2 de Cloud Connector**, vérifiez que votre certificat externe préparé contient des clés privées. Ce certificat externe doit être émis par une autorité de certification approuvée par défaut par Windows.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Définir le chemin d’accès à la passerelle RTC externe/certificat SBC

Si vous utilisez TLS entre le serveur de médiation et la passerelle RTC/SBC, exécutez l’applet de commande suivante pour définir le chemin d’accès, y compris le nom de fichier, sur le certificat de passerelle. Par exemple : C:\certs\cce\sbc.contoso.com.cer. Le certificat doit contenir l’autorité de certification racine et la chaîne intermédiaire pour le certificat affecté à la passerelle :

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Notez que le paramètre-Target est propre aux versions 1.4.2 et ultérieures. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Créer des commutateurs virtuels dans le Gestionnaire Hyper-V

1. Ouvrez le gestionnaire de commutateur virtuel du gestionnaire **Hyper-V**  >  **Virtual Switch Manager**, puis sélectionnez **nouveau gestionnaire de commutateur virtuel**.

2. Créez un commutateur virtuel externe et liez-le à la carte réseau physique qui est connectée à votre domaine réseau interne :

    Sélectionnez **autoriser le système d’exploitation de gestion à partager cette carte réseau** pour ce commutateur virtuel.

3. Créez un commutateur virtuel externe et associez-le à la carte réseau physique routée vers Internet :

    Désélectionnez **autoriser le système d’exploitation de gestion à partager cette carte réseau** pour ce commutateur virtuel.

4. Définissez le nom du commutateur qui connecte votre réseau de périmètre à votre commutateur de domaine interne **SFB CCE**.

    Définissez le nom du commutateur qui connecte votre réseau de périmètre au **commutateur Internet SFB CCE**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Mettre à jour le fichier de configuration CloudConnector.ini

Préparez le fichier de CloudConnector.ini à l’aide des informations recueillies dans [determine Deployment Parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) dans la rubrique [plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) .

Pour mettre à jour le fichier, exécutez d’abord l’applet de commande suivante pour obtenir l’exemple de modèle (CloudConnector.Sample.ini) :

```powershell
Export-CcConfigurationSampleFile
```

L’exemple de modèle est stocké dans le répertoire de l' **Appliance**.

Après avoir effectué la mise à jour avec les valeurs pour votre environnement, enregistrez le fichier en tant que CloudConnector.ini dans le répertoire de l' **Appliance**. Vous pouvez exécuter **Get-applet ccappliancedirectory** pour déterminer le chemin d’accès à l' **Annuaire d’équipements**.

Lors de la mise à jour du fichier. ini, tenez compte des éléments suivants :

> [!NOTE]
> Toutes les valeurs du fichier. ini ne sont pas abordées dans cette section, seuls les utilisateurs ayant une attention particulière sont abordés ici. Pour obtenir une liste complète, reportez-vous à la section [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) de la rubrique [plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) . Pour plus d’informations sur les valeurs qui doivent être modifiées pour les autres Appliances ou les nouveaux sites, reportez-vous [à site unique avec haute disponibilité (ha) par rapport aux déploiements multisites](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) de la rubrique [Deploy Multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName :** La valeur par défaut est **site1**. Vous devez le mettre à jour avant de déployer Cloud Connector, car lorsque vous exécutez **Register-applet ccappliance** pour inscrire une appliance sur un site existant ou nouveau, l’applet de commande utilise **SiteName** pour déterminer le site à enregistrer.

     Si vous souhaitez enregistrer l’appliance sur un nouveau site, la valeur **SiteName** doit être unique et différente des sites existants. Si vous souhaitez enregistrer l’appliance sur un site existant, la valeur **SiteName** dans le fichier. ini doit correspondre au nom défini dans la configuration de votre organisation Microsoft 365 ou Office 365. Si vous copiez un fichier de configuration d’un site à un autre, veillez à mettre à jour la valeur de **SiteName** pour chaque site en conséquence.

- **ServerName :** Le nom du serveur ne doit pas contenir le nom de domaine et doit être limité à 15 caractères.

- **HardwareType :** Si vous ne définissez pas ou ne laissez pas la valeur null, la valeur par défaut **normal** est utilisée. Utilisez **normal** si vous envisagez de déployer la version plus grande de Cloud Connector pour prendre en charge 500 appels simultanés par ordinateur hôte comme décrit dans [plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Utilisez le **minimum** pour un déploiement de plus petite taille qui prend en charge les appels simultanés 50.

- **Commutateurs virtuels Internet/de gestion de l’entreprise/gestion :**: ajoutez le nom des commutateurs virtuels que vous avez créés. Pour le commutateur virtuel de gestion, conservez la valeur par défaut. Le script de déploiement crée le commutateur virtuel de gestion au début du déploiement et le supprime une fois le déploiement terminé.

- **ManagementIPPrefix :** ManagementIPPrefix dans la section réseau doit être un sous-réseau différent des autres adresses IP internes. Par exemple, comme le montre la valeur par défaut, ManagementIPPrefix est 192.168.213.0, tandis que l’adresse IP de l’AD est 192.168.0.238.

    Les scripts de déploiement créent une carte réseau de gestion sur chaque machine virtuelle, attribuent une adresse IP de gestion et la connectent à un commutateur virtuel de gestion. Cela permet au serveur hôte de se connecter et de gérer chaque machine virtuelle via ce réseau de gestion. Le commutateur virtuel de gestion est supprimé lorsque le déploiement est terminé.

- **Configurations spécifiques de la machine virtuelle de base :** Les paramètres de cette section doivent être configurés pour l’applet de commande **Convert-applet ccisotovhdx** .

    Pendant la préparation de l’image VM de base, la machine virtuelle de base sera connectée au commutateur réseau interne. Les paramètres suivants sont essentiels pour que la machine virtuelle puisse accéder à Internet :

  - Usage BaseVMIP : adresse IP du réseau d’entreprise à affecter à la machine virtuelle de base.

  - Réseau CorpnetDefaultGateway : passerelle par défaut à affecter à la machine virtuelle de base.

  - Réseau CorpnetDNSIPAddress : adresse IP DNS à affecter à la machine virtuelle de base.

  - Réseau WSUSServer : adresse IP du service de mise à jour de Windows Server.

  - Réseau WSUSStatusServer : adresse IP du serveur d’État du service de mise à jour de Windows Server.

  - Réseau EnableReferSupport : spécifie si la prise en charge de SIP REFER est activée ou désactivée sur la configuration de jonction vers votre IP/PBX.

- **Adresses IP internes :**

  - Assurez-vous que le masque de sous-réseau CorpnetIPPrefixLength est correct.

  - Assurez-vous qu’aucun conflit IP n’existe pour ces adresses IP internes.

- **Adresses IP externes :**

  - Pour l’adresse IP publique de MR : spécifiez Externalmrip pour non-NAT ou ExternalMRPublicIPs pour NAT.

  - Externalsipip et Externalmrip peuvent être identiques.

  - Assurez-vous que le masque de sous-réseau InternetIPPrefixLength est correct.

  - Assurez-vous qu’aucun conflit IP n’existe pour ces adresses IP externes.

- **Passerelles**

  - Si vous n’avez qu’une seule passerelle, supprimez la section pour la passerelle secondaire. Si vous avez plus de deux passerelles, créez des sections supplémentaires en copiant et en collant le existant, puis en le mettant à jour.

  - Assurez-vous que l’adresse IP et le port de la (des) passerelle (s) sont corrects.

  - Pour prendre en charge la haute disponibilité de niveau passerelle PSTN, laissez la passerelle secondaire et ajoutez les passerelles supplémentaires que vous allez utiliser. Vous pouvez copier et coller une entrée existante, puis la mettre à jour.

- Vous pouvez également mettre à jour la valeur LocalRoute pour limiter les numéros d’appels sortants.

## <a name="download-the-bits-to-the-site-directory"></a>Télécharger le fichier bits vers l’annuaire de sites

Exécutez l’applet de commande suivante pour télécharger les fichiers d’informations de version et de bits dans l' **Annuaire de sites**:

```powershell
Start-CcDownload
```

> [!NOTE]
> Vous devez effectuer cette étape pour la première Appliance uniquement. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Préparation du disque virtuel de base (VHDX) à partir du fichier ISO téléchargé

Cette étape prépare un fichier de disque dur virtuel (VHDX) à partir de l’image ISO de Windows Server 2012. Le VHDX sera utilisé pour créer des machines virtuelles pendant le déploiement. Une machine virtuelle temporaire (VM de base) sera créée et Windows Server 2012 sera installé à partir du fichier ISO. Une fois que la machine virtuelle est créée, certains composants nécessaires seront installés et la dernière mise à jour de Windows sera appliquée. À la fin, la machine virtuelle de base sera généralisée (Sysprep) et nettoyée, en laissant uniquement le fichier de disque virtuel généré.

> [!NOTE]
> Vous devez effectuer cette étape pour la première Appliance uniquement. 

Avant de poursuivre cette étape, assurez-vous que le commutateur corpnet est créé. Vérifiez également que les paramètres suivants sont correctement configurés dans le fichier CloudConnector.ini :

- Réseau CorpnetSwitchName

- Usage BaseVMIP

- Réseau CorpnetIPPrefixLength

- Réseau CorpnetDefaultGateway

- Réseau CorpnetDNSIPAddress

Démarrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour convertir l’image ISO en disque dur virtuel (VHD) :

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Spécifiez le chemin d’accès complet, y compris le nom de fichier, dans l’image ISO. Par exemple : C:\ISO\WindowsServer2012R2.iso.

Le fichier de disque dur virtuel créé est stocké dans le dossier \Bits\VHD de l' **Annuaire de sites** . Vous pouvez obtenir le chemin d’accès à l' **Annuaire de sites** en exécutant la **applet ccsitedirectory**.

> [!IMPORTANT]
> Par défaut, les paramètres de proxy ne sont pas configurés sur la machine virtuelle de base. Si un proxy est requis dans votre environnement réseau pour mettre à jour la machine virtuelle via Windows Update, vous devez ajouter le commutateur-PauseBeforeUpdate lorsque vous exécutez « convert-applet ccisotovhdx ». Le script s’interrompt avant Windows Update et vous aurez la possibilité de configurer manuellement le proxy sur l’ordinateur virtuel. Une fois que le proxy est configuré et que la machine virtuelle peut accéder à Internet, vous pouvez reprendre le script pour effectuer les étapes restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Créer des disques durs virtuels pour un déploiement sur plusieurs sites

Il s’agit d’une étape facultative qui s’applique uniquement aux déploiements sur plusieurs sites.

Si vous déployez un déploiement sur plusieurs sites, vous n’avez pas besoin de convertir l’ISO en un disque dur virtuel pour chaque site. Vous pouvez copier le VHDX créé pour le premier site sur le serveur hôte pour un second site.

 Copiez le fichier dans le même emplacement de fichier (dossier \Bits\VHD de l' **Annuaire de sites** ) et avec le même nom de fichier sur le serveur hôte pour un site supplémentaire.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Définir la stratégie d’exécution PowerShell sur RemoteSigned

Les scripts PowerShell fournis nécessitent que la stratégie d’exécution soit définie sur RemoteSigned. Pour afficher le paramètre actuel, ouvrez une console PowerShell en tant qu’administrateur, puis exécutez l’applet de commande suivante :

```powershell
Get-ExecutionPolicy
```

S’il n’est pas défini sur « RemoteSigned », exécutez l’applet de commande suivante pour le modifier :

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Modifier la stratégie de groupe locale sur l’ordinateur hôte (versions 1.4.1 et antérieures)

> [!NOTE]
> Cette tâche n’est pas requise pour les versions 1.4.2 et ultérieures de Cloud Connector. 

Le compte CceService est créé lors du déploiement de Skype entreprise, version Cloud Connector. Il exécute le service de gestion Cloud Connector et nécessite l’autorisation de désinstaller le cloudconnector.msi. Vous devez modifier le paramètre de stratégie de groupe sur l’ordinateur hôte Cloud Connector pour spécifier que le registre de l’utilisateur ne doit pas être déchargé lorsque l’utilisateur se déconnecte. Suivez les étapes ci-dessous :

### <a name="to-change-the-group-policy-setting"></a>Pour modifier le paramètre de stratégie de groupe

1. Ouvrez l' **éditeur de stratégie de groupe** en exécutant gpedit. msc.

2. Dans l' **éditeur de stratégie de groupe**, accédez à modèles d’administration > système > UserProfile > ne forcez pas le déchargement du registre de l’utilisateur lors de la fermeture de session. 

3. Définissez sa valeur sur **activé**.

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Configurer votre organisation Microsoft 365 ou Office 365

Une organisation Microsoft 365 ou Office 365 avec Skype entreprise Online et le système téléphonique est requise. Assurez-vous que votre client est configuré et configuré avant d’utiliser Cloud Connector.

Certaines étapes de configuration de Microsoft 365 et d’Office 365 requièrent l’utilisation de PowerShell à distance client (TRPS) pour configurer votre organisation Microsoft 365 ou Office 365. **Il doit être installé sur le serveur hôte.** Vous pouvez télécharger le module Skype entreprise Online pour PowerShell à partir de l’un des modules suivants : [Skype entreprise Online et Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366).

Créez un compte d’administrateur Skype entreprise dédié pour la gestion en ligne de Cloud Connector, par exemple CceOnlineManagmentAdministrator. Ce compte sera utilisé par l’appliance pour ajouter ou supprimer des appliances, activer ou désactiver la mise à jour automatique du système d’exploitation, activer ou désactiver la mise à jour binaire automatique. Définissez le mot de passe de ce compte de sorte qu’il n’expire jamais afin que vous n’ayez pas besoin de le modifier à chaque fois qu’il arrive à expiration.


