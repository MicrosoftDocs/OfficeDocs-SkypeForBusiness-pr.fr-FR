---
title: Préparation de votre appareil Cloud Connector
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Découvrez comment préparer votre appliance Cloud Connector pour le déploiement et l’utilisation avec Système téléphonique (Cloud PBX).
ms.openlocfilehash: 255b276ebb0d192f876d07e318cf94ccf3698a1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589998"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Préparation de votre appareil Cloud Connector

> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Découvrez comment préparer votre appliance Cloud Connector pour le déploiement et l’utilisation avec Système téléphonique (Cloud PBX).

Cette section décrit comment obtenir les fichiers d’installation Skype Entreprise Cloud Connector Edition, installer le logiciel Cloud Connector et préparer votre appliance Cloud Connector pour le déploiement. Une fois toutes les étapes de cette section terminées, vous êtes prêt à déployer Cloud Connector pour un ou plusieurs sites. Si vous avez un déploiement Cloud Connector existant et que vous n’avez pas encore mis à niveau vers Cloud Connector version 2.1, voir Mise à niveau vers une nouvelle [version de Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)

> [!NOTE]
> Microsoft prend en charge la version actuelle de Cloud Connector, version 2.1. Si vous avez configuré la mise à jour automatique, Cloud Connector se met à jour automatiquement. Si vous avez configuré la mise à jour manuelle, vous devrez mettre à niveau vers la version 2.1 dans les 60 jours suivant sa publication. Microsoft prendra en charge la version précédente pendant 60 jours après la publication de la version 2.1 pour vous laisser le temps de mettre à niveau. 

> [!NOTE]
> Pour Cloud Connector version 2.1 et ultérieure, l’appliance hôte .NET Framework la version 4.6.1 ou ultérieure. 

> [!IMPORTANT]
> Pour un déploiement réussi, lorsque vous exécutez les cmdlets pour configurer les Skype Entreprise Cloud Connector Edition, utilisez toujours la même session console que celle que vous avez démarrée. Évitez de passer à différentes sessions pendant le déploiement et la configuration. 

> [!NOTE]
> Certaines étapes sont effectuées uniquement pour la première appliance de votre déploiement : création d’un partage pour l’annuaire de sites, téléchargement des bits et préparation d’un fichier de disque dur virtuel (VHDX) à partir de l’image ISO du serveur Windows. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Télécharger le programme Skype Entreprise Cloud Connector Edition installer

1. Sur le serveur hôte sur lequel s’exécuteront les VM Cloud Connector, téléchargez les fichiers d’installation [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) : 

    > [!IMPORTANT]
    > Le serveur hôte doit pouvoir accéder à Internet pendant l’installation de Cloud Connector, car des fichiers supplémentaires sont téléchargés pendant l’installation. 

2. Exécutez le programme d’installation et acceptez les valeurs par défaut pendant l’installation.

3. Confirmez que l’installation s’est correctement terminée.

## <a name="verify-the-installation-and-configure-the-environment"></a>Vérifier l’installation et configurer l’environnement

1. Ouvrez une console PowerShell en tant qu’administrateur et confirmez que les cmdlets Skype Entreprise Cloud Connector Edition sont disponibles à l’aide de l’cmdlet suivante :

   ```powershell
   Get-Command *-Cc*
   ```

    La commande doit renvoyer une liste des cmdlets pour Skype Entreprise Cloud Connector Edition.

2. Les fichiers VHD, SfBBits et VersionInfo seront stockés dans **l’annuaire de sites.**

    Vous pouvez trouver l’emplacement de **l’annuaire de** sites avec l’cmdlet suivante :

   ```powershell
   Get-CcSiteDirectory
   ```

    La commande doit renvoyer un emplacement dans votre système de fichiers. L’emplacement peut être un dossier local ou un partage de fichiers. L’emplacement par défaut de **l’annuaire de** sites est : %USERPROFILE%\CloudConnector\SiteRoot. L’emplacement par défaut doit être changé en partage de fichiers sur la première appliance créée dans chaque site.

    L’emplacement que vous sélectionnez doit être :

   - Créé sur la première appliance créée dans chaque site.

   - Dossier partagé accessible par les autres serveurs hôtes (appliances) dans le même site.

     Pour définir **l’annuaire de** sites sur un emplacement autre que celui par défaut, exécutez l’cmdlet suivante :

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Si vous déployez la haute disponibilité (HA) pour le site, veillez à exécuter l’cmdlet pour définir l’annuaire de sites sur le même emplacement sur chaque serveur hôte du site. 

    Lorsque vous vous connectez et déployez chaque appliance dans le site, assurez-vous que votre compte d’connexion actuel dispose du droit d’accès à **l’annuaire de sites.**

