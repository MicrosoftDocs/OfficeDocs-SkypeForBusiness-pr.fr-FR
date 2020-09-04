---
title: Résolution des problèmes de votre déploiement Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Dépannez votre déploiement de Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359330"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Résolution des problèmes de votre déploiement Cloud Connector

> [!Important]
> La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online. Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Dépannez votre déploiement de Cloud Connector Edition.
  
Cette rubrique décrit les solutions aux problèmes courants liés aux déploiements de Cloud Connector Edition. Si vous rencontrez des problèmes avec les appels vers et à partir du réseau téléphonique commuté (RTC), vous pouvez examiner les solutions décrites dans cette rubrique.
  
Cloud Connector fournit des mécanismes intégrés permettant de résoudre automatiquement certains problèmes. Un processus de détection automatique recherche les problèmes potentiels liés aux appareils Cloud Connector et, dans la mesure du possible, prend des mesures correctives pour résoudre ces problèmes sans intervention de l’administrateur. Le processus de détection fonctionne comme suit :
  
- **Séquence de détection :** Le service de gestion de Cloud Connector exécute un processus toutes les 60 secondes pour détecter si une appliance est en panne. Dans la version 2,0 de Cloud Connector et les versions ultérieures, le processus de détection utilise le commutateur de gestion des appels Skype entreprise pour établir des connexions PowerShell aux machines Cloud Connector ; pour les versions antérieures à 2,0, le processus de détection utilise le commutateur de gestion Cloud Connector.
    
    > [!NOTE]
    > Pour que la récupération automatique réussisse, il doit y avoir une connectivité réseau entre l’hôte et les machines virtuelles sur le commutateur réseau de l’hôte. Veillez à vérifier la connectivité réseau pour vous assurer que la détection et la récupération automatiques peuvent réussir. 
  
- **Surveillance :** Les services suivants sont surveillés dans Cloud Connector version 2,0 et versions ultérieures :
    
  - Les machines virtuelles ne sont pas connectées aux commutateurs virtuels d’entreprise ou Internet de Cloud Connector
    
  - Les machines virtuelles sont dans un état enregistré ou arrêté
    
  - Services de serveur de gestion centralisée : RÉPLICA, maître
    
  - Services de serveur de médiation : RÉPLICA, RTCSRV et MEDSVC
    
  - Services serveur Edge : RÉPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Les règles de pare-feu entrant sont désactivées pour le RTCSRV de CS sur le serveur Edge, CS RTCMEDSRV sur le serveur de médiation
    
    Dans la version 1.4.2 de Cloud Connector, seuls les services suivants sont surveillés :
    
  - Services de serveur de médiation : RTCSRV et MEDSVC
    
  - Service serveur Edge : RTCSRV
    
- **Processus de récupération :** Si des services surveillés sont en panne, une appliance est marquée comme étant inactive et les services sont arrêtés et corrigés manuellement jusqu’à ce que tous les problèmes puissent être résolus. Cela empêchera les appels de routage vers une appliance susceptible de provoquer des échecs d’appel.
    
    Le service de gestion Cloud Connector relance la récupération automatique comme suit
    
  - L’intervalle de nouvelle tentative initiale est de dix secondes, avec un intervalle maximal d’une heure.
    
  - Pour les trois premières tentatives de récupération, la durée de l’intervalle est de 10 secondes. À partir de la quatrième nouvelle tentative, le temps de l’intervalle augmente de deux fois l’intervalle de temps précédent. Par exemple, la quatrième tentative se produira dans 20 secondes, la cinquième en 40 secondes, et ainsi de suite. 
    
  - Lorsque l’intervalle maximal d’une heure est atteint, les tentatives se poursuivent une fois par heure.
    
  - Lorsque la récupération réussit, l’intervalle et le nombre de nouvelles tentatives sont définis sur leurs valeurs initiales.
    
  - Si le service de gestion est redémarré, l’intervalle et le nombre de nouvelles tentatives sont réinitialisés à leurs valeurs initiales.
    
## <a name="troubleshooting"></a>Résolution des problèmes

Voici des solutions aux problèmes rencontrés couramment :
  
