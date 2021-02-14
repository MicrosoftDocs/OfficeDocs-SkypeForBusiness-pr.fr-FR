---
title: Référence d’applet de commande Cloud Connector
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
description: Le tableau suivant répertorie les cmdlets de la version Cloud Connector de Skype Entreprise avec une brève description et des liens vers plus d’informations.
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359050"
---
# <a name="cloud-connector-cmdlet-reference"></a>Référence d’applet de commande Cloud Connector
 
> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Le tableau suivant répertorie les cmdlets de la version Cloud Connector de Skype Entreprise avec une brève description et des liens vers plus d’informations.
  
> [!NOTE]
> Vous devez exécuter toutes les cmdlets sur l’ordinateur hôte Cloud Connector et exécuter la session PowerShell en tant qu’administrateur. 
  
|**Nom de l'applet de commande**|**Description**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Sauvegarde le service d’autorité de certification dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous l’annuaire de partage de sites.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crée un fichier de disque dur virtuel de base (VHDX) à l’aide d’un fichier ISO fourni par un client pour Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement deCloud Connector.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prépare le serveur hôte Cloud Connector pour le processus de mise à jour en le mettant en mode maintenance. L’appliance est « drainée » ; autrement dit, tous les appels existants seront terminés, mais les nouveaux appels sont rejetés.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Quitte le mode maintenance des mises à jour sur le serveur hôte Cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exporte une configuration Skype Entreprise, version Cloud Connector vers un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporte un exemple de fichier de configuration Cloud Connector (.ini) dans l’annuaire d’appliances d’une appliance Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Exporte le certificat d’ac racine vers un fichier local sur le serveur hôte Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Extrait le répertoire de travail sur le serveur hôte Cloud Connector. Tous les fichiers de déploiement sont stockés dans ce répertoire.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Indique le répertoire actuel dans lequel les journaux d’une appliance Cloud Connector sont stockés.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2.1 et ultérieures  <br/> |Fournit des informations de diagnostic pour l’appliance Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Renvoie les informations d’identification du déploiement Cloud Connector actuel.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Renvoie le chemin d’accès au fichier de certificat externe pour le déploiement Cloud Connector. L’utilisateur prépare ce certificat.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Indique le répertoire actuel dans lequel les fichiers de configuration au niveau du site sont stockés. Le dossier contient les fichiers d’installation de base de VHD et Cloud Connector. Ce dossier doit être partagé avec toutes les autres appliances d’un site Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Indique le répertoire actuel dans lequel sont stockés les journaux au niveau du site pour Cloud Connector.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2.0 et ultérieures  <br/> |Renvoie la version sur l’instance Cloud Connector. Get-CCVersion ne peut être utilisé que dans l’ordinateur hôte de Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Version 2.0 et ultérieures  <br/> |Importe la configuration de la version Cloud Connector de Skype Entreprise à partir d’un fichier local vers le serveur hôte Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installe l’appliance Cloud Connector, y compris les machines virtuelles AD, Central Management Store, Mediation Server et Edge Server, sur le serveur hôte.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtient les informations de haute disponibilité de la configuration du client en ligne et les publie dans l’appliance Cloud Connector sur le serveur hôte. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Enregistre les informations de l’appliance sur un site PSTN dans une configuration client en ligne. Une appliance doit être inscrite avant de pouvoir être déployée et gérée par le service de gestion Cloud Connector. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Supprime le fichier de sauvegarde du service d’autorité de certification « \<SiteRootDirectory\> \CA\SfB CCE Root.p12 » dans le dossier de l’autorité de certification sous l’annuaire de partage de sites pour Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Supprime les certificats de serveur hérités sur le magasin central de gestion, le serveur de médiation et le serveur Edge après avoir exécuté les cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Version 1.4.2 uniquement  <br/> |Réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Version 1.4.2 uniquement  <br/> |Renouvelle les certificats pour Cloud Connector lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 et versions ultérieures  <br/> |Réinitialise les serveurs d’autorité de certification pour installer un nouveau certificat d’autorité de certification.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Version 2.1 et ultérieures  <br/> |Nettoie les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement cloud connector actuel.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Recherche les journaux des appels entrants et sortants dans l’annuaire des journaux de l’appliance Cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Définit le répertoire de travail sur le serveur hôte Cloud Connector. Tous les fichiers de déploiement sont stockés dans ce répertoire.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Définit les informations d’identification du déploiement Cloud Connector actuel.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Spécifie le chemin d’accès où le certificat pour le serveur de médiation ou le serveur Edge est stocké  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Définit le répertoire dans lequel les fichiers de configuration au niveau du site pour Cloud Connector seront stockés. Le dossier contient les fichiers de configuration vhD de base et Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Télécharge les bits et le fichier msi Cloud Connector de manière synchrone.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Génère le journal des appels entrants et sortants pour une appliance Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Arrête de générer le journal des appels entrants et sortants pour une appliance Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Déconnecte l’appliance en cours d’exécution et bascule vers une appliance nouvellement déployée ou de sauvegarde.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Désinstalle l’appliance Cloud Connector en cours d’exécution du serveur hôte.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Désinsère l’appliance Cloud Connector actuelle d’un site PSTN dans la configuration client en ligne.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Version 2.0 et ultérieures  <br/> |Réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2.0 et ultérieures  <br/> |Renouvelle les certificats pour Cloud Connector lorsqu’ils sont sur le point d’expirer ou qu’ils ont déjà expiré.  <br/> |
   

