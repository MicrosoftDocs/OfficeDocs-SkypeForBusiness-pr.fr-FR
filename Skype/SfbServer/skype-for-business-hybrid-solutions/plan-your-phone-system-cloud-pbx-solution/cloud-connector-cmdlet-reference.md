---
title: Référence d'applets de commande pour Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: Le tableau suivant présente les applets de commande Skype Entreprise, version Cloud Connector, une brève description et des liens pour obtenir plus d’informations.
ms.openlocfilehash: aa8b8ebe4ffd7d1cb2c405eae5fe6604c5f4c378
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234260"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
Le tableau suivant présente les applets de commande Skype Entreprise, version Cloud Connector, une brève description et des liens pour obtenir plus d’informations.
  
> [!NOTE]
> Vous devez exécuter tous les applets de commande sur l’hôte Cloud Connector, ainsi qu’une session PowerShell en tant qu’administrateur. 
  
|**Nom de l’applet de commande**|**Description**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Sauvegarde le service d’autorité de certification sur un fichier et l’enregistre dans un dossier AC sous l’annuaire de sites :          <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de Cloud Connector.    <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prépare le serveur hôte de Cloud Connector au processus de mise à jour en le mettant en mode maintenance. Le matériel est « drainée » ; Autrement dit, tous les appels en cours seront termine, mais les nouveaux appels sont rejetés.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Quitte le mode de maintenance de mise à jour du serveur hôte de Cloud Connector.    <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exporte un Skype pour la configuration du connecteur du nuage Professionnel vers un fichier local sur le Skype pour le serveur hôte de nuage connecteur édition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporte un fichier de configuration de l’exemple dans le nuage connecteur (.ini) vers le répertoire d’application d’un appareil de nuage connecteur. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Exporte le certificat de l’AC racine vers un fichier local sur le serveur hôte de Cloud Connector.   <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Extrait l’annuaire de travail sur le serveur hôte de Cloud Connector. Tous les fichiers de déploiement sont recensés dans cet annuaire.    <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Indique le répertoire actif où sont stockés les journaux pour une solution de nuage connecteur...  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2.1 et version ultérieure  <br/> |Fournit des informations de diagnostic pour la solution de nuage connecteur.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Renvoie les identifiants du déploiement Cloud Connector existant.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Cloud Connector. L’utilisateur prépare ce certificat.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de disque dur virtuel et de nuage connecteur base. Ce dossier doit être partagé avec tous les autres équipements d’un site dans le nuage connecteur.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Indique le répertoire actif où sont stockés les journaux de niveau site pour le connecteur sur le nuage.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2.0 et ultérieures  <br/> |Retourne la version sur l’instance du nuage connecteur. Get-CCVersion peut être utilisé uniquement dans l’ordinateur hôte du nuage connecteur.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Version 2.0 et ultérieures  <br/> |Importe le Skype pour la configuration du connecteur du nuage Professionnel à partir d’un fichier local vers le serveur hôte nuage connecteur.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installe la solution de nuage Connecteur — AD, y compris les ordinateurs virtuels magasin Central de gestion, serveur de médiation et serveur de périphérie, sur le serveur hôte.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtient des informations de disponibilité à partir de la configuration du client en ligne et la publie au matériel nuage connecteur sur le serveur hôte. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Enregistre les informations de l’appliance vers un site PSTN dans une configuration client en ligne. Une solution doit être enregistrée avant peuvent être déployé et géré par le service de gestion en nuage connecteur. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Supprime le fichier de sauvegarde de certification autorité service «\<SiteRootDirectory\>\CA\SfB CCE Root.p12 » dans le dossier de l’autorité de certification sous le répertoire de partage de site pour le connecteur sur le nuage.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Version 1.4.2 uniquement  <br/> |Réinstalle le serveur AD de service d’autorité de certification afin de créer un certificat de l’AC racine.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Version 1.4.2 uniquement  <br/> |Renouvelle les certificats de Cloud Connector lorsqu’ils arrivent à expiration ou une fois qu’ils ont expiré.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Réinitialise les serveurs d’autorité de certification pour installer un nouveau certificat d’autorité de certification.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Version 2.1 et version ultérieure  <br/> |Nettoie les informations d’identification et vous invite à entrer de nouveau toutes les informations d’identification utilisées pour le déploiement dans le nuage connecteur actuel.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Recherche les journaux d’appels entrants et sortants dans le répertoire des journaux de l’appliance Cloud Connector.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Définit le répertoire de travail sur le serveur hôte de nuage connecteur. Tous les fichiers de déploiement sont recensés dans cet annuaire.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Définit les identifiants du déploiement Cloud Connector existant.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Spécifie le chemin d’accès dans lequel le certificat pour le serveur de médiation ou le serveur Edge est enregistré.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Définit le répertoire dans lequel les fichiers de configuration de niveau site pour Cloud Connector sont conservés. Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Télécharge les bits nuage connecteur et le fichier msi de façon synchrone.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Génère le journal des appels entrants et sortants pour un appareil de connecteur dans le nuage.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Journal des appels pour un appareil de nuage connecteur cesse de génération entrantes et sortantes.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Déconnecte l’application en cours d’exécution et bascule vers un appareil nouvellement déployé ou de sauvegarde.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Désinstalle la solution de nuage connecteur en cours d’exécution sur le serveur hôte.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Annule l’enregistrement de la solution de nuage connecteur en cours d’un site PSTN dans la configuration du client en ligne.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Version 2.0 et ultérieures  <br/> |Réinstalle le serveur AD de service d’autorité de certification afin de créer un certificat de l’AC racine.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2.0 et ultérieures  <br/> |Renouvelle les certificats de Cloud Connector lorsqu’ils arrivent à expiration ou une fois qu’ils ont expiré.  <br/> |
   

