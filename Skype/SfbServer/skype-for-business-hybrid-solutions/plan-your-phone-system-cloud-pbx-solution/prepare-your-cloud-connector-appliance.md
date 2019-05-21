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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Apprenez-en davantage sur la préparation de votre appareil Cloud Connector pour le déploiement et l’utilisation avec le système téléphonique dans Office 365 (Cloud PBX).
ms.openlocfilehash: f2140eb0be25ba0b6935f389e5ae7b27bfc37359
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286998"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Préparation de votre appliance Cloud Connector

Apprenez-en davantage sur la préparation de votre appareil Cloud Connector pour le déploiement et l’utilisation avec le système téléphonique dans Office 365 (Cloud PBX).

Cette rubrique décrit comment obtenir les fichiers d’installation de la version Cloud Connector de Skype Entreprise, comment installer le logiciel Cloud Connector et préparer votre appliance Cloud Connector au déploiement. Après avoir effectué toutes les étapes de cette rubrique, vous serez prêt à déployer Cloud Connector pour un ou plusieurs sites. Si vous disposez d’un déploiement Cloud Connector existant et que vous n’avez pas encore effectué la mise à niveau vers la version 2,1 du Cloud Connector, voir [effectuer la mise à niveau vers une nouvelle version de Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft prend en charge la version actuelle de l’édition Cloud Connector, version 2,1. Si vous configurez une mise à jour automatique, Cloud Connector se mettra automatiquement à jour. Si vous avez configuré la mise à jour manuelle, vous devez effectuer la mise à niveau vers la version 2,1 dans 60 jours de sa publication. Microsoft prend en charge la version précédente de 60 jours après la publication d' 2,1 pour vous permettre d’effectuer la mise à niveau. 

> [!NOTE]
> Pour le Cloud Connector version 2,1 et les versions ultérieures, l’appareil hôte doit disposer de .NET Framework 4.6.1 ou version ultérieure. 

> [!IMPORTANT]
> Dans le cas d’un déploiement réussi, lorsque vous exécutez les applets de connexion pour configurer Skype entreprise version Cloud Connector, utilisez toujours la même session de console que celle que vous avez démarrée. Évitez de basculer entre plusieurs sessions lors du déploiement et de la configuration. 

> [!NOTE]
> Certaines étapes peuvent uniquement être exécutées pour la première appliance de votre déploiement : création d’un partage pour l’annuaire de sites, téléchargement de bits et préparation d’un fichier de disque dur virtuel (VHDX) à partir de l’image ISO du serveur Windows. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Téléchargement du programme d’installation de Skype Entreprise, version Cloud Connector

1. Sur le serveur hôte sur lequel s’exécutent les VM de connexion Cloud, téléchargez les [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)fichiers d’installation:. 

    > [!IMPORTANT]
    > Le serveur hôte doit pouvoir accéder à Internet lors de l’installation de Cloud Connector, car des fichiers supplémentaires sont téléchargés pendant cette opération. 

2. Exécutez le programme d’installation et acceptez les valeurs par défaut lors de l’installation.

3. Vérifiez que l’installation a été correctement effectuée.

## <a name="verify-the-installation-and-configure-the-environment"></a>Vérification de l’installation et configuration de l’environnement

1. Ouvrez une console PowerShell en tant qu’administrateur, puis vérifiez que les applets de commande Skype entreprise version Cloud Connector sont disponibles à l’aide de l’applet de commande suivante:

   ```
   Get-Command *-Cc*
   ```

    La commande doit retourner une liste d’applets de commande pour Skype entreprise version Cloud Connector.

2. Les fichiers de disques durs virtuels, SfBBits et VersionInfo seront stockés dans l’**Annuaire de sites**.

    Vous trouverez l’emplacement de l’**Annuaire de sites** à l’aide de l’applet de commande suivante :

   ```
   Get-CcSiteDirectory
   ```

    La commande doit renvoyer un emplacement dans votre système de fichiers. L’emplacement peut être un dossier local ou un partage de fichiers. L’emplacement par défaut de l’**Annuaire de sites** est le suivant : %USERPROFILE%\CloudConnector\SiteRoot. L’emplacement par défaut doit être remplacé par un partage de fichiers sur le premier équipement créé dans chaque site.

    L’emplacement que vous sélectionnez doit être :

   - Créé sur le premier équipement créé dans chaque site ;

   - Un dossier partagé accessible par les autres serveurs hôtes (équipements) dans le même site; 

     Pour définir l’**Annuaire de sites** sur un emplacement différent de celui par défaut, exécutez l’applet de commande suivante :

   ```
   Set-CcSiteDirectory <UNC File path>
   ```

    Si vous déployez la haute disponibilité pour le site, veillez à exécuter l’applet de comment pour définir l’**Annuaire de sites** vers le même emplacement sur chaque serveur hôte dans le site.

    Lorsque vous ouvrez une session et que vous déployez chaque application sur le site, vérifiez que votre compte d’ouverture de session actuel dispose de l’accès approprié à l' **Annuaire de sites**.

3. Le **répertoire** de l’application est le répertoire racine de travail local de Skype entreprise version Cloud Connector et l’emplacement où sont enregistrés les certificats externes, les instances et les journaux. L’emplacement par défaut est : %USERPROFILE%\CloudConnector\ApplianceRoot.

    Pour rechercher l’emplacement de l’**Annuaire de sites** exécutez l’applet de commande suivante :

   ```
   Get-CcApplianceDirectory
   ```

    Pour définir le **répertoire d'équipements** vers un emplacement différent de celui par défaut, exécutez l’applet de commande suivante :

   ```
   Set-CcApplianceDirectory <File path>
   ```

    L’annuaire d’appliances doit être dirigé vers un dossier local de l’appliance. Vous ne devez définir le **répertoire** de l’application que avant de lancer le déploiement de Skype entreprise version Cloud Connector. Si vous le modifiez après le déploiement, vous devrez redéployer le serveur hôte.

    > [!IMPORTANT]
    > Le chemin d’accès au **répertoire d'équipements** ne doit contenir aucun espace.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Définition du chemin d’accès au certificat Edge externe

- Pour définir le chemin d’accès au certificat Edge externe, notamment le nom du fichier, exécutez l’applet de commande suivante. Par exemple : C:\certs\cce\ap.contoso.com.pfx. Le certificat doit contenir des clés privées.

  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Notez que le paramètre-Target est spécifique aux versions 1.4.2 et ultérieures. 

    Spécifiez le chemin d’accès vers le certificat externe, notamment le nom de fichier. Le certificat peut être enregistré localement ou sur un partage de fichier. S’il est enregistré dans un dossier partagé, le dossier partagé doit être créé sur la première appliance de chaque site et être accessible par d’autres appliances appartenant au même site. Cette applet de commande copie le certificat externe vers l’**annuaire d’appliances**.

    > [!IMPORTANT]
    > **Si vous avez effectué une mise à jour vers le Connector Cloud version 1.4.2 ou une version ultérieure**, assurez-vous que votre certificat externe préparé contient des clés privées et la chaîne de certificats complète, y compris le certificat de l’autorité de certification racine et les certificats d’autorité de certification intermédiaire **Si vous n’avez pas encore mis à jour la version 1.4.2 de Cloud Connector**, vérifiez que votre certificat externe préparé contient des clés privées. Ce certificat externe doit être émis par une autorité de certification approuvée par défaut par Windows.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Définition du chemin d’accès pour le certificat externe de la passerelle RTC/SBC

Si vous utilisez TLS entre le serveur de médiation et la passerelle RTC/SBC, exécutez l’applet de commande suivante pour configurer le chemin d’accès, notamment le nom de fichier vers le certificat passerelle. Par exemple: C:\certs\cce\sbc.contoso.com.cer. Le certificat doit contenir l’AC racine et la chaîne intermédiaire pour le certificat assigné à la passerelle :

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Notez que le paramètre-Target est spécifique aux versions 1.4.2 et ultérieures. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Création de commutateurs virtuels dans le Gestionnaire Hyper-V

1. Ouvrez le**Gestionnaire de switches virtuel** **Hyper-V** > et sélectionnez **nouveau gestionnaire de switch virtuel**.

2. Créez un commutateur virtuel externe et associez-le à la carte réseau physique qui est connectée à votre domaine réseau interne :

    Sélectionnez **Permettre au système d’exploitation de gestion de partager cette carte réseau** pour le commutateur virtuel.

3. Créer un commutateur virtuel externe et le lier à la carte réseau physique routée vers Internet:

    Dé-sélectionnez **autoriser la gestion du système d’exploitation pour partager cette carte réseau** pour ce commutateur virtuel.

4. Définissez le nom du commutateur connecté à votre réseau de périmètre pour le **commutateur corpnet**du domaine de réseau marketing.

    Définissez le nom du commutateur connecté à votre réseau de périmètre au **commutateur Internet Marketing CCE**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Mise à jour du fichier de configuration CloudConnector.ini

Préparez le fichier CloudConnector. ini en utilisant les informations que vous avez collectées dans la section [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) du [plan pour Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md) .

Pour mettre à jour le fichier, exécutez d’abord l’applet de commande suivante pour obtenir l’exemple de modèle (CloudConnector.Sample.ini) :

```
Export-CcConfigurationSampleFile
```

L’exemple de modèle est stocké dans le **répertoire d'équipements**.

Une fois mis à jour avec les valeurs relatives à votre environnement, enregistrez le fichier sous CloudConnector.ini dans le **répertoire d'équipements**. Vous pouvez exécuter **Get-CcApplianceDirectory** pour définir le chemin d’accès sur le **répertoire d'équipements**.

Lors de la mise à jour du fichier .ini, tenez compte des points suivants :

> [!NOTE]
> Cette section couvre uniquement les valeurs du fichier .ini qui comportent des caractéristiques spécifiques. Pour obtenir une liste complète, consultez la section [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) de la rubrique [plan pour Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md) . Pour plus d’informations sur la nature des valeurs devant être changées pour des appliances supplémentaires ou de nouveaux sites, reportez-vous à [Site unique à haute disponibilité comparé aux déploiements multi-sites](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) dans la rubrique [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName :** la valeur par défaut est **Site1**. Vous devez la mettre à jour avant de déployer Cloud Connector, car lorsque vous exécutez **Register-CcAppliance** pour enregistrer un équipement dans un site existant ou nouveau, l’applet de commande utilisera le **SiteName** pour déterminer le site à enregistrer.

     Si vous souhaitez enregistrer l’équipement dans un nouveau site, la valeur **SiteName** doit être unique et différent des sites existants. Si vous voulez enregistrer l’application sur un site existant, la valeur de **SiteName** dans le fichier. ini doit correspondre au nom défini dans la configuration de votre client Office 365. Si vous copiez un fichier de configuration d’un site vers un autre, veillez à mettre à jour la valeur **SiteName** pour chaque site comme il convient.

- **ServerName :** Le nom de serveur ne doit pas contenir le nom de domaine et se limiter à 15 caractères. 

- **HardwareType:** Si vous ne définissez pas ou ne laissez pas la valeur null, la valeur par défaut **normale** est utilisée. Utilisez **normal** si vous envisagez de déployer la version plus grande de Cloud Connector pour prendre en charge les appels simultanés 500 par ordinateur hôte comme décrit dans la section [plan de Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md). Utilisez **Minimum** pour un déploiement moins développé qui prend en charge 50 appels simultanés.

- **Commutateurs virtuels Internet/corpnet/gestion:**: ajoutez le nom des commutateurs virtuels que vous avez créés. Pour le commutateur virtuel de gestion, conservez la valeur par défaut. Le script de déploiement va créer le commutateur virtuel de gestion au début du déploiement et le supprimer à la fin du déploiement.

- **ManagementIPPrefix :** le paramètre ManagementIPPrefix dans la section Réseau doit être un sous-réseau différent des autres IP internes. Par exemple, comme la valeur par défaut l’indique, ManagementIPPrefix est 192.168.213.0, tandis que AD IPAddress est 192.168.0.238.

    Les scripts de déploiement créent une carte réseau de gestion sur chacune des machines virtuelles, affectent une adresse IP de gestion et les connectent à un commutateur virtuel de gestion. Le serveur hôte peut ainsi se connecter aux machines virtuelles et les gérer via ce réseau de gestion. Le commutateur virtuel de gestion est supprimé à l’issue du déploiement.

- **Configurations spécifiques aux machines virtuelles de base :** les paramètres de cette section doivent être configurés pour l’applet de commande **Convert-CcIsoToVhdx**.

    Lors de la préparation de l’image de machine virtuelle de base, la machine virtuelle de base sera connectée au commutateur réseau interne. Les paramètres suivants sont critiques et permettent à la machine virtuelle d’accéder à Internet :

  - [Common]BaseVMIP : adresse IP du réseau d’entreprise à affecter à la machine virtuelle de base

  - [Network]CorpnetDefaultGateway : passerelle par défaut à affecter à la machine virtuelle de base

  - [Network]CorpnetDNSIPAddress : adresse IP du DNS à affecter à la machine virtuelle de base

  - [Network]WSUSServer : adresse IP du service WSUS (Windows Server Update Service)

  - [Network]WSUSStatusServer : adresse IP du serveur de statut WSUS (Windows Server Update Service)

  - [Network]EnableReferSupport : ce paramètre définira si la prise en charge SIP REFER est activée ou désactivée dans la configuration de jonctions pour votre IP/PBX.

- **Adresses IP internes :**

  - Vérifiez que le masque de sous-réseau CorpnetIPPrefixLength est correct.

  - Assurez-vous qu’il n’y a pas de conflits IP pour ces adresses IP internes.

- **Adresses IP externes :**

  - Pour une adresse IP publique de MR: spécifiez ExternalMRIPs pour les non-NAT ou ExternalMRPublicIPs pour tar.

  - ExternalSIPIPs et ExternalMRIPs peuvent être identiques.

  - Vérifiez que le masque de sous-réseau InternetIPPrefixLength est correct.

  - Assurez-vous qu’il n’y a pas de conflits IP pour ces adresses IP externes.

- **Passerelles :**

  - Si vous disposez d’une seule passerelle, supprimez la section concernant la deuxième passerelle. Si vous disposez de plus de deux passerelles, créez des sections supplémentaires en copiant et en collant, puis en la mettant à jour.

  - Assurez-vous que l’adresse IP et le port des passerelles sont corrects.

  - Pour prendre en charge la haute disponibilité de niveau passerelle PSTN, laissez la passerelle secondaire et ajoutez d’autres passerelles que vous utiliserez. Vous pouvez copier et coller une entrée existante, puis la mettre à jour.

- Le cas échéant, vous pouvez mettre à jour la valeur LocalRoute pour limiter les numéros d’appel sortants.

## <a name="download-the-bits-to-the-site-directory"></a>Téléchargement des fichiers BITS dans l’Annuaire de sites

Exécutez l’applet de commande suivante pour télécharger les fichiers BITS et d’informations de version vers l’**Annuaire de sites **:

```
Start-CcDownload
```

> [!NOTE]
> Vous devez effectuer cette étape uniquement pour la première appliance. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Préparation du disque virtuel de base (VHDX) à partir du fichier ISO téléchargé

Cette étape permet de préparer un fichier de disque dur virtuel (VHDX) à partir de l’image ISO Windows Server 2012. Ce VDHX sera utilisé pour créer des machines virtuelles lors du déploiement. Une machine virtuelle temporaire (VM de base) sera créée et Windows Server 2012 sera installé à partir du fichier ISO. Après la création de la machine virtuelle, certains composants requis seront installés et la dernière mise à jour Windows sera appliquée. Après cela, la machine virtuelle de base sera généralisée (sysprep) et nettoyée, seul le fichier de disque virtuel généré sera conservé.

> [!NOTE]
> Vous devez effectuer cette étape uniquement pour la première appliance. 

Avant de réaliser cette étape, assurez-vous que le commutateur réseau d’entreprise est créé. D’autre part, veillez à ce que les paramètres suivants soient correctement configurés dans le fichier CloudConnector.ini :

- [Network]CorpnetSwitchName

- [Common]BaseVMIP

- [Network]CorpnetIPPrefixLength

- [Network]CorpnetDefaultGateway

- [Network]CorpnetDNSIPAddress

Démarrez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour convertir l’image ISO en disque dur virtuel (VHD) :

```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Spécifiez le chemin d’accès complet, y compris le nom du fichier, à l’image ISO. Par exemple : C:\ISO\WindowsServer2012R2.iso.

Le fichier de disque dur virtuel créé est stocké dans le dossier \Bits\VHD de l' **Annuaire de sites** . Vous pouvez obtenir le chemin d’accès à l’**Annuaire de sites** en exécutant **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Par défaut, les paramètres proxy ne sont pas configurés dans la machine virtuelle de base. Si un proxy est requis dans votre environnement réseau pour mettre à jour l’ordinateur virtuel par le biais de Windows Update, vous devez ajouter le commutateur-PauseBeforeUpdate lorsque vous exécutez «convert-CcIsoToVhdx». Le script est suspendu avant Windows Update et vous aurez la possibilité de configurer manuellement un proxy sur la machine virtuelle. Une fois le proxy installé et que la machine virtuelle peut accéder à Internet, vous pouvez reprendre le script pour effectuer les étapes restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Création de VHD pour un déploiement multisite

Cette étape facultative s’applique uniquement aux déploiements multisites.

Si vous effectuez un déploiement multisite, il n’est pas nécessaire de convertir l’image ISO en VHD pour chaque site. Vous pouvez copier le VHDX créé pour le premier site sur le serveur hôte pour un second site.

 Copiez le fichier dans le même emplacement de fichier (dossier \Bits\VHD **Directory site** ) et avec le même nom de fichier, sur le serveur hôte d’un site supplémentaire.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Définition de la stratégie d’exécution PowerShell sur RemoteSigned

Les scripts PowerShell fournis requièrent que la stratégie d’exécution soit définie sur RemoteSigned. Pour consulter le paramètre actuel, ouvrez une console PowerShell en tant qu’administrateur, puis exécutez l’applet de commande suivante :

```
Get-ExecutionPolicy
```

Si elle n’est pas définie sur « RemoteSigned », exécutez l’applet de commande suivante pour la modifier :

```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Changement de la stratégie locale de groupe sur la machine hôte (versions 1.4.1 et précédentes)

> [!NOTE]
> Cette tâche n’est pas requise pour les versions de Cloud Connector 1.4.2 et versions ultérieures. 

Le compte CceService est créé lors du déplacement de Skype Entreprise, version Cloud Connector. Il exécute le service de gestion de connecteur Cloud et nécessite une autorisation de désinstallation de cloudconnector. msi. Vous devez modifier le paramètre de stratégie de groupe locale sur l’ordinateur hôte de Cloud Connector pour spécifier que le registre de l’utilisateur ne doit pas être déchargé lors de sa déconnexion. Suivez la procédure suivante :

### <a name="to-change-the-group-policy-setting"></a>Pour modifier le paramètre de stratégie de groupe locale

1. Ouvrez l' **éditeur de stratégies de groupe** en exécutant gpedit. msc.

2. Dans l’**Éditeur de stratégie de groupe**, sélectionnez Modèles d’administration > Système > UserProfile > Ne pas forcer le déchargement du registre de l’utilisateur lors de sa déconnexion.  

3. Définissez sa valeur sur **activé**.

## <a name="set-up-your-office-365-tenant"></a>Configurez votre client Office 365.

Un client Office 365 avec Skype entreprise Online et un système téléphonique dans Office 365 est requis. Assurez-vous que votre client est configuré et configuré avant d’utiliser Cloud Connector.

Certaines étapes d’installation d’Office 365 requièrent l’utilisation de Remote Remote PowerShell (TRPS) pour configurer votre client Office 365. **Il doit être installé sur le serveur hôte**. Vous pouvez télécharger le module Skype entreprise Online pour PowerShell depuis: [Skype entreprise Online, module Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Créer un compte d’administrateur Skype entreprise dédié pour la gestion en ligne du Cloud Connector, par exemple CceOnlineManagmentAdministrator. Ce compte sera utilisé pour ajouter ou supprimer un équipement, activer ou désactiver une mise à jour de SE automatique, activer ou désactiver la mise à jour automatique de fichiers binaires. Définissez le mot de passe de ce compte pour qu’il n’expire jamais ; ainsi vous n’aurez jamais à le modifier pour le service.