- **Problème : le déploiement échoue ou cesse de répondre lors de l’exécution des scripts de déploiement. Après l’ouverture de session sur chaque machine virtuelle, l’adresse IP est manquante ou incorrecte pour la carte d’interface réseau (NIC) de gestion/interne/externe.**
    
    **Résolution :** Ce problème ne peut pas être résolu automatiquement. Les cartes réseau ne peuvent pas être ajoutées aux machines virtuelles lorsqu’elles sont en cours d’exécution. Veuillez arrêter et supprimer ces machines virtuelles dans le Gestionnaire Hyper-v, puis exécutez les applets de commande suivantes :
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problème : après l’installation du serveur et de la forêt Active Directory, le serveur CMS et/ou le serveur de médiation n’ont pas correctement rejoint le domaine.**
    
    **Résolution :** Pour résoudre ce problème, procédez comme suit :
    
  - Ouvrez une session sur le serveur Active Directory et vérifiez que le domaine a été correctement créé.
    
  - Ouvrez une session sur le serveur CMS/médiation et vérifiez que sur la carte d’entreprise (corpnet) une adresse IP valide est attribuée, et que l’adresse IP et le DNS statiques valides sont configurés en tant qu’adresse IP du serveur AD.
    
  - Ouvrez une session sur le serveur CMS/médiation, puis ouvrez une invite de commandes. Assurez-vous que vous pouvez exécuter la commande ping sur le nom de domaine complet et l’adresse IP du serveur Active Directory. Si ce n’est pas le cas, il peut y avoir un conflit d’adresse IP. Essayez d’affecter une nouvelle adresse IP pour Active Directory et mettez à jour DNS sur le serveur CMS/médiation en conséquence.
    
- **Problème : vous recevez le message d’erreur suivant : «Remove-VMSwitch : failed lors de la suppression du commutateur Ethernet virtuel. Le commutateur virtuel’Cloud Connector Management switch’ne peut pas être supprimé, car il est utilisé par des ordinateurs virtuels en cours d’exécution ou attribué à des pools enfants. "**
    
    **Résolution :** Le « commutateur de gestion de Cloud Connector » n’a pas été supprimé après le déploiement. Si vous avez rencontré cette erreur, reportez-vous au Gestionnaire Hyper-v et vérifiez qu’il n’y a pas encore de machine virtuelle connectée. Si des machines virtuelles sont toujours connectées, déconnectez-les et supprimez le commutateur de gestion. Si le commutateur de gestion ne peut toujours pas être supprimé, redémarrez le serveur hôte et réessayez.
    
- **Problème : vous recevez le message d’erreur suivant : «le service RTCMRAUTH n’a pas pu démarrer. Vérifiez que le service n’est pas désactivé. "**
    
    > [!NOTE]
    > Ce problème concerne uniquement les versions de Cloud Connector antérieures à la version 1.4.2. 
  
    L’échec de démarrage peut également être dû au fait que ce serveur frontal était précédemment basculé (avec basculement de l’ordinateur). Si c’est le cas, appelez la restauration automatique (à l’aide de la restauration automatique de l’ordinateur).
    
    **Résolution :** Ce problème se produit sur un serveur Edge lorsque le certificat de l’autorité de certification racine ou le certificat de l’autorité de certification intermédiaire n’est pas approuvé par le serveur Edge. Même si le certificat externe peut être importé, mais que la chaîne de certificats est rompue. Dans cette condition, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.
    
    Importez manuellement le certificat de l’AC racine et tous les certificats de l’autorité de certification intermédiaire de votre certificat externe dans le serveur Edge, puis redémarrez le serveur Edge. Après avoir vu les services RTCMRAUTH et RTCSRV démarrés sur le serveur Edge, revenez à votre serveur hôte, lancez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour basculer vers le nouveau déploiement :
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problème : le serveur hôte a redémarré lorsque des mises à jour Windows ont été appliquées et les appels service par le serveur échouent.**
    
    **Résolution :** Si vous avez déployé un environnement de haute disponibilité, Microsoft fournit une cmdlet pour vous aider à déplacer un ordinateur hôte (instance de déploiement) à l’intérieur ou à l’extérieur de la topologie actuelle lors de la vérification et de l’installation manuelle de Windows Update. Pour ce faire, procédez comme suit :
    
1. Sur le serveur hôte, démarrez une console PowerShell en tant qu’administrateur, puis exécutez :
    
   ```powershell
   Enter-CcUpdate
   ```

2. Recherchez les mises à jour et installez celles qui sont disponibles.
    
