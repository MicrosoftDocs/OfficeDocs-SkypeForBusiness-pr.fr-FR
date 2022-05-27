---
title: Référence d’applet de commande Cloud Connector
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
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: Le tableau suivant répertorie les applets de commande Skype Entreprise Cloud Connector Edition avec une brève description et des liens vers plus d’informations.
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676166"
---
# <a name="cloud-connector-cmdlet-reference"></a>Référence d’applet de commande Cloud Connector

> [!Important]
> Cloud Connector Edition prendra sa retraite le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau de téléphonie local à Teams à l’aide du [routage direct](/MicrosoftTeams/direct-routing-landing-page).

Le tableau suivant répertorie les applets de commande Skype Entreprise Cloud Connector Edition avec une brève description et des liens vers plus d’informations.
  
> [!NOTE]
> Vous devez exécuter toutes les applets de commande sur l’ordinateur hôte Cloud Connector, et vous devez exécuter la session PowerShell en tant qu’administrateur. 
  
|Nom de l’applet de commande**|Description|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> Version 1.4.2 et ultérieure|Sauvegarde le service d’autorité de certification dans un fichier et l’enregistre dans le dossier de l’autorité de certification sous le répertoire de partage de sites.|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|Crée un fichier de disque dur virtuel de base (VHDX) à l’aide d’un fichier ISO fourni par le client Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement deCloud Connector.|
|[Enter-CcUpdate](enter-ccupdate.md)|Prépare le serveur hôte Cloud Connector pour le processus de mise à jour en le mettant en mode maintenance. L’appliance est « drainée » ; autrement dit, tous les appels existants seront terminés, mais les nouveaux appels sont rejetés.|
|[Exit-CcUpdate](exit-ccupdate.md)|Quitte le mode de maintenance de mise à jour sur le serveur hôte Cloud Connector.|
|[Export-CcConfiguration](export-ccconfiguration.md)|Exporte une configuration Skype Entreprise Cloud Connector Edition vers un fichier local sur le serveur hôte Skype Entreprise Cloud Connector Edition.|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|Exporte un exemple de fichier de configuration Cloud Connector (.ini) dans le répertoire d’appliance d’une appliance Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> Version 1.4.2 et ultérieure|Exporte le certificat d’autorité de certification racine vers un fichier local sur le serveur hôte Cloud Connector.|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|Récupère le répertoire de travail sur le serveur hôte Cloud Connector. Tous les fichiers de déploiement sont stockés dans ce répertoire.|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|Affiche le répertoire actuel dans lequel sont stockés les journaux d’activité d’une appliance Cloud Connector.|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> Version 2.1 et ultérieure|Fournit des informations de diagnostic pour l’appliance Cloud Connector.|
|[Get-CcCredential](get-cccredential.md)|Retourne les informations d’identification du déploiement actuel de Cloud Connector.|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|Retourne le chemin du fichier de certificat externe pour le déploiement de Cloud Connector. L’utilisateur prépare ce certificat.|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|Affiche le répertoire actuel où sont stockés les fichiers de configuration au niveau du site. Le dossier contient les fichiers d’installation du disque dur virtuel de base et du connecteur cloud. Ce dossier doit être partagé avec toutes les autres appliances d’un site Cloud Connector.|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|Affiche le répertoire actuel dans lequel sont stockés les journaux d’activité au niveau du site pour Cloud Connector.|
|[Get-CcVersion](get-ccversion.md) <p> Version 2.0 et ultérieure|Retourne la version sur l’instance de Cloud Connector. Get-CCVersion ne peut être utilisé que dans l’ordinateur hôte de Cloud Connector.|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> Version 2.0 et ultérieure|Importe la configuration Skype Entreprise Cloud Connector Edition à partir d’un fichier local vers le serveur hôte Cloud Connector.|
|[Install-CcAppliance](install-ccappliance.md)|Installe l’appliance Cloud Connector, y compris les machines virtuelles AD, Central Management Store, Mediation Server et Edge Server, sur le serveur hôte.|
|[Publish-CcAppliance](publish-ccappliance.md)|Obtient les informations de haute disponibilité de la configuration du locataire en ligne et les publie sur l’appliance Cloud Connector sur le serveur hôte.|
|[Register-CcAppliance](register-ccappliance.md)|Inscrit les informations de l’appliance sur un site RTC dans une configuration de locataire en ligne. Une appliance doit être inscrite avant de pouvoir être déployée et gérée par le service de gestion cloud connecteur.|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> Version 1.4.2 et ultérieure|Supprime le fichier de sauvegarde du service d’autorité de certification «\<SiteRootDirectory\> \CA\SfB CCE Root.p12 » dans le dossier de l’autorité de certification sous le répertoire de partage de site pour Cloud Connector.|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> Version 1.4.2 et ultérieure|Supprime les certificats de serveur hérités sur le magasin de gestion centrale, le serveur de médiation et le serveur Edge après avoir exécuté les applets de commande Renew-CcCACertificate ou Renouveler CcServerCertificate.|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> Version 1.4.2 uniquement|Réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine.|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> Version 1.4.2 uniquement|Renouvelle les certificats pour Cloud Connector lorsqu’ils sont proches d’expiration ou déjà arrivés à expiration.|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> Version 1.4.2 et ultérieure|Réinitialise les serveurs d’autorité de certification pour installer un nouveau certificat d’autorité de certification.|
|[Restore-CcCredentials](restore-cccredentials.md) <p> Version 2.1 et ultérieure|Nettoie les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement actuel de Cloud Connector.|
|[Search-CcLog](search-cclog.md)|Recherche les journaux d’appels entrants et sortants dans le répertoire du journal de l’appliance Cloud Connector|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|Définit le répertoire de travail sur le serveur hôte Cloud Connector. Tous les fichiers de déploiement sont stockés dans ce répertoire.|
|[Set-CcCredential](set-cccredential.md)|Définit les informations d’identification du déploiement actuel de Cloud Connector.|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|Spécifie le chemin d’accès où le certificat pour le serveur de médiation ou le serveur Edge est stocké|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|Définit le répertoire dans lequel les fichiers de configuration au niveau du site pour Cloud Connector seront stockés. Le dossier contient les fichiers de configuration du disque dur virtuel de base et du connecteur cloud.|
|[Start-CcDownload](start-ccdownload.md)|Télécharge les bits Cloud Connector et le fichier msi de façon synchrone.|
|[Start-CcLogging](start-cclogging.md)|Génère le journal des appels entrants et sortants pour une appliance Cloud Connector.|
|[Stop-CcLogging](stop-cclogging.md)|Arrête de générer le journal des appels entrants et sortants pour une appliance Cloud Connector.|
|[Switch-CcVersion](switch-ccversion.md)|Déconnecte l’appliance en cours d’exécution et bascule vers une appliance nouvellement déployée ou de sauvegarde.|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|Désinstalle l’appliance Cloud Connector en cours d’exécution à partir du serveur hôte.|
|[Unregister-CcAppliance](unregister-ccappliance.md)|Annule l’inscription de l’appliance Cloud Connector actuelle à partir d’un site PSTN dans la configuration de locataire en ligne.|
|[Update-CcCACertificate](update-cccacertificate.md) <p> Version 2.0 et ultérieure|Réinstalle le serveur AD du service d’autorité de certification pour créer un certificat d’autorité de certification racine.|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> Version 2.0 et ultérieure|Renouvelle les certificats pour Cloud Connector lorsqu’ils sont proches d’expiration ou déjà arrivés à expiration.|
