---
title: Préparation de votre appliance Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Découvrez comment préparer votre solution de nuage connecteur pour le déploiement et l’utiliser avec le système téléphonique dans Office 365 (en nuage PBX).
ms.openlocfilehash: 3716c7c4b9d4b8daa0a4995ed7e3d77b400b587f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240881"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Préparation de votre appliance Cloud Connector

Découvrez comment préparer votre solution de nuage connecteur pour le déploiement et l’utiliser avec le système téléphonique dans Office 365 (en nuage PBX).

Cette rubrique décrit comment obtenir les fichiers d’installation de la version Cloud Connector de Skype Entreprise, comment installer le logiciel Cloud Connector et préparer votre appliance Cloud Connector au déploiement. Après avoir effectué toutes les étapes de cette rubrique, vous serez prêt à déployer Cloud Connector pour un ou plusieurs sites. Si vous avez un déploiement en nuage connecteur existant, et vous ne disposez pas encore mis à niveau vers nuage connecteur version 2.1, consultez [mise à niveau vers une nouvelle version du nuage connecteur](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft prend en charge la version actuelle du nuage connecteur Edition, version 2.1. Si vous configurez une mise à jour automatique, Cloud Connector se mettra automatiquement à jour. Si vous avez configuré la mise à jour manuelle, vous devrez mettre à niveau vers la version 2.1 60 jours avant sa publication. Microsoft prendra en charge la version précédente de 60 jours après la publication de 2.1 permettant d’heure pour mettre à niveau. 

> [!NOTE]
> L’application hôte .NET Framework 4.6.1 doit être nuage connecteur version 2.1 et version ultérieure, ou version ultérieure. 

> [!IMPORTANT]
> Pour un déploiement réussi, lorsque vous exécutez les applets de commande pour configurer Skype pour édition dans le nuage connecteur, utilisez toujours la même session de console que celui que vous avez réactivé à. Évitez de basculer entre plusieurs sessions lors du déploiement et de la configuration. 

> [!NOTE]
> Certaines étapes peuvent uniquement être exécutées pour la première appliance de votre déploiement : création d’un partage pour l’annuaire de sites, téléchargement de bits et préparation d’un fichier de disque dur virtuel (VHDX) à partir de l’image ISO du serveur Windows. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Téléchargement du programme d’installation de Skype Entreprise, version Cloud Connector

1. Sur le serveur hôte où les ordinateurs virtuels dans le nuage connecteur s’exécutera, téléchargez les fichiers d’installation : [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller). 

    > [!IMPORTANT]
    > Le serveur hôte doit pouvoir accéder à Internet lors de l’installation de Cloud Connector, car des fichiers supplémentaires sont téléchargés pendant cette opération. 

2. Exécutez le programme d’installation et acceptez les valeurs par défaut lors de l’installation.

3. Vérifiez que l’installation a été correctement effectuée.

## <a name="verify-the-installation-and-configure-the-environment"></a>Vérification de l’installation et configuration de l’environnement

1. Ouvrez une console PowerShell en tant qu’administrateur et vérifiez que le Skype pour les applets de commande Business nuage connecteur Edition sont disponibles à l’aide de l’applet de commande suivante :

   ```
   Get-Command *-Cc*
   ```

    La commande doit renvoyer une liste des applets de commande pour Skype pour l’édition de connecteur Business Cloud.

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

    Lorsque vous ouvrez une session et déployez chaque appliance dans le site, vérifiez que votre compte d’ouverture de session en cours a le droit accéder à l' **Annuaire de sites**.

3. Le **Répertoire de l’application** est le répertoire racine travail local Skype pour édition dans le nuage connecteur et l’emplacement où les certificats externes, des instances et des journaux sont enregistrés. L’emplacement par défaut est : %USERPROFILE%\CloudConnector\ApplianceRoot.

    Pour rechercher l’emplacement de l’**Annuaire de sites** exécutez l’applet de commande suivante :

   ```
   Get-CcApplianceDirectory
   ```

    Pour définir le **répertoire d'équipements** vers un emplacement différent de celui par défaut, exécutez l’applet de commande suivante :

   ```
   Set-CcApplianceDirectory <File path>
   ```

    L’annuaire d’appliances doit être dirigé vers un dossier local de l’appliance. Vous devez uniquement définir le **Répertoire de l’Appliance** avant de commencer la Skype pour le déploiement dans le nuage connecteur édition. Si vous le modifiez après le déploiement, vous devrez redéployer le serveur hôte.

    > [!IMPORTANT]
    > Le chemin d’accès au **répertoire d'équipements** ne doit contenir aucun espace.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Définition du chemin d’accès au certificat Edge externe

- Pour définir le chemin d’accès au certificat Edge externe, notamment le nom du fichier, exécutez l’applet de commande suivante. Par exemple : C:\certs\cce\ap.contoso.com.pfx. Le certificat doit contenir des clés privées.

  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Notez que-cible paramètre est spécifique aux versions 1.4.2 et version ultérieure. 

    Spécifiez le chemin d’accès vers le certificat externe, notamment le nom de fichier. Le certificat peut être enregistré localement ou sur un partage de fichier. S’il est enregistré dans un dossier partagé, le dossier partagé doit être créé sur la première appliance de chaque site et être accessible par d’autres appliances appartenant au même site. Cette applet de commande copie le certificat externe vers l’**annuaire d’appliances**.

    > [!IMPORTANT]
    > **Si vous avez mis à jour vers le nuage connecteur version 1.4.2 ou une version ultérieure**, assurez-vous que votre certificat externe préparé contient les clés privées et la chaîne de certificats complète, y compris le certificat d’autorité de certification racine et les certificats d’autorité de certification intermédiaires. **Si vous n’avez pas encore mis à jour la version 1.4.2 de Cloud Connector**, vérifiez que votre certificat externe préparé contient des clés privées. Ce certificat externe doit être émis par une autorité de certification approuvée par défaut par Windows.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Définition du chemin d’accès pour le certificat externe de la passerelle RTC/SBC

Si vous utilisez TLS entre le serveur de médiation et la passerelle RTC/SBC, exécutez l’applet de commande suivante pour configurer le chemin d’accès, notamment le nom de fichier vers le certificat passerelle. Par exemple : C:\certs\cce\sbc.contoso.com.cer. Le certificat doit contenir l’AC racine et la chaîne intermédiaire pour le certificat assigné à la passerelle :

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Notez que-cible paramètre est spécifique aux versions 1.4.2 et version ultérieure. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Création de commutateurs virtuels dans le Gestionnaire Hyper-V

1. Ouvrez le **Gestionnaire Hyper-V** > **Gestionnaire de commutateur virtuel**et sélectionnez **Nouveau gestionnaire de commutateur virtuel**.

2. Créez un commutateur virtuel externe et associez-le à la carte réseau physique qui est connectée à votre domaine réseau interne :

    Sélectionnez **Permettre au système d’exploitation de gestion de partager cette carte réseau** pour le commutateur virtuel.

3. Créer un commutateur virtuel externe et le lier à la carte réseau physique qui est acheminée vers Internet :

    Désélectionnez **Autoriser le système d’exploitation de gestion à partager cette carte réseau** pour ce commutateur virtuel.

4. Définir le nom du commutateur qui se connecte votre réseau de périmètre pour votre domaine du réseau interne **SfB CCE Corpnet basculer**.

    Définir le nom du commutateur qui se connecte votre réseau de périmètre pour l’Internet **SfB CCE Internet basculer**.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Mise à jour du fichier de configuration CloudConnector.ini

Préparer le fichier CloudConnector.ini en utilisant les informations recueillies à [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) dans la rubrique [planifier Skype pour l’édition de connecteur Business Cloud](plan-skype-for-business-cloud-connector-edition.md) .

Pour mettre à jour le fichier, exécutez d’abord l’applet de commande suivante pour obtenir l’exemple de modèle (CloudConnector.Sample.ini) :

```
Export-CcConfigurationSampleFile
```

L’exemple de modèle est stocké dans le **répertoire d'équipements**.

Une fois mis à jour avec les valeurs relatives à votre environnement, enregistrez le fichier sous CloudConnector.ini dans le **répertoire d'équipements**. Vous pouvez exécuter **Get-CcApplianceDirectory** pour définir le chemin d’accès sur le **répertoire d'équipements**.

Lors de la mise à jour du fichier .ini, tenez compte des points suivants :

> [!NOTE]
> Cette section couvre uniquement les valeurs du fichier .ini qui comportent des caractéristiques spécifiques. Pour obtenir la liste complète, consultez la section [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) de la rubrique [planifier Skype pour l’édition de connecteur Business Cloud](plan-skype-for-business-cloud-connector-edition.md) . Pour plus d’informations sur la nature des valeurs devant être changées pour des appliances supplémentaires ou de nouveaux sites, reportez-vous à [Site unique à haute disponibilité comparé aux déploiements multi-sites](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) dans la rubrique [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName :** la valeur par défaut est **Site1**. Vous devez la mettre à jour avant de déployer Cloud Connector, car lorsque vous exécutez **Register-CcAppliance** pour enregistrer un équipement dans un site existant ou nouveau, l’applet de commande utilisera le **SiteName** pour déterminer le site à enregistrer.

     Si vous souhaitez enregistrer l’équipement dans un nouveau site, la valeur **SiteName** doit être unique et différent des sites existants. Si vous souhaitez inscrire l’application à un site existant, la valeur pour **SiteName** dans le fichier .ini doit correspondre au nom défini dans votre configuration du client Office 365. Si vous copiez un fichier de configuration d’un site vers un autre, veillez à mettre à jour la valeur **SiteName** pour chaque site comme il convient.

- **ServerName :** Le nom de serveur ne doit pas contenir le nom de domaine et se limiter à 15 caractères. 

- **HardwareType :** Si vous ne définissez ou conservez la valeur null, la valeur par défaut du **style Normal** sera utilisée. Utilisez **Normal** si vous prévoyez de déployer la version la plus grande du nuage connecteur pour prendre en charge 500 appels simultanés par ordinateur hôte comme décrit dans [Plan for Skype pour l’édition de connecteur Business Cloud](plan-skype-for-business-cloud-connector-edition.md). Utilisez **Minimum** pour un déploiement moins développé qui prend en charge 50 appels simultanés.

- **Commutateurs virtuels Internet/réseau d’entreprise/gestion :**: ajouter le nom des commutateurs virtuels que vous avez créé. Pour le commutateur virtuel gestion, laissez la valeur par défaut. Le script de déploiement crée le commutateur virtuel gestion au début du déploiement et supprimer une fois le déploiement.

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

  - Assurez-vous que le masque de sous-réseau CorpnetIPPrefixLength est correct.

  - Assurez-vous qu’il n’existe aucun conflit IP pour les adresses IP internes.

- **Adresses IP externes :**

  - Pour les adresses IP publiques MR : spécifiez ExternalMRIPs pour NAT non ou ExternalMRPublicIPs pour NAT.

  - ExternalSIPIPs et ExternalMRIPs peut être la même.

  - Assurez-vous que le masque de sous-réseau InternetIPPrefixLength est correct.

  - Assurez-vous qu’il n’existe aucun conflit IP pour les adresses IP externes.

- **Passerelles :**

  - Si vous disposez d’une seule passerelle, supprimez la section concernant la deuxième passerelle. Si vous disposez de plus de deux passerelles, créez des sections supplémentaires en copiant et en collant, puis en la mettant à jour.

  - Assurez-vous que l’adresse IP et le port des passerelles sont corrects.

  - Pour prendre en charge la haute disponibilité de niveau passerelle PSTN, laissez la passerelle secondaire et ajoutez d’autres passerelles que vous utiliserez. Vous pouvez copier et coller une entrée existante et mettez-le à jour.

- Si vous le souhaitez, vous pouvez mettre à jour la valeur LocalRoute pour limiter les numéros d’appel sortants.

## <a name="download-the-bits-to-the-site-directory"></a>Téléchargement des fichiers BITS dans l’Annuaire de sites

Exécutez l’applet de commande suivante pour télécharger les fichiers BITS et d’informations de version vers l’**Annuaire de sites **:

```
Start-CcDownload
```

> [!NOTE]
> Vous devez effectuer cette étape uniquement pour la première appliance. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Préparation du disque virtuel de base (VHDX) à partir du fichier ISO téléchargé

Cette étape permet de préparer un fichier de disque dur virtuel (VHDX) à partir de l’image ISO Windows Server 2012. Ce VDHX sera utilisé pour créer des machines virtuelles lors du déploiement. Un ordinateur virtuel temporaire (base VM) sera créé et Windows Server 2012 sera installé à partir du fichier ISO. Après la création de la machine virtuelle, certains composants requis seront installés et la dernière mise à jour Windows sera appliquée. Après cela, la machine virtuelle de base sera généralisée (sysprep) et nettoyée, seul le fichier de disque virtuel généré sera conservé.

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

Le fichier de disque dur virtuel créé est stocké dans le dossier \Bits\VHD **Annuaire de sites** . Vous pouvez obtenir le chemin d’accès à l’**Annuaire de sites** en exécutant **Get-CcSiteDirectory**.

> [!IMPORTANT]
> Par défaut, les paramètres proxy ne sont pas configurés dans la machine virtuelle de base. Si un proxy est nécessaire dans votre environnement réseau pour mettre à jour de la machine virtuelle via Windows Update, vous devez ajouter le commutateur - PauseBeforeUpdate lorsque vous exécutez « Convert-CcIsoToVhdx ». Le script s’interrompt avant la mise à jour Windows et vous aurez l’occasion pour définir manuellement un proxy sur l’ordinateur virtuel. Une fois le proxy installé et que la machine virtuelle peut accéder à Internet, vous pouvez reprendre le script pour effectuer les étapes restantes. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Création de VHD pour un déploiement multisite

Cette étape facultative s’applique uniquement aux déploiements multisites.

Si vous effectuez un déploiement multisite, il n’est pas nécessaire de convertir l’image ISO en VHD pour chaque site. Vous pouvez copier le VHDX créé pour le premier site sur le serveur hôte pour un second site.

 Copiez le fichier vers le même emplacement de fichier (dossier \Bits\VHD de **l’Annuaire de sites** ) et portant le même nom de fichier, sur le serveur hôte pour un site supplémentaire.

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
> Cette tâche n’est pas requis pour les versions de nuage connecteur 1.4.2 et version ultérieure. 

Le compte CceService est créé lors du déplacement de Skype Entreprise, version Cloud Connector. Il s’exécute le Service de gestion en nuage connecteur et nécessite une autorisation pour désinstaller le cloudconnector.msi. Vous devez modifier le paramètre de stratégie de groupe locale sur l’ordinateur hôte de Cloud Connector pour spécifier que le registre de l’utilisateur ne doit pas être déchargé lors de sa déconnexion. Suivez la procédure suivante :

### <a name="to-change-the-group-policy-setting"></a>Pour modifier le paramètre de stratégie de groupe locale

1. Ouvrez l' **Éditeur de stratégie de groupe** en exécutant gpedit.msc.

2. Dans l’**Éditeur de stratégie de groupe**, sélectionnez Modèles d’administration > Système > UserProfile > Ne pas forcer le déchargement du registre de l’utilisateur lors de sa déconnexion.  

3. Définissez sa valeur sur **activé**.

## <a name="set-up-your-office-365-tenant"></a>Configurez votre client Office 365.

Un client Office 365 avec Skype pour Business Online et système téléphonique dans Office 365 est requis. Assurez-vous que votre client est installé et configuré avant d’essayer d’utiliser le connecteur sur le nuage.

Certaines étapes de configuration d’Office 365 vous obligent à utiliser PowerShell à distance de client (TRPS) pour configurer votre client Office 365. **Il doit être installé sur le serveur hôte**. Vous pouvez télécharger le Skype pour le module Business Online pour PowerShell à partir de : [Skype pour Business Online, le Module Windows PowerShell](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Créez un Skype dédié pour le compte d’administrateur entreprise pour la gestion en ligne dans le nuage connecteur, par exemple CceOnlineManagmentAdministrator. Ce compte sera utilisé pour ajouter ou supprimer un équipement, activer ou désactiver une mise à jour de SE automatique, activer ou désactiver la mise à jour automatique de fichiers binaires. Définissez le mot de passe de ce compte pour qu’il n’expire jamais ; ainsi vous n’aurez jamais à le modifier pour le service.