3. Dans la console PowerShell, exécutez l’applet de commande suivante :
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problème : lorsqu’un appel est effectué à partir d’un client Skype entreprise à l’aide d’un numéro RTC, l’appel ne peut pas être remonté vers une conférence en invitant un autre numéro RTC.**
    
    **Résolution :** Pour résoudre ce problème, reportez-vous à la rubrique [configure Online Hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problème : un message d’avertissement s’affiche à propos de Windows Update lors de l’installation d’Active Directory Server : «la mise à jour automatique de Windows n’est pas activée. Pour vous assurer que votre rôle ou votre fonctionnalité nouvellement installée est automatiquement mis à jour, activez Windows Update. "**
    
    **Résolution :** Lancez une session PowerShell à distance du client à l’aide des informations d’identification de l’administrateur client de Skype entreprise, puis exécutez l’applet de commande suivante pour vérifier la configuration de _EnableAutoUpdate_ de votre site :
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Si  _EnableAutoUpdate_ a la valeur **true**, vous pouvez ignorer ce message d’avertissement en toute sécurité, car le service CCEManagement gère le téléchargement et l’installation des mises à jour Windows pour les machines virtuelles et le serveur hôte. Si  _EnableAutoUpdate_ a la valeur **false**, exécutez la cmdlet suivante pour lui affecter la valeur **true**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Vous pouvez également vérifier et installer manuellement les mises à jour. Voir la section suivante.
    
- **Problème : vous recevez un message d’erreur : impossible d’enregistrer l’appliance, car votre entrée/configuration actuelle ou ou, ou \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> ou \<Mediation Server IP Address\> en conflit avec une ou plusieurs Appliances existantes. Supprimez l’appliance Conflict ou mettez à jour vos informations d’entrée/configuration, puis réinscrivez-vous. 'lors de l’exécution de Register-applet ccappliance pour inscrire l’appliance actuelle sur Online.**
    
    **Résolution :** Les valeurs pour \<ApplianceName\> le \<Mediation Server FQDN\> et \<Mediation Server IP Address\> doivent être uniques et utilisées uniquement pour l’enregistrement d’une appliance. Par défaut, \<ApplianceName\> provient du nom d’hôte. \<Mediation Server FQDN\> et \<Mediation Server IP Address\> défini dans le fichier ini de configuration.
    
    Par exemple, l’utilisation de (Appliance = MyserverNew, nom de domaine complet du serveur de médiation = ms. contoso. com, adresse IP du serveur de médiation = 10.10.10.10) pour s’enregistrer sur SiteName = monsite, mais s’il existe un équipement enregistré (Appliance = monserveur, nom de domaine complet du serveur de médiation = ms. contoso. com, adresse IP du serveur de médiation)
    
    Tout d’abord, vérifiez votre fichier CloudConnector.ini dans la section Directory ApplianceRoot. Vous obtiendrez \<SiteName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> les valeurs et dans le fichier. \<ApplianceName\> est le nom de votre serveur hôte.
    
    Deuxièmement, lancez le client distant PowerShell à l’aide de vos informations d’identification d’administrateur client Skype entreprise, puis exécutez l’applet de commande suivante pour vérifier les appliances inscrites.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Après avoir identifié les conflits, vous pouvez soit mettre à jour votre fichier CloudConnector.ini avec les informations correspondant à l’appliance enregistrée, soit annuler l’inscription de l’appliance existante pour résoudre les conflits.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problème : l’applet de commande Get-applet ccrunningversion ne renvoie une valeur vide si une appliance déployée est en cours d’exécution sur l’hôte.**
    
  **Résolution :** Cela peut se produire lorsque vous effectuez une mise à niveau depuis version 1.3.4 ou 1.3.8 vers 1.4.1. Après avoir installé la version 1.4.1 avec le. msi, vous devez exécuter `Register-CcAppliance` avant d’exécuter toute autre cmdlet. `Register-CcAppliance` migre le fichier module.ini de%UserProfile%\CloudConnector vers%ProgramData%\CloudConnector. Si vous l’avez manqué, un nouveau module.ini sera créé dans le dossier%ProgramData%\CloudConnector et remplacera les informations de version en cours d’exécution/sauvegarde pour version 1.3.4 ou 1.3.8.
    
  Comparez les fichiers module.ini dans le dossier%UserProfile%\CloudConnector et%ProgramData%\CloudConnector. S’il existe des différences, supprimez le fichier module.ini dans%ProgramData%\CloudConnector et réexécutez  `Register-CcAppliance` . Vous pouvez également modifier manuellement le fichier vers la version d’exécution et de sauvegarde correcte.
    
- **Problème : après avoir exécuté la cmdlet Switch-CcVersion pour basculer vers une ancienne version différente de la version du script actuelle, il n’existe pas de prise en charge de la haute disponibilité pour cette ancienne version.**
    
    **Résolution :** Par exemple, vous avez effectué une mise à niveau de 1.4.1 vers 1.4.2. Votre version de script actuelle, qui peut être déterminée en exécutant `Get-CcVersion` , et votre version en cours d’exécution, qui peut être déterminée en exécutant  `Get-CcRunningVersion` sont les deux 1.4.2. Pour l’instant, si vous exécutez `Switch-CcVersion` pour rebasculer la version en cours d’exécution vers la version 1.4.1, il n’y aura pas de prise en charge de la haute disponibilité pour cette ancienne version.
    
    Pour obtenir une prise en charge complète de la haute disponibilité, revenez à la version 1.4.2, de sorte que la version en cours d’exécution et la version de script sont les mêmes. Si vous rencontrez des problèmes avec votre déploiement 1.4.2, veuillez le désinstaller et le réinstaller dès que possible.
    
- **Problème : les certificats de l’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**
    
    **Résolution :** Les certificats de l’autorité de certification Skype entreprise sont valides pendant cinq ans. Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides pendant deux ans.
    
    > [!NOTE]
    > Dans la version 2,0 de Cloud Connector et les versions ultérieures, la cmdlet Renew-CcServerCertificate a été remplacée par Update-CcServerCertificate et la cmdlet Renew-applet cccacertificate a été remplacée par Update-applet cccacertificate. 
  
    Si les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis, exécutez l’applet de commande Renew-CcServerCertificate ou Update-CcServerCertificate pour renouveler vos certificats.
    
    Si les certificats de l’autorité de certification sont à proximité de l’expiration, exécutez l’applet de commande Renew-applet cccacertificate ou Update-applet cccacertificate pour renouveler vos certificats.
    
    **Si les certificats de l’autorité de certification sont compromis et qu’il n’y a qu’une seule Appliance dans le site,** procédez comme suit :
    
1. Exécutez la cmdlet Enter-applet ccupdate pour drainer les services et placer l’appliance en mode maintenance.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Exécutez les applets de commande suivantes pour réinitialiser et créer les nouveaux certificats de l’autorité de certification et tous les certificats de serveur interne :
    
    Pour les versions de Cloud Connector antérieures à 2,0 :
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou pour Cloud Connector version 2,0 et versions ultérieures :
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de commande Export-applet ccrootcertificate à partir de l’appliance, puis installez le certificat exporté sur vos passerelles RTC. Vous devrez peut-être également relancer le certificat sur votre passerelle.

   ```powershell
   Export-CcRootCertificate
   ```

4. Exécutez la cmdlet Exit-applet ccupdate pour démarrer les services et quitter le mode maintenance.

   ```powershell
   Exit-CcUpdate
   ```


    **Si les certificats de l’autorité de certification sont compromis et qu’il y a plusieurs Appliances dans le site,** effectuez les étapes séquentielles suivantes sur chaque appliance du site.
    
    Microsoft vous recommande d’effectuer ces étapes en dehors des heures de pointe.
    
1. Sur la première appliance, exécutez la cmdlet Remove-applet cccertificationauthorityfile pour nettoyer les fichiers de sauvegarde de l’autorité de certification dans le \<SiteRoot\> répertoire.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Exécutez la cmdlet Enter-applet ccupdate pour purger les services et placez chaque appliance en mode maintenance.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Sur la première appliance, exécutez les applets de commande suivantes pour réinitialiser et créer de nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :
    
     Pour les versions de Cloud Connector antérieures à 2,0 :
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou pour Cloud Connector version 2,0 et versions ultérieures :
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. Sur la première appliance, exécutez l’applet de commande suivante pour sauvegarder les fichiers de l’autorité de certification dans le \<SiteRoot\> dossier.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Sur toutes les autres Appliances du même site, exécutez les commandes suivantes pour consommer les fichiers de sauvegarde de l’autorité de certification, afin que les applications utilisent le même certificat racine, puis demandez de nouveaux certificats. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de commande Export-applet ccrootcertificate à partir de n’importe quelle Appliance dans le site, puis installez le certificat exporté sur vos passerelles RTC. Vous devrez peut-être également relancer le certificat sur votre passerelle.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Exécutez la cmdlet Exit-applet ccupdate pour démarrer les services et quitter le mode maintenance. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problème : vous recevez le message d’erreur suivant dans le journal du service de gestion de Cloud Connector, « C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log » : CceService Error : 0 : exception inattendue lors de la création de rapports sur en ligne : System. Management. Automation. CmdletInvocationException : échec de l’ouverture de session pour l’utilisateur \<Global Tenant Admin\> . Créez un objet d’informations d’identification, en vous assurant que vous avez utilisé le nom d’utilisateur et le mot de passe corrects. ---\>**
    
    **Résolution :** Les informations d’identification d’administrateur client global Microsoft 365 ou Office 365 ont été modifiées depuis l’inscription de l’appliance Cloud Connector. Pour mettre à jour les informations d’identification stockées localement sur le matériel de Cloud Connector, exécutez la commande suivante à partir d’administration PowerShell sur l’appliance hôte :
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problème : une fois que vous avez modifié le mot de passe pour le compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : Key non valide pour une utilisation dans l’état spécifié. » dans%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de la cmdlet Get-applet cccredential.**
    
    **Résolution :** Toutes les informations d’identification Cloud Connector sont stockées dans le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML». Lorsque le mot de passe sur le serveur hôte est modifié, vous devez mettre à jour les informations d’identification stockées localement.
    
    **Si vous exécutez la version 1.4.2 de Cloud Connector,** regénérez tous les mots de passe Cloud Connector en procédant comme suit :
    
  1. Redémarrez le serveur hôte.
    
  2. Supprimez le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML».
    
  3. Lancez une console PowerShell en tant qu’administrateur, puis exécutez la commande « Register-applet ccappliance-local » pour entrer de nouveau les mots de passe à la suite de la description. Entrez les mêmes mots de passe que ceux que vous avez entrés pour le déploiement de Cloud Connector.
    
     **Si vous exécutez la version 2,0 de Cloud Connector ou une version ultérieure,** regénérez tous les mots de passe Cloud Connector en procédant comme suit :
    
  4. Redémarrez le serveur hôte.
    
  5. Supprimez le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML».
    
  6. Lancez une console PowerShell en tant qu’administrateur, puis exécutez la commande « Register-applet ccappliance-local » pour entrer de nouveau les mots de passe à la suite de la description. 
    
     Si le fichier de mot de passe mis en cache a été généré avec la version 1.4.2 de Cloud Connector, utilisez le mot de passe VMAdmin pour le mot de passe CceService lorsque vous y êtes invité. Entrez le mot de passe que vous avez entré avant le déploiement de Cloud Connector pour tous les autres comptes.
    
     Si le fichier de mot de passe mis en cache a été généré avec Cloud Connector version 1.4.2 et que les mots de passe DomainAdmin et VMAdmin sont différents, vous devez effectuer les étapes suivantes :
    
  7. Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :
    
  8. Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
  9. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé précédemment.
    
     Si le fichier de mot de passe mis en cache a été généré avec la version 2,0 ou ultérieure de Cloud Connector, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les étapes suivantes :
    
  10. Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :
    
       1. Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService
    
       2. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé précédemment.
    
  11. Exécutez Set-applet cccredential-AccountType VmAdmin comme suit :
    
       1. Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService
    
       2. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin que vous avez utilisé précédemment. 
    
- **Problème : avec Cloud Connector version 2,1 et versions ultérieures, lors de l’exécution de la commande Register-applet ccappliance ou d’autres cmdlets sur l’appliance, vous recevez un message d’erreur de type : « for each-Object : la propriété «Common » est introuvable sur cet objet. Vérifiez que la propriété existe. Sur C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char : 14 "**
    
    **Résolution :** Cloud Connector 2,1 et versions ultérieures nécessite .NET Framework 4.6.1 ou version ultérieure. Mettez à jour .NET Framework sur l’appliance vers la version 4.6.1 ou ultérieure et réexécutez l’applet de commande.

- **Problème : avec la version Cloud Connector 2,1, lors de l’exécution de install-applet ccappliance, vous recevez un message d’erreur tel que : « échec de l’installation de la nouvelle instance avec l’erreur : impossible de définir «état » car seules les chaînes peuvent être utilisées comme valeurs pour définir les propriétés XmlNode»**

   **Résolution :** Dans Cloudconnector.ini, dans la section [Common], ajoutez le fichier « State » config comme suit : CountryCode = USA state = WA City = Redmond

   Il n’est pas obligatoire que la ligne « État » ait la valeur, mais la ligne « État » ne peut pas être supprimée du fichier Cloudconnector.ini.

- **Problème : vous recevez le message d’erreur suivant : «Dismount-WindowsImage : Dismount-WindowsImage a échoué. Code d’erreur = 0xc1550115 "lors de l’installation ou de la mise à niveau de la version Cloud Connector.**
    
    **Résolution :** Lancez une console PowerShell en tant qu’administrateur, exécutez « DISM-Cleanup-Wim ». Cette opération nettoie toutes les images ayant rencontré un problème. Exécutez à nouveau install-applet ccappliance ou attendez que la mise à niveau de bits soit automatique.
    
- **Problème : le déploiement de la première Appliance Cloud Connector dans un environnement haute disponibilité échoue.**
    
    **Résolution :** Les étapes que vous effectuez dépendent de la raison pour laquelle le déploiement a échoué :
    
  - Si la première Appliance Cloud Connector échoue et que vous ne parvenez pas à déterminer la raison de l’échec, vous devez réinstaller l’appliance jusqu’à ce que le déploiement réussisse, puis installer les autres appliances.
    
  - Si la première Appliance Cloud Connector échoue avec un problème mineur, tel qu’un problème de certificat externe, vous pourrez peut-être résoudre le problème sans réinstaller l’appliance. Vous pouvez ensuite utiliser PowerShell à distance du client pour marquer le déploiement comme étant réussi, comme suit. (Vous pouvez également utiliser les étapes suivantes si le premier déploiement a réussi, mais, pour une raison quelconque, Cloud Connector ne parvient pas à signaler le déploiement en tant que réussite.)
    
  - Pour obtenir l’identité (GUID) de la première Appliance Cloud Connector, exécutez la cmdlet Get-CsHybridPSTNAppliance.
    
  - Pour marquer l’appliance comme ayant été déployée avec succès, exécutez la CsCceApplianceDeploymentStatus comme suit :
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problème : vous devez vérifier et installer les mises à jour de Windows manuellement sur le serveur hôte ou les machines virtuelles.**
    
   **Résolution :** Nous vous recommandons de tirer parti des mises à jour automatisées du système d’exploitation fournies par Skype entreprise, version Cloud Connector. Une fois qu’une appliance est inscrite pour la gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifieront et installeront automatiquement les mises à jour de Windows conformément aux paramètres de la fenêtre de mise à jour du système d’exploitation
    
   Si vous devez vérifier et installer les mises à jour de Windows manuellement, suivez les étapes de cette section qui s’appliquent à votre type de déploiement. Vous devez planifier la mise à jour simultanée du serveur hôte et des machines virtuelles qu’il exécute, afin de minimiser le temps nécessaire pour les mises à jour.
    
   Si vous préférez, vous pouvez utiliser un serveur Windows Server Update Services (WSUS) pour fournir des mises à jour aux serveurs Cloud Connector. N’oubliez pas de configurer la mise à jour Windows pour qu’elle **ne soit pas** installée automatiquement.
    
   Pour plus d’informations sur la mise à jour manuelle de votre déploiement de Cloud Connector, reportez-vous à la section suivante.
    
- **Problème : lorsque Cloud Connector est mis à jour vers une nouvelle version, les cmdlets de Cloud Connector ne sont pas mises à jour.** Cela se produit parfois si une fenêtre PowerShell est laissée ouverte lorsque des mises à jour automatiques se produisent.
    
  **Résolution :** Pour charger les applets de commande mises à jour, vous pouvez effectuer l’une des opérations suivantes :
    
   - Fermez PowerShell sur le matériel Cloud Connector, puis rouvrez PowerShell.
    
     - Sinon, vous pouvez exécuter import-module CloudConnector-force. 
 
-   **Problème : « le terme «Stop-CsWindowsService » n’est pas reconnu comme le nom d’une cmdlet, d’une fonction, d’un fichier de script ou d’un programme exécutable». erreur lors de la tentative d’exécution de la cmdlet Enter-applet ccupdate.**

    **Résolution :** Supprimez le $HOME fichier \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crée ce fichier sous la forme d’un cache d’applets de commande à partir de modules qu’il trouve afin qu’il n’ait pas à analyser à chaque fois tous les modules, car cela entraînerait un ralentissement des opérations. Il y a probablement eu une altération des fichiers qui fournissait des résultats trompeurs lors de la lecture de ce cache.

-   **Problème : "import-module CloudConnector" génère une erreur "Import-Module : le module spécifié" CloudConnector "n’a pas été chargé, car aucun fichier de module valide n’a été trouvé dans un répertoire de module"**

    **Résolution :**
    - Vérifiez que le module CloudConnector existe effectivement sous c:\Program Files\WindowsPowerShell\Modules
    
    - Après avoir validé que le module CloudConnector existe sous cet emplacement, la variable d’environnement PSModulePath stockant le chemin d’accès aux emplacements des modules peut être modifiée :
    
     a. Modification temporaire : démarrez PowerShell en tant qu’administrateur et exécutez la commande suivante : $env :P SModulePath = $env :P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Pour les modifications permanentes, démarrez PowerShell en tant qu’administrateur et exécutez les commandes suivantes, une par une : $CurrentValue = [Environment] :: GetEnvironmentVariable ("PSModulePath", "machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," machine ")

    
## <a name="install-windows-updates-manually"></a>Installer les mises à jour de Windows manuellement

Si vous ne souhaitez pas utiliser les mises à jour automatiques dans votre environnement, procédez comme suit pour vérifier et appliquer manuellement les mises à jour de Windows. La vérification et l’installation des mises à jour Windows peuvent nécessiter un redémarrage du serveur. Lorsqu’un serveur hôte redémarre, les utilisateurs ne peuvent pas utiliser Cloud Connector pour passer ou recevoir des appels. Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler le moment où les mises à jour ont lieu, puis redémarrer les ordinateurs selon vos besoins pendant les périodes où vous choisissez d’éviter toute interruption des services.
  
Pour vérifier manuellement les mises à jour, connectez-vous à chaque serveur hôte et ouvrez le **panneau de configuration**. Sélectionnez **système et sécurité \> Windows Update**, puis gérez les mises à jour et les redémarrages du serveur en fonction de votre environnement.
  
- S’il n’y a qu’une seule Appliance dans le site, connectez-vous à chaque machine virtuelle et ouvrez le **panneau de configuration**. Sélectionnez **système et sécurité \> Windows Update**, puis configurez les mises à jour et les redémarrages du serveur, le cas échéant.
    
- S’il y a plusieurs Appliances dans le site, l’instance en cours de mise à jour et de redémarrage n’est pas accessible par les utilisateurs pendant les mises à jour. Les utilisateurs se connecteront à d’autres instances dans le déploiement jusqu’à ce que toutes les machines virtuelles et tous les services Skype entreprise démarrent sur les machines virtuelles une fois les mises à jour terminées. Pour éviter toute interruption potentielle du service, vous pouvez supprimer l’instance de la haute disponibilité lors de l’application des mises à jour, puis la restaurer lorsque vous avez terminé. Pour ce faire, procédez comme suit :
    
1. Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.
    
2. Supprimez l’instance de la haute disponibilité à l’aide de l’applet de commande suivante :
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Suivez les étapes d’une instance unique pour appliquer manuellement les mises à jour et redémarrer l’ordinateur virtuel.
    
4. Redéfinissez l’instance sur HA avec l’applet de commande suivante :
    
   ```powershell
   Exit-CcUpdate
   ```

Pour les déploiements multisites, suivez les étapes d’un site unique pour chaque site du déploiement, en appliquant les mises à jour à un site à la fois.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Conseils lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte de Cloud Connector

Si vous devez installer un logiciel antivirus sur l’ordinateur hôte de Cloud Connector, vous devez ajouter les exclusions suivantes :
  
- Répertoire d’appliance local sur chaque ordinateur.
    
- Annuaire de sites distants sur chaque ordinateur.
    
- L’annuaire de sites local sur l’ordinateur héberge le dossier racine du site partagé.
    
- %ProgramFiles%\Skype pour Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Le processus Microsoft.Rtc.CCE.ManagementService.exe.
