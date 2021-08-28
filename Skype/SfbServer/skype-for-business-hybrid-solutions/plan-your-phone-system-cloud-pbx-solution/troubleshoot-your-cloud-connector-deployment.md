---
title: Résolution des problèmes liés à votre déploiement de Cloud Connector
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Résolution des problèmes de déploiement de la version Cloud Connector.
ms.openlocfilehash: 95a3a89e4ae593ffa972f7b5de3891ee94aaeff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623402"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Résolution des problèmes liés à votre déploiement de Cloud Connector

> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)
 
Résolution des problèmes de déploiement de la version Cloud Connector.
  
Cette rubrique décrit les solutions aux problèmes courants avec les déploiements de la version Cloud Connector. Si vous rencontrez des problèmes avec les appels vers et depuis le réseau téléphonique commuté (PSTN), vous pouvez examiner les solutions décrites dans cette rubrique.
  
Cloud Connector fournit des mécanismes intégrés pour résoudre automatiquement certains problèmes. Un processus de détection automatique recherche les problèmes potentiels avec les appliances Cloud Connector et, si possible, prend des mesures correctives pour résoudre ces problèmes sans intervention de l’administrateur. Le processus de détection fonctionne comme suit :
  
- **Séquence de détection :** Le service de gestion Cloud Connector exécute un processus toutes les 60 secondes pour détecter si une appliance est en panne. Dans Cloud Connector version 2.0 et versions ultérieures, le processus de détection utilise le commutateur Skype Entreprise Corpnet pour établir des connexions PowerShell aux ordinateurs Cloud Connector ; Pour les versions antérieures à la version 2.0, le processus de détection utilise le commutateur de gestion Cloud Connector.
    
    > [!NOTE]
    > Pour que la récupération automatique réussisse, il doit y avoir une connectivité réseau entre l’hôte et les machines virtuelles sur le commutateur réseau hôte. Veillez à vérifier la connectivité réseau pour vous assurer que la détection et la récupération automatiques peuvent réussir. 
  
- **Surveillance :** Les services suivants sont surveillés dans Cloud Connector version 2.0 et ultérieures :
    
  - Les machines virtuelles ne sont pas connectées aux commutateurs virtuels d’entreprise ou Internet Cloud Connector
    
  - Les machines virtuelles sont dans un état enregistré ou arrêté
    
  - Services serveur de gestion centralisée : REPLICA, MASTER
    
  - Services de serveur de médiation : REPLICA, RTCSRV et MEDSVC
    
  - Services de serveur Edge : REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Les règles de pare-feu entrant sont désactivées pour CS RTCSRV sur le serveur Edge, CS RTCMEDSRV sur le serveur de médiation
    
    Dans Cloud Connector version 1.4.2, seuls les services suivants sont surveillés :
    
  - Services de serveur de médiation : RTCSRV et MEDSVC
    
  - Service serveur Edge : RTCSRV
    
- **Processus de récupération :** Si des services surveillés sont arrêtés, une appliance est marquée et les services sont arrêtés et marqués manuellement jusqu’à ce que tous les problèmes soient résolus. Cela empêche le routage des appels vers une appliance qui peut entraîner des défaillances d’appel.
    
    Le service de gestion Cloud Connector va réessayer la récupération automatique comme suit:
    
  - L’intervalle de nouvelle tentative initial est toutes les dix secondes avec une durée d’intervalle maximale d’une heure.
    
  - Pour les trois premières tentatives de récupération, l’intervalle est de 10 secondes. À partir de la quatrième tentative, l’intervalle augmente de deux fois l’intervalle précédent. Par exemple, la quatrième nouvelle tentative aura lieu dans 20 secondes, la cinquième en 40 secondes, etc. 
    
  - Lorsque l’intervalle maximal d’une heure est atteint, les tentatives se poursuivent une fois par heure.
    
  - Lorsque la récupération réussit, le nombre d’intervalles et de tentatives est fixé à leurs valeurs initiales.
    
  - Si le service de gestion est redémarré, le nombre d’intervalles et de tentatives est réinitialisé à leurs valeurs initiales.
    
## <a name="troubleshooting"></a>Résolution des problèmes

Voici des solutions aux problèmes couramment rencontrés :
  