3. **L’annuaire** d’équipements est le répertoire racine de travail local pour Skype Entreprise Cloud Connector Edition et l’emplacement où les certificats externes, les instances et les journaux sont enregistrés. L’emplacement par défaut est : %USERPROFILE%\CloudConnector\ApplianceRoot.

    Pour trouver l’emplacement du répertoire **d’équipements,** exécutez l’cmdlet suivante :

   ```powershell
   Get-CcApplianceDirectory
   ```

    Pour définir **l’annuaire d’équipements** sur un emplacement autre que le répertoire par défaut, exécutez l’cmdlet suivante :

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    L’annuaire d’appliances doit être définie sur un dossier local sur l’appliance. Vous devez uniquement définir **l’annuaire d’appliances** avant de commencer le Skype Entreprise Cloud Connector Edition déploiement. Si vous le modifiez après le déploiement, vous devez redéployer le serveur hôte.

    > [!IMPORTANT]
    > Le chemin d’accès au **répertoire d’équipements** ne doit contenir aucun espace.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Définir le chemin d’accès pour le certificat Edge externe

- Exécutez l’cmdlet suivante pour définir le chemin d’accès, y compris le nom de fichier, au certificat Edge externe. Par exemple : C:\certs\cce\ap.contoso.com.pfx. Le certificat doit contenir des clés privées.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Notez que le paramètre -Target est spécifique aux versions 1.4.2 et ultérieures. 

    Spécifiez le chemin d’accès complet au certificat externe, y compris le nom de fichier. Le certificat peut être stocké localement ou sur un partage de fichiers. Si le certificat est stocké dans un dossier partagé, le dossier partagé doit être créé sur la première appliance de chaque site et doit être accessible par d’autres appliances appartenant au même site. Cette cmdlet copie le certificat externe dans **l’annuaire d’appliances.**

    > [!IMPORTANT]
    > Si vous avez mis à jour vers **Cloud Connector version 1.4.2** ou ultérieure, assurez-vous que votre certificat externe préparé contient des clés privées et la chaîne de certificats complète, y compris le certificat d’ac racine et les certificats d’ac intermédiaire. Si vous n’avez PAS encore mis à jour **la version 1.4.2** de Cloud Connector, assurez-vous que votre certificat externe préparé contient des clés privées. Ce certificat externe doit être émis par une autorité de certification qui est Windows par défaut.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Définir le chemin d’accès pour la passerelle PSTN externe/certificat SBC

Si vous utilisez TLS entre le serveur de médiation et la passerelle PSTN/SBC, exécutez l’cmdlet suivante pour définir le chemin d’accès, y compris le nom de fichier, au certificat de passerelle. Par exemple : C:\certs\cce\sbc.contoso.com.cer. Le certificat doit contenir l’ac racine et la chaîne intermédiaire pour le certificat affecté à la passerelle :

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Notez que le paramètre -Target est spécifique aux versions 1.4.2 et ultérieures. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Créer des commutateurs virtuels dans le Gestionnaire Hyper-V

1. Ouvrez le Gestionnaire de commutateur virtuel   >  **Hyper-V,** puis sélectionnez **Nouveau gestionnaire de commutateur virtuel.**

2. Créez un commutateur virtuel externe et l’attachez à la carte réseau physique connectée à votre domaine réseau interne :

    Sélectionnez **Autoriser le système d’exploitation de gestion à partager cette carte réseau** pour ce commutateur virtuel.

3. Créez un commutateur virtuel externe et l’attachez à la carte réseau physique acheminée vers Internet :

    Désélectez **Autoriser le système d’exploitation de gestion à partager cette carte réseau** pour ce commutateur virtuel.

