---
title: Référence d'applets de commande pour Cloud Connector
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
ms.openlocfilehash: 5528b7ef5d2fe0ccfab680f2300b444f0532a059
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="cloud-connector-cmdlet-reference"></a>Référence d'applets de commande pour Cloud Connector
 
Le tableau suivant présente les applets de commande Skype Entreprise, version Cloud Connector, une brève description et des liens pour obtenir plus d’informations.
  
> [!NOTE]
> Vous devez exécuter tous les applets de commande sur l’hôte Cloud Connector, ainsi qu’une session PowerShell en tant qu’administrateur. 
  
|**Nom de l’applet de commande**|**Description**|
|:-----|:-----|
|[Sauvegarde-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 et suivantes  <br/> |Sauvegarde le service d’autorité de certification sur un fichier et l’enregistre dans un dossier AC sous l’annuaire de sites :      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de Cloud Connector.    <br/> |
|[Entrez-CcUpdate](enter-ccupdate.md) <br/> |Prépare le serveur hôte de Cloud Connector au processus de mise à jour en le mettant en mode maintenance. La solution matérielle-logicielle est « purgé ; » Autrement dit, tous les appels en cours seront termine, mais nouveaux appels sont rejetés.  <br/> |
|[Quitter-CcUpdate](exit-ccupdate.md) <br/> |Quitte le mode de maintenance de mise à jour du serveur hôte de Cloud Connector.    <br/> |
|[Exportation-CcConfiguration](export-ccconfiguration.md) <br/> | Exporte une configuration Skype Entreprise, version Cloud Connector vers un fichier local sur le serveur hôte Skype Entreprise, version Cloud Connector. <br/> |
|[Exportation-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporte un fichier de configuration de l’exemple Connecteur de nuage (.ini) vers le répertoire de la solution matérielle-logicielle d’un appareil de connecteur de nuage. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.  <br/> |
|[Exportation-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 et suivantes  <br/> |Exporte le certificat de l’AC racine vers un fichier local sur le serveur hôte de Cloud Connector.   <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Extrait l’annuaire de travail sur le serveur hôte de Cloud Connector. Tous les fichiers de déploiement sont recensés dans cet annuaire.    <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Affiche le répertoire en cours où sont stockés les journaux pour un appareil de connecteur de nuage...  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2.1 et version ultérieure  <br/> |Fournit des informations de diagnostic pour la solution matérielle-logicielle connecteur de nuage.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Renvoie les identifiants du déploiement Cloud Connector existant.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Renvoie le chemin d’accès du fichier du certificat externe pour le déploiement de Cloud Connector. L’utilisateur prépare ce certificat.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Affiche le répertoire dans lequel sont actuellement conservés les fichiers de configuration de niveau site. Le dossier contient les fichiers d’installation de disque dur virtuel et de nuage connecteur base. Ce dossier doit être partagé avec tous les autres équipements d’un site connecteur du nuage.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Affiche le répertoire en cours où se trouvent les journaux de niveau site pour connecteur de nuage.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2.0 et suivantes  <br/> |Renvoie la version sur l'instance Cloud Connector. Get-CCVersion peut uniquement être utilisé dans l'hôte de Cloud Connector.  <br/> |
|[Importation-CcConfiguration](import-ccconfiguration.md) <br/> Version 2.0 et ultérieures  <br/> |Importe le Skype pour la configuration du connecteur de Cloud Business Edition à partir d’un fichier local sur le serveur hôte de connecteur de nuage.  <br/> |
|[Installation-CcAppliance](install-ccappliance.md) <br/> |Installe l’application Connecteur de nuage — y compris de la publicité, ordinateurs virtuels magasin Central de gestion, serveur de médiation et serveur de transport Edge, sur le serveur hôte.  <br/> |
|[Publication-CcAppliance](publish-ccappliance.md) <br/> | Obtient les informations de disponibilité à partir de la configuration des clients en ligne et le publie à l’appliance de nuage connecteur sur le serveur hôte. <br/> |
|[Registre-CcAppliance](register-ccappliance.md) <br/> | Enregistre les informations de l’appliance vers un site PSTN dans une configuration client en ligne. Une solution matérielle-logicielle doit être enregistré avant de pouvoir être déployé et géré par le service de gestion de Cloud connecteur. <br/> |
|[Supprimer-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 et suivantes  <br/> |Supprime le fichier de sauvegarde de certification autorité service "\<SiteRootDirectory\>\CA\SfB CCE Root.p12 » dans le dossier de l’autorité de certification sous le répertoire de partage de site pour connecteur de nuage.  <br/> |
|[Supprimer-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 et suivantes  <br/> |Supprime les certificats de l’ancien serveur sur le magasin central de gestion, le serveur de médiation et le serveur Edge après l’exécution des applets de commande Renew-CcCACertificate ou Renew CcServerCertificate.  <br/> |
|[Renouveler-CcCACertificate](renew-cccacertificate.md) <br/> Version 1.4.2 uniquement  <br/> |Réinstalle le serveur AD de service d’autorité de certification afin de créer un certificat de l’AC racine.  <br/> |
|[Renouveler-CcServerCertificate](renew-ccservercertificate.md) <br/> Version 1.4.2 uniquement  <br/> |Renouvelle les certificats de Cloud Connector lorsqu’ils arrivent à expiration ou une fois qu’ils ont expiré.  <br/> |
|[Réinitialisation-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 et suivantes  <br/> |Réinitialise les serveurs d’autorité de certification pour installer un nouveau certificat d’autorité de certification.  <br/> |
|[Restauration-CcCredentials](restore-cccredentials.md) <br/> Version 2.1 et version ultérieure  <br/> |Nettoie les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement de Cloud connecteur en cours.  <br/> |
|[Recherche-CcLog](search-cclog.md) <br/> |Recherche les journaux d’appels entrants et sortants dans le répertoire des journaux de l’appliance Cloud Connector.  <br/> |
|[Ensemble-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Définit le répertoire de travail sur le serveur hôte de connecteur de nuage. Tous les fichiers de déploiement sont recensés dans cet annuaire.  <br/> |
|[Ensemble-CcCredential](set-cccredential.md) <br/> |Définit les identifiants du déploiement Cloud Connector existant.  <br/> |
|[Ensemble-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Spécifie le chemin d’accès dans lequel le certificat pour le serveur de médiation ou le serveur Edge est enregistré.  <br/> |
|[Ensemble-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Définit le répertoire dans lequel les fichiers de configuration de niveau site pour Cloud Connector sont conservés. Le dossier contient les fichiers de configuration de base de VHD et Cloud Connector.  <br/> |
|[Démarrer-CcDownload](start-ccdownload.md) <br/> |Télécharge les bits du connecteur du nuage et le fichier msi de façon synchrone.  <br/> |
|[Démarrer-CcLogging](start-cclogging.md) <br/> |Génère le journal des appels entrants et sortants pour un appareil de connecteur de nuage.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Journal des appels cesse de génération entrants et sortants pour un appareil de connecteur de nuage.  <br/> |
|[Commutateur-CcVersion](switch-ccversion.md) <br/> |Déconnecte l'appliance et les commutateurs exécutés d'une appliance récemment déployée ou de sauvegarde.    <br/> |
|[CcAppliance-désinstaller](uninstall-ccappliance.md) <br/> |Désinstalle l’application Connecteur de nuage en cours d’exécution sur le serveur hôte.  <br/> |
|[Annuler l’inscription-CcAppliance](unregister-ccappliance.md) <br/> |Annule l’inscription de la solution de Cloud connecteur en cours à partir d’un site RTPC dans la configuration de clients en ligne.  <br/> |
|[Mise à jour-CcCACertificate](update-cccacertificate.md) <br/> Version 2.0 et suivantes  <br/> |Réinstalle le serveur AD de service d’autorité de certification afin de créer un certificat de l’AC racine.  <br/> |
|[Mise à jour-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2.0 et suivantes  <br/> |Renouvelle les certificats de Cloud Connector lorsqu’ils arrivent à expiration ou une fois qu’ils ont expiré.  <br/> |
   