- **Problème : le déploiement échoue ou cesse de répondre lors de l’exécution des scripts de déploiement. Après la connexion à chaque VM, l’adresse IP est manquante ou incorrecte pour la NIC gestion/interne/externe.**
    
    **Résolution :** Ce problème ne peut pas être résolu automatiquement. Les CCI ne peuvent pas être ajoutées aux ordinateurs VM pendant leur exécution. Veuillez arrêter et supprimer ces VM dans le gestionnaire hyper-v, puis exécutez les cmdlets suivantes :
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problème : une fois le serveur Active Directory et la forêt installés, le serveur CMS et/ou le serveur de médiation n’ont pas correctement rejoint le domaine.**
    
    **Résolution :** Pour résoudre ce problème, prenez les mesures suivantes :
    
  - Connectez-vous au serveur Active Directory et vérifiez que le domaine a été créé correctement.
    
  - Connectez-vous au serveur CMS/de médiation et vérifiez qu’une adresse IP valide est attribuée à la carte réseau du réseau d’entreprise et que l’adresse IP statique et le DNS valides sont configurés en tant qu’adresse IP du serveur AD.
    
  - Connectez-vous au serveur CMS/de médiation et ouvrez une invite de commandes. Assurez-vous que vous pouvez effectuer un test ping sur le nom deqdn et l’adresse IP du serveur Active Directory. Si vous ne le pouvez pas, il peut y avoir un conflit d’adresses IP. Essayez d’affecter une nouvelle adresse IP pour Active Directory et mettez à jour le DNS sur le serveur CMS/médiation en conséquence.
    
- **Problème : vous recevez le message d’erreur suivant, « Remove-VMSwitch : Échec lors de la suppression du commutateur Ethernet virtuel. Le commutateur virtuel « Cloud Connector Management Switch » ne peut pas être supprimé, car il est utilisé par des machines virtuelles ou affecté à des pools enfants. »**
    
    **Résolution :** Le « commutateur de gestion Cloud Connector » n’a pas été supprimé après le déploiement. Si vous avez atteint cette erreur, consultez le gestionnaire Hyper-v et vérifiez qu’aucune machine virtuelle ne s’y connecte encore. Si des machines virtuelles sont toujours connectées, déconnectez-les et supprimez le commutateur de gestion. Si le commutateur de gestion ne peut toujours pas être supprimé, redémarrez le serveur hôte et réessayez.
    
- **Problème : vous recevez le message d’erreur suivant, « Le démarrage du service RTCMRAUTH a échoué. Vérifiez que le service n’est pas désactivé. »**
    
    > [!NOTE]
    > Ce problème s’applique uniquement aux versions cloud connector antérieures à la version 1.4.2. 
  
    L’échec du démarrage peut également être dû au fait que ce serveur frontal a été précédemment échoué (à l’aide d’un ordinateur qui a échoué). Si c’est le cas, veuillez appeler la panne (à l’aide de la panne de l’ordinateur).
    
    **Résolution :** Ce problème se produit sur un serveur Edge lorsque le certificat d’ac racine ou le certificat d’ac intermédiaire n’est pas approuvé par le serveur Edge. Même si le certificat externe peut être importé mais que la chaîne de certificats est rompue. Dans cette condition, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.
    
    Importez manuellement le certificat d’ac racine et tous les certificats d’ac intermédiaire de votre certificat externe dans le serveur Edge, puis redémarrez le serveur Edge. Une fois que les services RTCMRAUTH et RTCSRV ont démarré sur le serveur Edge, revenir à votre serveur hôte, lancez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante pour basculer vers le nouveau déploiement :
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problème : le serveur hôte a été redémarré lors Windows mises à jour ont été appliquées, et les appels mis en service par le serveur échouent.**
    
    **Résolution :** Si vous avez déployé un environnement de haute disponibilité, Microsoft fournit une cmdlet pour vous aider à déplacer un ordinateur hôte (instance de déploiement) vers ou hors de la topologie actuelle lorsque vous vérifiez et installez Windows mise à jour manuellement. Pour ce faire, utilisez les étapes suivantes :
    
1. Sur le serveur hôte, démarrez une console PowerShell en tant qu’administrateur, puis exécutez :
    
   ```powershell
   Enter-CcUpdate
   ```

2. Recherchez les mises à jour et installez les mises à jour disponibles.
    