4. Définissez le nom du commutateur qui connecte votre réseau de périmètre à votre domaine réseau **interne SfB CCE Corpnet Switch**.

    Définissez le nom du commutateur qui connecte votre réseau de périmètre au commutateur **Internet SfB CCE Internet.**

## <a name="update-the-cloudconnectorini-configuration-file"></a>Mettre à jour le CloudConnector.ini de configuration de l’ordinateur

Préparez le CloudConnector.ini à l’aide des informations que vous avez [recueillies](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) dans Déterminer les paramètres de déploiement dans la [rubrique Plan for Skype Entreprise Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)

Pour mettre à jour le fichier, exécutez d’abord l’cmdlet suivante pour obtenir l’exemple de modèle (CloudConnector.Sample.ini) :

```powershell
Export-CcConfigurationSampleFile
```

L’exemple de modèle est stocké dans **l’annuaire d’équipements.**

Une fois que vous l’avez mis à jour avec les valeurs de votre environnement, enregistrez le fichier CloudConnector.ini dans **l’annuaire d’équipements.** Vous pouvez exécuter **Get-CcApplianceDirectory pour** déterminer le chemin d’accès au répertoire **d’équipements.**

Lors de la mise à jour .ini fichier, prenons en compte les considérations suivantes :

> [!NOTE]
> Les valeurs du fichier .ini ne sont pas toutes abordées dans cette section, seules celles qui font l’objet d’une attention particulière sont abordées ici. Pour obtenir la liste complète, consultez la section Déterminer les [paramètres](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) de déploiement de la rubrique [Plan for Skype Entreprise Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md) Pour plus d’informations sur les valeurs qui doivent être modifiées pour des appliances supplémentaires ou de nouveaux sites, voir Site unique avec haute disponibilité (HA) par rapport aux [déploiements multisesses](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) dans la rubrique Déployer plusieurs sites dans [Cloud Connector.](deploy-multiple-sites-in-cloud-connector.md) 

- **SiteName :** La valeur par défaut **est Site1**. Vous devez la mettre à jour avant de déployer Cloud Connector, car lorsque vous exécutez **Register-CcAppliance** pour inscrire une appliance sur un site existant ou nouveau, l’cmdlet utilise **SiteName** pour déterminer le site à inscrire.

     Si vous souhaitez inscrire l’appliance sur un nouveau site, la valeur de **SiteName** doit être unique et différente des sites existants. Si vous souhaitez inscrire l’appliance sur un site existant, la valeur de **SiteName** dans le fichier .ini doit correspondre au nom défini dans la configuration de votre organisation Microsoft 365 ou Office 365. Si vous copiez un fichier de configuration d’un site à un autre, veillez à mettre à jour la valeur de **SiteName** pour chaque site en conséquence.

- **ServerName :** Le nom du serveur ne doit pas contenir le nom de domaine et doit être limité à 15 caractères.

- **HardwareType :** Si vous ne définissez pas ou ne laissez pas la valeur null, la valeur par défaut **normal** est utilisée. Utilisez **Normal** si vous prévoyez de déployer la version plus grande de Cloud Connector pour prendre en charge 500 appels simultanés par ordinateur hôte, comme décrit dans [Planifier Skype Entreprise Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). Utilisez **minimum** pour un déploiement plus petit qui prend en charge 50 appels simultanés.

- **Commutateurs virtuels Internet/Réseau d’entreprise/Gestion**: ajoutez le nom des commutateurs virtuels que vous avez créés. Pour le commutateur virtuel de gestion, laissez la valeur par défaut. Le script de déploiement crée le commutateur virtuel de gestion au début du déploiement et le supprime une fois le déploiement terminé.

- **ManagementIPPrefix :** ManagementIPPrefix dans la section Réseau doit être un sous-réseau différent des autres IP internes. Par exemple, comme le montre la valeur par défaut, ManagementIPPrefix est 192.168.213.0, tandis qu’AD IPAddress est 192.168.0.238.

    Les scripts de déploiement créent une carte réseau de gestion sur chaque ordinateur virtuel, attribuent une adresse IP de gestion et la connectent à un commutateur virtuel de gestion. Cela permet au serveur hôte de se connecter à chaque machine virtuelle et de la gérer via ce réseau de gestion. Le commutateur virtuel de gestion est supprimé lorsque le déploiement est terminé.

