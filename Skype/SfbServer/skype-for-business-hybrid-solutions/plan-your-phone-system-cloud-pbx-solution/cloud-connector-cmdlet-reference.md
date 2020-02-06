---
title: Référence d'applets de commande pour Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: Le tableau suivant présente les applets de commande Skype Entreprise, version Cloud Connector, une brève description et des liens pour obtenir plus d’informations.
ms.openlocfilehash: c82d81fe19af7c0f305ce18e0bbce83f944b5d73
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803714"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
Le tableau suivant présente les applets de commande Skype Entreprise, version Cloud Connector, une brève description et des liens pour obtenir plus d’informations.
  
> [!NOTE]
> Vous devez exécuter tous les applets de commande sur l’hôte Cloud Connector, ainsi qu’une session PowerShell en tant qu’administrateur. 
  
|**Nom de l’applet de commande**|**Description**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 et ultérieure  <br/> |Sauvegarde le service d’autorité de certification sur un fichier et l’enregistre dans un dossier AC sous l’annuaire de sites :          <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de Cloud Connector.    <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prépare le serveur hôte de Cloud Connector au processus de mise à jour en le mettant en mode maintenance. Le matériel est "vidé"; ainsi, tous les appels existants seront terminés, mais les nouveaux appels seront refusés.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Quitte le mode de maintenance de mise à jour du serveur hôte de Cloud Connector.    <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exporte une configuration de Skype entreprise version Cloud Connector dans un fichier local sur le serveur hôte Cloud Connector Skype entreprise. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporte un fichier de configuration d’exemple Cloud Connector (. ini) vers le répertoire de l’application dans le répertoire des appareils Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 et ultérieure  <br/> |Exporte le certificat de l’AC racine vers un fichier local sur le serveur hôte de Cloud Connector.   <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Extrait l’annuaire de travail sur le serveur hôte de Cloud Connector. Tous les fichiers de déploiement sont recensés dans cet annuaire.    <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Affiche le répertoire actuel dans lequel sont stockés les journaux pour un appareil de connecteur Cloud.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2,1 et versions ultérieures  <br/> |Fournit des informations de diagnostic pour le dispositif de connexion Cloud.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Renvoie les identifiants du déploiement Cloud Connector existant.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Cloud Connector. L’utilisateur prépare ce certificat.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Ce dossier contient les fichiers d’installation de base VHD et Cloud Connector. Ce dossier doit être partagé avec toutes les autres applications d’un site Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Affiche le répertoire actuel dans lequel se trouvent les journaux au niveau du site pour le connecteur Cloud.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2.0 et ultérieures  <br/> |Renvoie la version de l’instance Cloud Connector. Get-CCVersion ne peut être utilisé que sur l’ordinateur hôte du Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Version 2.0 et ultérieures  <br/> |Permet d’importer la configuration de Skype entreprise version Cloud Connector à partir d’un fichier local sur le serveur hôte du Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installe le logiciel de connexion Cloud (y compris les machines virtuelles AD, Central Management, serveur de médiation et serveur de périphérie) sur le serveur hôte.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtient des informations de haute disponibilité dans la configuration de client en ligne et la publie sur le périphérique Cloud Connector sur le serveur hôte. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Enregistre les informations de l’appliance vers un site PSTN dans une configuration client en ligne. Un appareil doit être inscrit pour pouvoir être déployé et géré par le service de gestion de connecteurs Cloud. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 et ultérieure  <br/> |Supprime le fichier de sauvegarde du service de\<l'\>autorité de certification « SiteRootDirectory \CA\SfB CCE. p12 » dans le dossier ca sous le répertoire du partage de site pour le Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 et ultérieure  <br/> |Supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Version 1.4.2 uniquement  <br/> |Réinstalle le serveur AD de service d’autorité de certification afin de créer un certificat de l’AC racine.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Version 1.4.2 uniquement  <br/> |Renouvelle les certificats de Cloud Connector lorsqu’ils arrivent à expiration ou une fois qu’ils ont expiré.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 et ultérieure  <br/> |Réinitialise les serveurs d’autorité de certification pour installer un nouveau certificat d’autorité de certification.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Version 2,1 et versions ultérieures  <br/> |Nettoie les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement actuel du connecteur Cloud.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Recherche les journaux d’appels entrants et sortants dans le répertoire des journaux de l’appliance Cloud Connector.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Définit le répertoire de travail sur le serveur hôte du Cloud Connector. Tous les fichiers de déploiement sont recensés dans cet annuaire.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Définit les identifiants du déploiement Cloud Connector existant.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Spécifie le chemin d’accès dans lequel le certificat pour le serveur de médiation ou le serveur Edge est enregistré.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Définit le répertoire dans lequel les fichiers de configuration de niveau site pour Cloud Connector sont conservés. Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Télécharge de manière synchrone les fichiers.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Génère le journal des appels entrants et sortants pour un appareil de connecteur Cloud.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Arrête de générer le journal des appels entrants et sortants pour un appareil de connecteur Cloud.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Déconnecte l’application en cours d’exécution et bascule vers une nouvelle appliance déployée ou Backup.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Désinstalle l’appareil exécutant le connecteur Cloud du serveur hôte.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Annule l’inscription de l’appareil de connexion Cloud actuel d’un site PSTN dans la configuration de client en ligne.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Version 2.0 et ultérieures  <br/> |Réinstalle le serveur AD de service d’autorité de certification afin de créer un certificat de l’AC racine.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2.0 et ultérieures  <br/> |Renouvelle les certificats de Cloud Connector lorsqu’ils arrivent à expiration ou une fois qu’ils ont expiré.  <br/> |
   