3. Dans la console PowerShell, exécutez l’cmdlet suivante :
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problème : lorsqu’un appel est effectué à partir d’un client Skype Entreprise à l’aide d’un numéro PSTN, l’appel ne peut pas être recalcalé à une conférence en invitant un autre numéro PSTN.**
    
    **Résolution :** Pour résoudre ce problème, voir Configurer le serveur de médiation [hybride en ligne Paramètres](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problème : un message d’avertissement s’affiche à propos Windows mise à jour lorsque vous installez le serveur Active Directory : « la mise à jour Windows automatique n’est pas activée. Pour vous assurer que votre rôle ou fonctionnalité nouvellement installé est automatiquement mis à jour, Windows mise à jour. »**
    
    **Résolution :** Lancez une session PowerShell client distante à l’aide des informations d’identification d’administrateur client Skype Entreprise, puis exécutez l’cmdlet suivante pour vérifier la configuration _EnableAutoUpdate_ de votre site :
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Si _EnableAutoUpdate_ est définie sur **True,** vous pouvez ignorer ce message d’avertissement en toute sécurité, car le service CCEManagement gère le téléchargement et l’installation des mises à jour Windows pour les machines virtuelles et le serveur hôte. Si  _EnableAutoUpdate_ est définie sur **False,** exécutez l’cmdlet suivante pour la définir sur **True**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Vous pouvez également vérifier et installer manuellement les mises à jour. Voir la section suivante.
    
- **Problème : vous recevez un message d’erreur : impossible d’inscrire l’appliance en raison de votre entrée/configuration actuelle ou ou en conflit avec des \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> appliances existantes. Supprimez l’appliance conflictuelle ou mettez à jour vos informations d’entrée/configuration, puis inscrivez-vous à nouveau. ' when run Register-CcAppliance to register current appliance to online.**
    
    **Résolution :** Valeurs pour le , et doit être unique et utilisé \<ApplianceName\> \<Mediation Server FQDN\> uniquement pour \<Mediation Server IP Address\> l’inscription d’une appliance. Par défaut, \<ApplianceName\> provient du nom d’hôte. \<Mediation Server FQDN\> et \<Mediation Server IP Address\> défini dans le fichier ini de configuration.
    
    Par exemple, à l’aide de (ApplianceName= MyserverNew, FQDN du serveur de médiation=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.
    
    Tout d’abord, vérifiez votre CloudConnector.ini dans la section Répertoire ApplianceRoot. Vous obtenez \<SiteName\> et \<Mediation Server FQDN\> les \<Mediation Server IP Address\> valeurs dans le fichier. \<ApplianceName\> est le nom de votre serveur hôte.
    
    Ensuite, lancez Tenant Remote PowerShell à l’aide de vos informations d’identification d’administrateur client Skype Entreprise, puis exécutez l’cmdlet suivante pour vérifier la ou les appliance(s) inscrite(s).
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Après avoir identifié les conflits, vous pouvez mettre à jour votre fichier CloudConnector.ini avec les informations qui correspond à l’appliance inscrite, ou désinsister l’appliance existante pour résoudre les conflits.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problème : la cmdlet Get-CcRunningVersion renvoie une valeur vide si une appliance déployée est en cours d’exécution sur l’hôte.**
    
  **Résolution :** Cela peut se produire lorsque vous faites une mise à niveau de la version 1.3.4 ou 1.3.8 vers la version 1.4.1. Après avoir installé la version 1.4.1 avec le .msi, vous devez l’exécuter avant d’exécuter une `Register-CcAppliance` autre cmdlet. `Register-CcAppliance` migrera le module.ini de %UserProfile%\CloudConnector vers %ProgramData%\CloudConnector. Si vous l’avez manqué, une nouvelle module.ini sera créée dans le dossier %ProgramData%\CloudConnector et remplacera les informations de version d’exécution/sauvegarde pour la version 1.3.4 ou 1.3.8.
    
  Comparez module.ini fichiers dans le dossier %UserProfile%\CloudConnector et %ProgramData%\CloudConnector. S’il existe des différences, supprimez le module.ini dans %ProgramData%\CloudConnector et  `Register-CcAppliance` réexécutez. Vous pouvez également modifier le fichier manuellement pour qu’il soit correctement en cours d’exécution et en version de sauvegarde.
    
- **Problème : après avoir exécuté l'Switch-CcVersion cmdlet pour basculer vers une ancienne version différente de la version actuelle du script, il n’existe aucune prise en charge de la haute disponibilité pour cette ancienne version.**
    
    **Résolution :** Par exemple, vous avez mis à niveau la version 1.4.1 vers la version 1.4.2. Votre version de script actuelle, qui peut être déterminée par l’exécution, et votre version en cours d’exécution, qui peut être déterminée par l’exécution sont les deux `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2. Pour l’instant, si vous exécutez pour revenir à la version en cours d’exécution vers la version 1.4.1, il n’y aura pas de prise en charge de la haute disponibilité pour cette `Switch-CcVersion` ancienne version.
    
    Pour obtenir une prise en charge complète de la haute disponibilité, revenir à la version 1.4.2, afin que la version en cours d’exécution et la version de script soient identiques. Si vous rencontrez des problèmes avec votre déploiement 1.4.2, désinstallez-le et réinstallez-le dès que possible.
    
- **Problème : les certificats d’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**
    
    **Solution : Skype Entreprise** certificats de l’autorité de certification sont valides pendant cinq ans. Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides pendant deux ans.
    
    > [!NOTE]
    > Dans Cloud Connector version 2.0 et versions ultérieures, l’cmdlet Renew-CcServerCertificate est devenu Update-CcServerCertificate et la cmdlet Renew-CcCACertificate a été changée en Update-CcCACertificate. 
  
    Si les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis, exécutez la cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate pour renouveler vos certificats.
    
    Si les certificats d’autorité de certification sont sur le point d’expirer, exécutez la cmdlet Renew-CcCACertificate ou Update-CcCACertificate pour renouveler vos certificats.
    
    **Si les certificats de l’autorité** de certification sont compromis et qu’il n’existe qu’une seule appliance dans le site, effectuez les étapes suivantes :
    
1. Exécutez lEnter-CcUpdate cmdlet pour vider les services et mettre l’appliance en mode maintenance.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Exécutez les cmdlets suivantes pour réinitialiser et créer de nouveaux certificats d’autorité de certification et tous les certificats serveur internes :
    
    Pour les publication de Cloud Connector avant la version 2.0 :
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou pour cloud connector version 2.0 et ultérieure :
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez la cmdlet Export-CcRootCertificate à partir de l’appliance, puis installez le certificat exporté sur vos passerelles PSTN. Vous pouvez également être tenu de ré-émettre le certificat sur votre passerelle.

   ```powershell
   Export-CcRootCertificate
   ```

4. Exécutez l'Exit-CcUpdate pour démarrer les services et quitter le mode maintenance.

   ```powershell
   Exit-CcUpdate
   ```


    **Si les certificats de** l’autorité de certification sont compromis et qu’il existe plusieurs appliances dans le site, effectuez les étapes séquentielles suivantes sur chaque appliance du site.
    
    Microsoft vous recommande d’effectuer ces étapes pendant les périodes d’utilisation normales.
    
1. Sur la première appliance, exécutez la cmdlet Remove-CcCertificationAuthorityFile pour nettoyer les fichiers de sauvegarde de l’autorité de contrôle d’accès dans \<SiteRoot\> l’annuaire.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Exécutez l'Enter-CcUpdate pour vider les services et mettre chaque appliance en mode maintenance.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Sur la première appliance, exécutez les cmdlets suivantes pour réinitialiser et créer de nouveaux certificats d’autorité de certification et tous les certificats serveur internes :
    
     Pour les publication de Cloud Connector avant la version 2.0 :
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou pour cloud connector version 2.0 et ultérieure :
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. Sur la première appliance, exécutez l’cmdlet suivante pour back up the CA files to the \<SiteRoot\> folder.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Sur toutes les autres appliances du même site, exécutez les commandes suivantes pour consommer les fichiers de sauvegarde de l’ac, afin que les appliances utilisent toutes le même certificat racine, puis demandent de nouveaux certificats. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez la cmdlet Export-CcRootCertificate à partir de n’importe quelle appliance du site, puis installez le certificat exporté sur vos passerelles PSTN. Vous pouvez également être tenu de ré-émettre le certificat sur votre passerelle.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Exécutez l'Exit-CcUpdate pour démarrer les services et quitter le mode maintenance. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problème : vous recevez le message d’erreur suivant dans le journal du service de gestion Cloud Connector, « C:\Program Files\Skype Entreprise Cloud Connector Edition\ManagementService\CceManagementService.log » : Erreur CceService : 0 : Exception inattendue lors du signalement de l’état en ligne : System.Management.Automation.CmdletInvocationException : Échec de connexion pour \<Global Tenant Admin\> l’utilisateur. Veuillez créer un objet d’informations d’identification, en vous assurez que vous avez utilisé le nom d’utilisateur et le mot de passe corrects. ---\>**
    
    **Résolution :** Les informations Microsoft 365 ou Office 365 d’administrateur client global ont été modifiées depuis l’inscription de l’appliance Cloud Connector. Pour mettre à jour les informations d’identification stockées localement sur l’appliance Cloud Connector, exécutez ce qui suit à partir de l’administrateur PowerShell sur l’appliance hôte :
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problème : après avoir changé le mot de passe du compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : clé non valide pour une utilisation dans l’état spécifié . » dans %ProgramFiles%\Skype Entreprise Cloud Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de l’cmdlet Get-CcCredential.**
    
    **Résolution :** Toutes les informations d’identification Cloud Connector sont stockées dans le fichier suivant : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ». Lorsque le mot de passe du serveur hôte change, vous devez mettre à jour les informations d’identification stockées localement.
    
    **Si vous exécutez Cloud Connector version 1.4.2,** régénérez tous les mots de passe Cloud Connector en suivant les étapes suivantes :
    
  1. Redémarrez le serveur hôte.
    
  2. Supprimez le fichier suivant : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».
    
  3. Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance -Local » pour entrer à nouveau les mots de passe suivant la description. Entrez les mêmes mots de passe que vous avez entrés auparavant pour le déploiement Cloud Connector.
    
     **Si vous exécutez Cloud Connector version 2.0** ou ultérieure, régénérez tous les mots de passe Cloud Connector en suivant les étapes suivantes :
    
  4. Redémarrez le serveur hôte.
    
  5. Supprimez le fichier suivant : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml " .
    
  6. Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance -Local » pour entrer à nouveau les mots de passe suivant la description. 
    
     Si le fichier de mot de passe mis en cache a été généré avec Cloud Connector version 1.4.2, utilisez le mot de passe VMAdmin pour le mot de passe CceService lorsque vous y êtes invité. Entrez le mot de passe que vous avez entré auparavant pour le déploiement Cloud Connector pour tous les autres comptes.
    
     Si le fichier de mot de passe mis en cache a été généré avec Cloud Connector version 1.4.2 et que les mots de passe DomainAdmin et VMAdmin sont différents, vous devez effectuer les étapes suivantes :
    
  7. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
  8. Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
  9. Lorsque vous êtes invité à entrer les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé auparavant.
    
     Si le fichier de mot de passe mis en cache a été généré avec Cloud Connector version 2.0 ou ultérieure, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les étapes suivantes :
    
  10. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
       1. Lorsque vous êtes invité à entrer l’ancienne identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService
    
       2. Lorsque vous êtes invité à entrer les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé auparavant.
    
  11. Exécutez Set-CcCredential -AccountType VmAdmin comme suit :
    
       1. Lorsque vous êtes invité à entrer l’ancienne identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService
    
       2. Lorsque vous êtes invité à entrer les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe VmAdmin que vous avez utilisé auparavant. 
    
- **Problème : avec Cloud Connector version 2.1 et versions ultérieures, lors de l’exécution de Register-CcAppliance ou d’autres cmdlets sur l’appliance, vous recevez un message d’erreur tel que : « Pour Each-Object : la propriété « Common » est in trouvée sur cet objet. Vérifiez que la propriété existe. À C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14 »**
    
    **Résolution :** Cloud Connector 2.1 et les ultérieures nécessitent .NET Framework 4.6.1 ou ultérieure. Veuillez mettre .NET Framework jour sur l’appliance vers la version 4.6.1 ou ultérieure et ré-exécuter la ou les cmdlet.

- **Problème : avec Cloud Connector Edition 2.1, lorsque vous exécutez Install-CcAppliance, vous recevez un message d’erreur tel que : « Échec de l’installation d’une nouvelle instance avec erreur : impossible de définir « State », car seules les chaînes peuvent être utilisées comme valeurs pour définir les propriétés XmlNode »**

   **Résolution :** In Cloudconnector.ini, under the [Common] section, please add the « State » config as below: CountryCode=US State=WA City=Redmond

   Il n’est pas obligatoire que la ligne « State » soit une valeur, mais la ligne « State » ne peut pas être supprimée du fichier Cloudconnector.ini'état.

- **Problème : vous recevez le message d’erreur suivant « Démon-WindowsImage : Dismount-WindowsImage échoué. Code d’erreur = 0xc1550115 » lors de l’installation ou de la mise à niveau de l’édition Cloud Connector.**
    
    **Résolution :** Lancez une console PowerShell en tant qu’administrateur, exécutez « DISM -Cleanup-Wim ». Cette opération nettoie toutes les images en difficulté. Exécutez Install-CcAppliance à nouveau ou attendez la mise à niveau automatique des bits.
    
- **Problème : échec du déploiement de la première appliance Cloud Connector dans un environnement de haute haute sécurité**
    
    **Résolution :** Les étapes à suivre dépendent de la raison de l’échec du déploiement :
    
  - Si la première appliance Cloud Connector échoue et que vous ne pouvez pas déterminer la raison de la défaillance, vous devez réinstaller l’appliance jusqu’à ce que le déploiement réussisse, puis installer les autres appliances.
    
  - Si la première appliance Cloud Connector échoue avec un problème mineur, tel qu’un problème de certificat externe, vous pourrez peut-être résoudre le problème sans réinstaller l’appliance. Vous pouvez ensuite utiliser l’powerShell distant client pour marquer le déploiement comme réussi comme suit. (Vous pouvez également suivre les étapes suivantes si le premier déploiement a réussi, mais, pour une raison quelconque, Cloud Connector ne parvient pas à signaler le déploiement comme un succès.)
    
  - Pour obtenir l’identité (GUID) de la première appliance Cloud Connector, exécutez Get-CsHybridPSTNAppliance cmdlet.
    
  - Pour marquer l’appliance comme correctement déployée, exécutez le Set-CsCceApplianceDeploymentStatus comme suit :
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problème : vous devez vérifier et installer les mises à jour Windows manuellement sur le serveur hôte ou les machines virtuelles.**
    
   **Résolution :** Nous vous recommandons de tirer parti des mises à jour automatisées du système d’exploitation fournies par Skype Entreprise Cloud Connector Edition. Une fois qu’une appliance est inscrite pour la gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifient et installent les mises à jour Windows automatiquement en fonction des paramètres de la fenêtre de temps de mise à jour du système d’exploitation.
    
   Si vous devez vérifier et installer manuellement Windows mises à jour, suivez les étapes de cette section qui s’appliquent à votre type de déploiement. Vous devez planifier la mise à jour du serveur hôte et des ordinateurs virtuels qui s’exécutent sur celui-ci en même temps afin de réduire le temps d’in panne nécessaire pour les mises à jour.
    
   Si vous préférez, vous pouvez utiliser un serveur Windows Server Update Services (WSUS) pour fournir des mises à jour aux serveurs Cloud Connector. Assurez-vous simplement de configurer la mise à jour Windows pour **qu’elle ne s’installe** pas automatiquement.
    
   Pour plus d’informations sur la mise à jour manuelle de votre déploiement Cloud Connector, consultez la section suivante.
    
- **Problème : lorsque Cloud Connector est mis à jour vers une nouvelle build, les cmdlets Cloud Connector ne sont pas mises à jour.** Cela se produit parfois si une fenêtre PowerShell reste ouverte lorsque la mise à jour automatique se produit.
    
  **Résolution :** Pour charger les cmdlets mises à jour, vous pouvez suivre l’une des étapes suivantes :
    
   - Fermez PowerShell sur l’appliance Cloud Connector, puis rouvrez PowerShell.
    
     - Sinon, vous pouvez exécuter Import-Module CloudConnector -Force. 
 
-   **Problème : le terme « Stop-CsWindowsService » n’est pas reconnu comme nom d’une cmdlet, d’une fonction, d’un fichier de script ou d’un programme opérable. » erreur lors de la tentative d'Enter-CcUpdate cmdlet.**

    **Résolution :** Supprimez le $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell crée ce fichier en tant que cache d’cmdlets à partir de modules qu’il trouve afin qu’il n’a pas à analyser à nouveau tous les modules, car cela ralentit les choses. Il est fort probable qu’il y a eu une altération de fichier qui a fourni des résultats erronés à PowerShell lors de la lecture à partir de ce cache.

-   **Problème : « Import-Module CloudConnector » génère l’erreur « Import-Module : le module spécifié « CloudConnector » n’a pas été chargé car aucun fichier de module valide n’a été trouvé dans un répertoire de modules »**

    **Résolution :**
    - Vérifier que effectivement le module CloudConnector existe sous c:\Program Files\WindowsPowerShell\Modules
    
    - Après avoir validé que le module CloudConnector existe sous cet emplacement, la variable d’environnement PSModulePath stockant le chemin d’accès aux emplacements des modules peut être modifiée :
    
     a. Modification temporaire : démarrez Powershell en tant qu’administrateur et exécutez la commande suivante : $env:PSModulePath = $env:PSModulePath + « ; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Pour les changements persistants, démarrez PowerShell en tant qu’administrateur et exécutez les commandes suivantes, une par une : $CurrentValue = [Environment]::GetEnvironmentVariable(« PSModulePath », « Machine ») SetEnvironmentVariable(« PSModulePath », $CurrentValue + « ; C:\Program Files\WindowsPowerShell\Modules », « Machine »)

    
## <a name="install-windows-updates-manually"></a>Installer Windows mises à jour manuellement

Si vous ne souhaitez pas utiliser les mises à jour automatiques dans votre environnement, suivez ces étapes pour vérifier et appliquer manuellement Windows mises à jour. La recherche et l’installation Windows mises à jour peuvent nécessiter un redémarrage du serveur. Lorsqu’un serveur hôte redémarre, les utilisateurs ne peuvent pas utiliser Cloud Connector pour mettre en place ou recevoir des appels. Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler le moment où elles ont lieu, puis redémarrer les ordinateurs selon vos besoins pendant les heures de votre choix afin d’éviter toute perturbation des services.
  
Pour vérifier manuellement les mises à jour, connectez-vous à chaque serveur hôte et ouvrez le **Panneau de contrôle.** Sélectionnez **System and Security Windows \> Update,** puis gérez les mises à jour et les redémarrages du serveur selon les cas de votre environnement.
  
- S’il n’existe qu’une seule appliance dans le site, connectez-vous à chaque machine virtuelle et ouvrez le **Panneau de contrôle.** Sélectionnez **System and Security Windows \> Update,** puis configurez les mises à jour et les redémarrages du serveur, le cas échéant.
    
- S’il existe plusieurs équipements dans le site, l’instance mise à jour et redémarré n’est pas accessible aux utilisateurs pendant les mises à jour. Les utilisateurs se connectent à d’autres instances du déploiement jusqu’à ce que toutes les machines virtuelles et tous les services Skype Entreprise démarrent sur les ordinateurs virtuels une fois les mises à jour terminées. Pour éviter toute perturbation potentielle du service, vous pouvez supprimer l’instance de la ha pendant que vous appliquez les mises à jour, puis la restaurer une fois terminée. Pour ce faire, procédez comme suit :
    
1. Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.
    
2. Supprimez l’instance de la ha à l’aide de l’cmdlet suivante :
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Suivez les étapes d’une instance unique pour appliquer manuellement les mises à jour et redémarrer la machine virtuelle.
    
4. Définissez à nouveau l’instance sur HA avec l’cmdlet suivante :
    
   ```powershell
   Exit-CcUpdate
   ```

Pour les déploiements sur plusieurs sites, suivez les étapes d’un site unique pour chaque site du déploiement, en appliquant des mises à jour à un site à la fois.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Astuces lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte Cloud Connector

Si vous devez installer un logiciel antivirus sur l’ordinateur hôte Cloud Connector, vous devez ajouter les exclusions suivantes :
  
- Répertoire Local Appliance sur chaque ordinateur.
    
- Annuaire de sites distants sur chaque ordinateur.
    
- L’annuaire de sites local sur l’ordinateur héberge le dossier racine du site partagé.
    
- %ProgramFiles%\Skype Entreprise Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Le processus est Microsoft.Rtc.CCE.ManagementService.exe.