- **Configurations spécifiques** aux ordinateurs Paramètres de base : les Paramètres dans cette section doivent être configurées pour l';cmdlet **Convert-CcIsoToVhdx.**

    Lors de la préparation de l’image de la VM de base, la VM de base est connectée au commutateur réseau interne. Les paramètres suivants sont essentiels pour que la VM puisse accéder à Internet :

  - [Common] BaseVMIP : adresse IP du réseau d’entreprise à attribuer à la VM de base.

  - [Réseau] CorpnetDefaultGateway : passerelle par défaut à attribuer à la VM de base.

  - [Réseau] CorpnetDNSIPAddress : adresse IP DNS à attribuer à la VM de base.

  - [Réseau] WSUSServer : adresse IP de Windows Server Update Service.

  - [Réseau] WSUSStatusServer : adresse IP du serveur Windows d’état du service de mise à jour du serveur.

  - [Réseau] EnableReferSupport : cette opération définit si la prise en charge SIP REFER est activée ou désactivée sur la configuration de la trunk sur votre IP/PBX.

- **IPs internes :**

  - Assurez-vous que le masque de sous-réseau CorpnetIPPrefixLength est correct.

  - Assurez-vous qu’il n’existe aucun conflit IP pour ces adresses IP internes.

- **Fournisseurs d’IP externes :**

  - Pour l’adresse IP publique mr : spécifiez externalMRIPs pour les adresses non NAT ou ExternalMRPublicIPs pour NAT.

  - ExternalSIPIPs et ExternalMRIPs peuvent être identiques.

  - Assurez-vous que le masque de sous-réseau InternetIPPrefixLength est correct.

  - Assurez-vous qu’il n’existe aucun conflit IP pour ces adresses IP externes.

- **Passerelles :**

  - Si vous n’avez qu’une seule passerelle, supprimez la section de la passerelle secondaire. Si vous avez plus de deux passerelles, créez des sections supplémentaires en copiant et en coller une existante, puis en la mettant à jour.

  - Assurez-vous que l’adresse IP et le port des passerelles sont corrects.

  - Pour prendre en charge la ha de niveau passerelle PSTN, quittez la passerelle secondaire et ajoutez les passerelles supplémentaires que vous utiliserez. Vous pouvez copier et coller une entrée existante, puis la mettre à jour.

- Si vous le souhaitez, vous pouvez mettre à jour la valeur LocalRoute pour limiter les numéros d’appel sortants.

## <a name="download-the-bits-to-the-site-directory"></a>Télécharger les bits dans l’annuaire de sites

Exécutez l’cmdlet suivante pour télécharger les fichiers d’informations sur les bits et la version dans **l’annuaire de sites**:

```powershell
Start-CcDownload
```

> [!NOTE]
> Vous devez effectuer cette étape pour la première appliance uniquement. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Préparer le disque virtuel de base (VHDX) à partir du fichier ISO téléchargé

Cette étape prépare un fichier de disque dur virtuel (VHDX) à partir de l Windows Server 2012 image ISO. Le VHDX sera utilisé pour créer des machines virtuelles pendant le déploiement. Une machine virtuelle temporaire (machine virtuelle de base) sera créée et Windows Server 2012 sera installée à partir du fichier ISO. Une fois la VM créée, certains composants nécessaires sont installés et la dernière mise à jour Windows mise à jour est appliquée. À la fin, l’ordinateur virtuel de base sera généralisé (sysprep) et nettoyé, ne laissant que le fichier de disque virtuel généré.

> [!NOTE]
> Vous devez effectuer cette étape pour la première appliance uniquement. 

Avant de passer à cette étape, assurez-vous que le commutateur de réseau d’entreprise est créé. En outre, confirmez que les paramètres suivants sont correctement configurés dans CloudConnector.ini fichier :

- [Réseau] CorpnetSwitchName

- [Common] BaseVMIP

- [Réseau] CorpnetIPPrefixLength

- [Réseau] CorpnetDefaultGateway

- [Réseau] CorpnetDNSIPAddress

Démarrez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante pour convertir l’image ISO en disque dur virtuel (VHD) :

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Spécifiez le chemin d’accès complet, y compris le nom de fichier, à l’image ISO. Par exemple : C:\ISO\WindowsServer2012R2.iso.

Le fichier VHD créé est stocké dans le dossier **Répertoire** de sites \Bits\VHD. Vous pouvez obtenir le chemin d’accès à **l’annuaire de** sites en exécutant **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Par défaut, les paramètres proxy ne sont pas configurés sur la VM de base. Si un proxy est requis dans votre environnement réseau pour mettre à jour la VM via Windows Update, vous devez ajouter le commutateur -PauseBeforeUpdate lorsque vous exécutez « Convert-CcIsoToVhdx ». Le script s’interrompt avant Windows mise à jour et vous avez la possibilité de configurer manuellement le proxy sur la VM. Une fois que le proxy est configuré et que la VM peut accéder à Internet, vous pouvez reprendre le script pour effectuer les étapes restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Créer des disques durs durs pour un déploiement sur plusieurs sites

Il s’agit d’une étape facultative qui s’applique uniquement aux déploiements sur plusieurs sites.

Si vous déployez un déploiement sur plusieurs sites, vous n’avez pas besoin de convertir l’iso en disque dur vhd pour chaque site. Vous pouvez copier le VHDX créé pour le premier site sur le serveur hôte pour un second site.

 Copiez le fichier au même emplacement (répertoire du **site** \Bits\dossier VHD) et avec le même nom de fichier, sur le serveur hôte pour un site supplémentaire.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Définir la stratégie d’exécution PowerShell sur RemoteSigned

Les scripts PowerShell fournis nécessitent que la stratégie d’exécution soit définie sur RemoteSigned. Pour voir le paramètre actuel, ouvrez une console PowerShell en tant qu’administrateur, puis exécutez l’cmdlet suivante :

```powershell
Get-ExecutionPolicy
```

Si elle n’est pas définie sur « RemoteSigned », exécutez l’cmdlet suivante pour la modifier :

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Modifier la stratégie de groupe locale sur l’ordinateur hôte (versions 1.4.1 et antérieures)

> [!NOTE]
> Cette tâche n’est pas requise pour les versions 1.4.2 et ultérieures de Cloud Connector. 

Le compte CceService est créé pendant le Skype Entreprise Cloud Connector Edition de travail. Il exécute le service de gestion Cloud Connector et requiert l’autorisation de désinstaller le cloudconnector.msi. Vous devez modifier le paramètre de stratégie de groupe sur l’ordinateur hôte Cloud Connector pour spécifier que le Registre de l’utilisateur ne doit pas être déchargé lorsque l’utilisateur se déconnecte. Suivez les étapes ci-dessous :

### <a name="to-change-the-group-policy-setting"></a>Pour modifier le paramètre de stratégie de groupe

1. Ouvrez **l’Éditeur de stratégie de** groupe en exécutant gpedit.msc.

2. Dans l’Éditeur de stratégie de **groupe,** accédez à Modèles d’administration > Système > UserProfile > Ne déchargez pas de force le Registre utilisateur lors de la déconnexion de l’utilisateur. 

3. Définissez sa valeur sur **Activé.**

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Configurer votre organisation Microsoft 365 ou Office 365 organisation

Une Microsoft 365 ou Office 365 organisation avec Skype Entreprise Online et Système téléphonique est requise. Assurez-vous que votre client est configuré avant d’essayer d’utiliser Cloud Connector.

Certaines étapes Microsoft 365 et Office 365 de configuration nécessitent l’utilisation de Tenant Remote PowerShell (TRPS) pour configurer votre organisation Microsoft 365 ou Office 365 client. **Il doit être installé sur le serveur hôte.** Vous pouvez télécharger le module Skype Entreprise Online pour PowerShell à partir de : [Skype Entreprise Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).

Créez un compte Skype Entreprise administrateur dédié pour la gestion en ligne de Cloud Connector, par exemple CceOnlineManagmentAdministrator. Ce compte sera utilisé par l’appliance pour ajouter ou supprimer une appliance, activer ou désactiver la mise à jour automatique du système d’exploitation, activer ou désactiver la mise à jour binaire automatique. Définissez le mot de passe de ce compte pour qu’il n’expire jamais afin que vous n’avez pas besoin de le modifier pour le service chaque fois qu’il expire.