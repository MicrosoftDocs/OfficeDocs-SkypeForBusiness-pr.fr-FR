---
title: Identification et résolution des problèmes de votre déploiement Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Résoudre les problèmes de déploiement de votre édition Cloud Connector.
ms.openlocfilehash: 3edc67d5887c21543e4cbb01a6057a0c657e95e3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002074"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Identification et résolution des problèmes de votre déploiement Cloud Connector
 
Résoudre les problèmes de déploiement de votre édition Cloud Connector.
  
Cette rubrique vous décrit les solutions aux problèmes courants liés au déploiement de la version Cloud Connector. Si vous rencontrez des problèmes liés aux appels vers ou sur la Réseau Téléphonique Commuté (RTC), vous pouvez tenter de les résoudre en suivant les solutions décrites dans cette rubrique.
  
Le Cloud Connector fournit des mécanismes intégrés qui permettent de résoudre automatiquement certains problèmes. Un processus de détection automatique recherche les problèmes potentiels liés aux appareils Cloud Connector, et, dans la mesure du possible, effectue une action corrective pour résoudre ces problèmes sans nécessiter l’intervention de l’administrateur. Le processus de détection fonctionne comme suit :
  
- **Séquence de détection :** Le service de gestion des connecteurs Cloud exécute un processus toutes les 60 secondes pour détecter si une appliance est en panne. Dans Cloud Connector version 2,0 et les versions ultérieures, le processus de détection utilise le commutateur corpnet Skype entreprise pour effectuer des connexions PowerShell aux ordinateurs Cloud Connector. pour les versions antérieures à 2,0, le processus de détection utilise le commutateur de gestion Cloud Connector.
    
    > [!NOTE]
    > Pour que la récupération automatique puisse aboutir, la connectivité réseau doit être établie entre l’hôte et les machines virtuelles sur le commutateur du réseau hôte. Veillez à vérifier la connectivité réseau pour vous assurer que la détection automatique et la récupération peuvent aboutir. 
  
- **Surveiller :** Les services suivants sont surveillés dans Cloud Connector version 2,0 et les versions ultérieures :
    
  - Les machines virtuelles ne sont pas connectées aux commutateurs virtuels d’entreprise ou de connexion Internet dans le Cloud Connector
    
  - Les machines virtuelles sont dans un état enregistré ou arrêté
    
  - Services serveur de gestion centralisée : réplica, maître
    
  - Services du serveur de médiation : RÉPLICA, RTCSRV et MEDSVC
    
  - Services Edge Server : fac-similé, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Les règles de pare-feu entrant sont désactivées pour le RTCSRV sur le serveur Edge, RTCMEDSRV CS
    
    Dans Cloud Connector version 1.4.2, seuls les services suivants sont surveillés :
    
  - Services serveur de médiation : RTCSRV et MEDSVC
    
  - Service Edge Server : RTCSRV
    
- **Processus de récupération :** Si des services surveillés sont en panne, une application est marquée comme étant arrêtée et les services sont arrêtés et signalés manuellement jusqu’à ce que tous les problèmes puissent être résolus. Cela empêchera les appels de routage vers une appliance qui peut provoquer des échecs d’appel.
    
    Le service de gestion de connecteur Cloud réutilise la récupération automatique comme suit.
    
  - L’intervalle de nouvelle tentative initial est de dix secondes, avec un intervalle de temps maximal d’une heure.
    
  - Pour les trois premières tentatives de récupération, l’intervalle est de 10 secondes. À partir de la quatrième réessayer, l’intervalle de temps augmente de deux fois l’intervalle de temps précédent. Par exemple, la quatrième réessayer aura lieu dans 20 secondes, le cinquième dans 40 secondes, et ainsi de suite. 
    
  - Lorsque l’intervalle maximal d’une heure est atteint, les tentatives de connexion continuent une fois par heure.
    
  - Lorsque la restauration est réussie, l’intervalle et le nombre de tentatives sont définis sur leur valeur initiale.
    
  - Si le service de gestion est redémarré, l’intervalle et le nombre de tentatives sont réinitialisés à leur valeur initiale.
    
## <a name="troubleshooting"></a>Résolution des problèmes

Vous trouverez ci-après les solutions aux problèmes rencontrés fréquemment :
  
- **Problème : le déploiement échoue ou cesse de répondre pendant l’exécution des scripts de déploiement. Après s’être connectée sur chaque machine virtuelle, l’adresse IP est manquante ou incorrecte pour la NIC Externe/Interne/Gestion.**
    
    **Résolution :** Ce problème ne peut pas être résolu automatiquement. Les NIC ne peuvent pas être ajoutées aux machines virtuelles tant qu’elles sont en cours d’exécution. Veuillez éteindre et retirer ces machines virtuelles dans le gestionnaire hyper-v, puis exécuter l’applet de commande suivante :
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problème : après l’installation du serveur et de la forêt Active Directory, le serveur CMS et/ou le serveur de médiation ne rejoignent pas correctement le domaine.**
    
    **Résolution :** Pour résoudre ce problème, suivez les étapes suivantes :
    
  - Ouvrez une session sur le serveur Active Directory et vérifiez que le domaine a été correctement créé.
    
  - Connectez-vous au serveur CMS/de médiation et vérifiez qu’une adresse IP valide est affectée à la NIC du réseau interne, et qu'une adresse IP statique et le DNS sont configurés comme adresse IP du serveur AD.
    
  - Ouvrez une session sur le serveur CMS/médiation et ouvrez une invite de commandes. Vérifiez que vous pouvez exécuter une commande ping sur le FQDN et l’adresse IP du serveur Active Directory. Si ce n’est pas le cas, il peut y avoir un conflit d’adresses IP. Veuillez essayer d’affecter une nouvelle adresse IP pour Active Directory et de mettre à jour le DNS sur le serveur CMS/médiation en conséquence.
    
- **Problème : vous recevez le message d’erreur suivant : «Remove-VMSwitch : failed lors de la suppression du commutateur Virtual Ethernet. Le commutateur virtuel’commutateur de gestion des connecteurs Cloud’ne peut pas être supprimé car il est utilisé par des machines virtuelles ou affectées à des pools enfants. "**
    
    **Résolution :** Le « commutateur de gestion des connecteurs Cloud » n’a pas été supprimé après le déploiement. Si vous avez atteint ce message d’erreur, accédez au Gestionnaire Hyper-v et vérifiez qu’aucun ordinateur virtuel n’est encore connecté à celui-ci. Si des machines virtuelles sont toujours connectées, déconnectez-les et supprimez le commutateur de gestion. Si le commutateur de gestion ne peut pas être supprimé, redémarrez le serveur hôte, puis réessayez.
    
- **Problème : vous recevez le message d’erreur suivant : « impossible de démarrer le service RTCMRAUTH ». Vérifiez que le service n’est pas désactivé.»**
    
    > [!NOTE]
    > Ce problème ne s’applique qu’aux versions Cloud Connector antérieures à la version 1.4.2. 
  
    L’échec du démarrage peut aussi être dû au fait que le serveur frontal a basculé (en utilisant la bascule ordinateur). Si c’est le cas, veuillez appeler la restauration (en utilisant la restauration ordinateur).
    
    **Résolution :** Ce problème se produit sur un serveur Edge quand le certificat de l’AC racine ou le certificat de l’AC intermédiaire n’est pas approuvé par le serveur Edge, même si le certificat extérieur peut être importé mais que la chaîne de certificats est brisée. Dans ces conditions, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.
    
    Veuillez importer manuellement dans le serveur Edge le certificat de l’AC racine et tous les certificats d’AC intermédiaires de votre certificat externe, puis redémarrer le serveur Edge. Une fois que les services RTCMRAUTH et RTCSRV ont démarré sur le serveur Edge, retournez sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez l’applet de commande suivante pour basculer vers le nouveau déploiement :
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problème : le serveur hôte a redémarré à l’application des mises à jour de Windows, et les appels qu’il gérait échouent.**
    
    **Résolution :** Si vous avez déployé un environnement haute disponibilité, Microsoft fournit une cmdlet pour vous permettre de déplacer un ordinateur hôte (instance de déploiement) dans ou en dehors de la topologie actuelle lorsque vous vérifiez et installez manuellement Windows Update. Pour cela, veuillez suivre les étapes suivantes :
    
1. Sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez :
    
   ```powershell
   Enter-CcUpdate
   ```

2. Vérifiez la présence de mise à jour, et installez toutes celles qui sont disponibles.
    
3. Dans la console PowerShell, exécutez l’applet de commande suivante :
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problème : Quand un appel est placé en utilisant un numéro RTC depuis un client Skype Entreprise, l';appel ne peut pas être transformé en conférence en invitant un autre numéro RTC.**
    
    **Résolution :** Pour résoudre ce problème, voir [configurer les paramètres du serveur de médiation hybride en ligne](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problème : un avertissement à propos de Windows Update s’affiche quand vous installez le serveur Active Directory - « La mise à jour automatique de Windows n’est pas activée. Pour vous assurer que le rôle ou la fonctionnalité que vous venez d’installer est automatiquement mis à jour, activez Windows Update. »**
    
    **Résolution :** Lancez une session PowerShell distante du client à l’aide des informations d’identification d’administrateur de clients Skype entreprise, puis exécutez l’applet de commande suivante pour vérifier la configuration de _EnableAutoUpdate_ de votre site :
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Si l’argument _EnableAutoUpdate_ a la valeur **true**, vous pouvez ignorer ce message d’avertissement, car le service CCEManagement gère le téléchargement et l’installation des mises à jour Windows pour les machines virtuelles et le serveur hôte. Si l’argument _EnableAutoUpdate_ est défini sur **false**, exécutez l’applet de commande suivante pour lui attribuer la valeur **true**.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Une autre solution consiste à vérifier et installer les mises à jour manuellement. Consultez la rubrique suivante.
    
- **Problème : vous recevez un message d’erreur : il n’est pas possible d’enregistrer l' \<application\> , \<car\> votre \<nom de domaine\> complet \</de l’adresse\> de site Supprimez l’application Conflict ou mettez à jour vos informations d’entrée/configuration, puis inscrivez-vous à nouveau. 'lors de l’inscription de Register-CcAppliance pour inscrire l’application en ligne.**
    
    **Résolution :** Les valeurs de \<l'\>adresse \<\> IP du serveur\> de \<médiation et du nom de domaine complet du serveur de médiation ApplianceName doivent être uniques et réservées pour une seule inscription d’appliance. Par défaut, \<ApplianceName\> provient du nom d’hôte. \<Nom de domaine\> complet \<du serveur de médiation\> et adresse IP du serveur de médiation définie dans le fichier ini de configuration.
    
    Par exemple, utiliser (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) pour inscrire sur SiteName=MySite, mais s'il existe un appareil inscrit (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), un conflit se produira.
    
    Tout d’abord, vérifiez votre fichier CloudConnector.ini dans la rubrique répertoire ApplianceRoot. Vous obtiendrez \<SiteName\>, \<Mediation Server FQDN\> et \<les valeurs d’adresse\> IP du serveur de médiation dans le fichier. \<ApplianceName\> est le nom de votre serveur hôte.
    
    Deuxièmement, lancez l’application PowerShell distante avec les informations d’identification d’administrateur de votre client Skype entreprise, puis exécutez l’applet de commande suivante pour vérifier les matériels enregistrés.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Après avoir identifié les conflits, vous pouvez soit mettre à jour votre fichier CloudConnector.ini avec les informations correspondant à l’appliance inscrite, soit annuler l’inscription de « l’appliance » existant pour résoudre les conflits.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problème : l’applet de passe Get-CcRunningVersion renvoie une valeur vide si une application déployée est en cours d’exécution sur l’hôte.**
    
  **Résolution :** Cela peut se produire lorsque vous effectuez une mise à niveau de 1.3.4 ou de 1.3.8 vers 1.4.1. Après l’installation de la version 1.4.1 avec le fichier. msi, `Register-CcAppliance` vous devez l’exécuter avant d’exécuter une autre cmdlet. `Register-CcAppliance`va migrer le fichier module. ini de%UserProfile%\CloudConnector vers%ProgramData%\CloudConnector. Si vous l’avez manqué, un nouveau module .ini sera créé dans le dossier %ProgramData%\CloudConnector et remplacera les informations de la version exécutée ou de sauvegarde pour la version 1.3.4 ou la 1.3.8.
    
  Comparez les modules des fichier .ini dans les dossiers %UserProfile%\CloudConnector et %ProgramData%\CloudConnector. S’il existe des différences, supprimez le fichier module. ini dans%ProgramData%\CloudConnector `Register-CcAppliance`, puis réexécutez. Vous pouvez également modifier manuellement le fichier en fonction de la version correcte d’exécution et de sauvegarde.
    
- **Problème : après avoir exécuté l’applet de contrôle Switch-CcVersion pour basculer vers une ancienne version différente de la version de script actuelle, il n’y a pas de prise en charge de haute disponibilité pour cette ancienne version.**
    
    **Résolution :** Par exemple, vous avez effectué une mise à niveau de 1.4.1 vers 1.4.2. Votre version de script actuelle, qui peut être déterminée en `Get-CcVersion`cours d’exécution, ainsi que votre version en cours d’exécution `Get-CcRunningVersion` , qui peut être déterminée en exécution sont les deux 1.4.2. Pour le moment, si vous exécutez `Switch-CcVersion` pour basculer la version d’exécution vers 1.4.1, il n’y a pas de prise en charge de haute disponibilité pour cette ancienne version.
    
    Pour que la haute disponibilité soit entièrement prise en charge, veuillez rebasculer vers la version 1.4.2 afin que la version exécutée et celle du script soient les mêmes. Si vous rencontrez des problèmes avec votre déploiement 1.4.2, veuillez désinstaller et réinstaller dès que possible.
    
- **Problème : Les certificats de l’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**
    
    **Résolution :** Les certificats de l’autorité de certification de Skype Entreprise sont valides cinq ans. Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides deux ans.
    
    > [!NOTE]
    > Dans Cloud Connector version 2,0 et les versions ultérieures, l’applet de contrôle Renew-CcServerCertificate a été remplacée par Update-CcServerCertificate et l’applet de connexion Renew-CcCACertificate a changé pour Update-CcCACertificate. 
  
    Si les certificats internes émis au magasin de gestion central, au serveur de médiation et au serveur Edge sont proches de l’expiration ou de la compromission, exécutez l’applet de certification Renew-CcServerCertificate ou Update-CcServerCertificate pour renouveler vos certificats.
    
    Si les certificats d’autorité de certification sont proches de leur expiration, exécutez l’applet de nouvelle tentative de renouvellement-CcCACertificate ou de mise à jour-CcCACertificate pour renouveler vos certificats.
    
    **Si les certificats d’autorité de certification sont compromis et qu’il n’y a qu’une seule application sur le site,** procédez comme suit :
    
1. Exécutez l’applet de commande Enter-CcUpdate afin d’épuiser les services et de mettre l’appliance en mode maintenance.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Exécutez les applets de commande suivantes afin de réinitialiser et de créer les nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :
    
    Pour les publications sur le Cloud Connector avant 2,0 :
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou pour la version 2,0 du Cloud Connector ou version ultérieure :
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de cmdlet Export-CcRootCertificate à partir de l’application, puis installez le certificat exporté sur vos passerelles RTC. Il est possible que vous deviez également remettre à nouveau le certificat sur votre passerelle.

   ```powershell
   Export-CcRootCertificate
   ```

4. Exécutez l’applet de passe Exit-CcUpdate pour démarrer les services et quitter le mode maintenance.

   ```powershell
   Exit-CcUpdate
   ```


    **Si les certificats d’autorité de certification sont compromis et qu’il existe plusieurs applications sur le site,** effectuez les étapes séquentielles suivantes sur chaque application du site.
    
    Microsoft vous recommande d’effectuer ces étapes en temps réel d’utilisation.
    
1. Sur la première application, exécutez l’applet de l’applet de suppression-CcCertificationAuthorityFile pour nettoyer les fichiers de \<sauvegarde\> de l’autorité de certification dans l’annuaire SiteRoot.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Exécutez l’applet de conduite Enter-CcUpdate pour purger les services et placez chaque application en mode de maintenance.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Sur la première application, exécutez les applets de commande suivantes pour réinitialiser et créer de nouveaux certificats d’autorité de certification et tous les certificats de serveur interne :
    
     Pour les publications sur le Cloud Connector avant 2,0 :
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou pour la version 2,0 du Cloud Connector ou version ultérieure :
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. Sur la première application, exécutez l’applet de commande suivante pour sauvegarder les fichiers de l' \<autorité\> de certification dans le dossier SiteRoot.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Sur tous les autres appareils du même site, exécutez les commandes suivantes pour utiliser les fichiers de sauvegarde de l’autorité de certification, afin que les applications utilisent le même certificat racine, puis demandent de nouveaux certificats. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de certification Export-CcRootCertificate à partir de n’importe quel appareil dans le site, puis installez le certificat exporté sur vos passerelles RTC. Il est possible que vous deviez également remettre à nouveau le certificat sur votre passerelle.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Exécutez l’applet de passe Exit-CcUpdate pour démarrer les services et quitter le mode maintenance. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problème : vous recevez le message d’erreur suivant dans le journal du service de gestion des connecteurs Cloud, "C:\Program Files\Skype entreprise Cloud Connector Edition\ManagementService\CceManagementService.log" : CceService erreur : 0 : exception inattendue lors du signalement de l’État sur Online : System. Management. \<Automation. CmdletInvocationException\>: échec de l’ouverture de session de l’administrateur client global de l’utilisateur. Créez un nouvel objet d’information d’identification, en vous assurant d’avoir utilisé le nom d’utilisateur et le mot de passe appropriés. ---\>**
    
    **Résolution :** Les informations d’identification d’administrateur de client Office 365 globales ont été modifiées depuis l’inscription de l’application Cloud Connector. Pour mettre à jour les informations d’identification stockées localement sur le périphérique Cloud Connector, exécutez la commande suivante à partir d’administrateur PowerShell sur l’appareil hôte :
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problème : après avoir modifié le mot de passe du compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : clé non valide pour une utilisation dans l’état spécifié ». dans%ProgramFiles%\Skype entreprise Cloud Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de l’applet de passe Get-CcCredential.**
    
    **Résolution :** Les informations d’identification de tous les connecteurs Cloud sont stockées dans le fichier suivant : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Lorsque le mot de passe du serveur hôte change, vous devrez mettre à jour les informations d’identification stockées localement.
    
    **Si vous exécutez le Cloud Connector version 1.4.2,** régénérez tous les mots de passe du connecteur Cloud en procédant comme suit :
    
  1. Redémarrez le serveur hôte.
    
  2. Supprimez le fichier suivant : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  3. Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance-local » pour entrer de nouveau le mot de passe suivi de la description. Entrez le mot de passe que vous avez entré auparavant pour le déploiement Cloud Connector.
    
     **Si vous exécutez le Cloud Connector version 2,0 ou une version ultérieure,** régénérez tous les mots de passe du connecteur Cloud en procédant comme suit :
    
  4. Redémarrez le serveur hôte.
    
  5. Supprimez le fichier suivant : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  6. Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance-local » pour entrer de nouveau le mot de passe suivi de la description. 
    
     Si le fichier de mot de passe mis en cache a été généré à l’aide de la version 1.4.2 du Cloud Connector, utilisez le mot de passe VMAdmin du mot de passe CceService lorsque vous y êtes invité. Entrez le mot de passe que vous avez entré précédemment pour le déploiement Cloud Connector pour tous les autres comptes.
    
     Si le fichier de mot de passe mis en cache a été généré avec le Cloud Connector version 1.4.2 et que les mots de passe DomainAdmin et VMAdmin sont différents, vous devez effectuer les étapes suivantes :
    
  7. Exécutez Set-CcCredential-AccountType DomainAdmin comme suit :
    
  8. Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.
    
  9. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé auparavant.
    
     Si le fichier de mot de passe mis en cache a été généré avec le Cloud Connector version 2,0 ou ultérieure, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les étapes suivantes :
    
  10. Exécutez Set-CcCredential-AccountType DomainAdmin comme suit :
    
       1. Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService
    
       2. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé auparavant.
    
  11. Exécutez Set-CcCredential-AccountType VmAdmin comme suit :
    
       1. Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService
    
       2. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin que vous avez utilisé auparavant. 
    
- **Problème : avec le Cloud Connector version 2,1 et les versions ultérieures, lors de l’exécution de Register-CcAppliance ou d’autres applets de connexion sur l’application, vous recevez un message d’erreur tel que : « pour chaque objet : la propriété «Common » est introuvable sur cet objet. Vérifiez que la propriété existe. Dans C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char : 14 pouces**
    
    **Résolution :** Le Cloud Connector 2,1 et les versions ultérieures requièrent .NET Framework 4.6.1 ou version ultérieure. Mettez à jour .NET Framework sur l’application avec la version 4.6.1 ou une version ultérieure, puis exécutez de nouveau l’applet de contrôle.

- **Problème : avec le Cloud Connector édition 2,1, lors de l’exécution de l’installation-CcAppliance, vous recevez un message d’erreur tel que : « échec de l’installation d’une nouvelle instance avec une erreur : impossible de définir «État », car seules les chaînes peuvent être utilisées en tant que valeurs pour définir les propriétés XmlNode».**

   **Résolution :** Dans Cloudconnector. ini, sous la section [Common], ajoutez la configuration « State » comme suit : CountryCode = US State = WA City = Redmond

   La valeur de la ligne « State » n’est pas obligatoire, mais la ligne « State » ne peut pas être supprimée du fichier Cloudconnector. ini.

- **Problème : vous recevez le message d’erreur suivant : «démonter-WindowsImage : Dismount-WindowsImage a échoué. Code d’erreur = 0xc1550115 "lors de l’installation ou de la mise à niveau de la version Cloud Connector.**
    
    **Résolution :** Lancez une console PowerShell en tant qu’administrateur, exécutez "DISM-Cleanup-Wim" ". Toutes les images dépendantes sont nettoyées. Exécutez de nouveau l’installation-CcAppliance ou attendez que la mise à niveau du bit soit automatique.
    
- **Problème : échec du déploiement du premier appareil de connexion Cloud dans un environnement HA**
    
    **Résolution :** Les étapes que vous prenez dépendent de la raison pour laquelle le déploiement a échoué :
    
  - Si la première Appliance du connecteur Cloud ne fonctionne pas et que vous ne pouvez pas déterminer la raison de l’échec, vous devez réinstaller celle-ci jusqu’à ce que le déploiement réussisse, puis installer les autres appareils.
    
  - Si la première Appliance du connecteur Cloud ne fonctionne pas avec un problème mineur, tel qu’un problème de certificat externe, vous serez peut-être en mesure de résoudre le problème sans réinstaller l’appliance. Vous pouvez ensuite utiliser Remote PowerShell distante pour marquer le déploiement comme ayant abouti comme suit. (Vous pouvez également suivre les étapes ci-dessous si le premier déploiement a abouti, mais pour une raison quelconque, le connecteur Cloud ne peut pas signaler le déploiement en tant que succès.)
    
  - Pour obtenir l’identité (GUID) du premier appareil de connexion Cloud, exécutez l’applet de connexion Get-CsHybridPSTNAppliance.
    
  - Pour marquer l’application comme ayant été déployée correctement, exécutez l’ensemble-CsCceApplianceDeploymentStatus en procédant comme suit :
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problème : Vous devez vérifier et installer les mises à jour de Windows manuellement sur le serveur hôte ou les machines virtuelles.**
    
   **Résolution ** Nous vous conseillons de profiter des avantages des mises à jour automatiques du système d’exploitation fournies par la version Cloud Connector de Skype Entreprise. Une fois qu’un appareil est inscrit pour une gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifieront et installeront automatiquement les mises à jour de Windows en fonction des paramètres d’heure de mise à jour du système d’exploitation.
    
   Si vous devez vérifier et installer les mises à jour de Windows manuellement, suivez les étapes de cette rubrique qui s’appliquent à votre type de déploiement. Vous devriez mettre à jour le serveur hôte en même temps que les machines virtuelles qui sont exécutées dessus pour réduire le temps d’arrêt nécessaire aux mises à jour.
    
   Si vous préférez, vous pouvez utiliser un serveur WSUS (services de mises à jour de serveur Windows) pour qu’il fournisse les mises à jour aux serveurs Cloud Connector. Assurez-vous simplement de configurer Windows Update de sorte qu’il n’effectue **pas** d’installation automatique.
    
   Pour en savoir plus sur la mise à jour de votre déploiement Cloud Collector manuellement, consultez la rubrique suivante.
    
- **Problème : lors de la mise à jour du connecteur Cloud vers une nouvelle version, les applets de construction Cloud Connector ne sont pas mis à jour.** Cela se produit parfois si une fenêtre PowerShell reste ouverte lorsque la mise à jour automatique se produit.
    
  **Résolution :** Pour charger les applets de commande mises à jour, vous pouvez effectuer l’une des opérations suivantes :
    
   - Fermez PowerShell sur le périphérique Cloud Connector, puis rouvrez PowerShell.
    
     - Vous pouvez exécuter import-module CloudConnector-force. 
 
-   **Problème : « le terme «Stop-CsWindowsService » n’est pas reconnu comme le nom d’une cmdlet, d’une fonction, d’un fichier de script ou d’un programme exécutable.» Lorsque vous tentez d’exécuter une cmdlet Enter-CcUpdate.**

    **Résolution :** Supprimez le fichier \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache $HOME.
PowerShell crée ce fichier sous la forme d’un cache d’applets de connexion provenant de modules qu’il recherche afin qu’il n’ait pas à réanalyser tous les modules chaque fois que cela risque de ralentir. Dans la plupart des cas, il y a eu une corruption de fichier qui proposait des résultats erronés à PowerShell lors de la lecture de ce cache.

-   **Problème : « import-module CloudConnector » génère une erreur « import-module : le module spécifié «CloudConnector » n’a pas été chargé car aucun fichier de module valide n’a été trouvé dans un répertoire de modules»**

    **Résolution **
    - Vérifiez que le module CloudConnector existe bien sous c:\Program Files\WindowsPowerShell\Modules
    
    - Après validation du module CloudConnector dans cet emplacement, la variable d’environnement PSModulePath stockant le chemin d’accès aux emplacements des modules peut être modifiée :
    
     a. Modification temporaire : démarrez PowerShell en tant qu’administrateur et exécutez la commande suivante : $env :P SModulePath = $env :P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Pour le changement permanent, démarrez PowerShell en tant qu’administrateur et exécutez les commandes suivantes, une par une : $CurrentValue = [Environment] :: GetEnvironmentVariable ("PSModulePath", "machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," machine ")

    
## <a name="install-windows-updates-manually"></a>Installer manuellement les mises à jour Windows

Si vous ne voulez pas utiliser les mises à jour automatiques dans votre environnement, suivez ces étapes pour vérifier et appliquer manuellement les mises à jour de Windows. Vérifier et installer manuellement les mises à jour de Windows nécessite de redémarrer le serveur. Lors du redémarrage d’un serveur hôte, les utilisateurs ne peuvent pas utiliser le Cloud Connector pour passer ou recevoir des appels. Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler quand elles ont lieu, puis redémarrer les machines au besoin au moment de votre choix pour éviter une perturbation des services.
  
Pour vérifier et installer manuellement les mises à jours, connectez-vous à chaque serveur hôte et ouvrez le **Panneau de contrôle**. Sélectionnez **système et sécurité \>Windows Update**, puis gérez les mises à jour et les redémarrages du serveur en fonction de votre environnement.
  
- S’il n’existe qu’un seul appareil sur le site, connectez-vous à chaque machine virtuelle et ouvrez le **Panneau de contrôle**. Sélectionnez **système et sécurité \>Windows Update**, puis configurez les mises à jour et les redémarrages du serveur, le cas échéant.
    
- S’il existe plusieurs appareils sur le site, l’instance en cours de mise à jour et de redémarrage n’est plus accessible par les utilisateurs. Les utilisateurs se connecteront à d’autres instances du déploiement jusqu’à ce que toutes les machines virtuelles et que tous les services Skype Entreprise démarrent sur les machines virtuelles après la fin des mises à jour. Pour éviter de potentielles perturbations du service, vous pouvez supprimer les instances de la haute disponibilité pendant que vous appliquez les mises à jour, puis les restaurer une fois celles-ce achevées. Pour ce faire :
    
1. Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.
    
2. Supprimez l’instance de la haute disponibilité grâce à l’applet de commande suivante :
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Suivez les étapes pour une instance unique afin d’appliquer manuellement les mises à jour et redémarrer la machine virtuelle.
    
4. Définissez à nouveau l’instance en haute disponibilité grâce à l’applet de commande suivante :
    
   ```powershell
   Exit-CcUpdate
   ```

Pour des déploiements sur plusieurs sites, suivez les étapes pour un site unique pour chaque site du déploiement, en appliquant les mises à jour un site à la fois.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Conseils lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte du Cloud Connector

Si vous avez besoin d’installer un logiciel antivirus sur l’ordinateur hôte du Cloud Connector, vous devez ajouter les exclusions suivantes :
  
- Répertoire d’appliance locale sur chaque ordinateur.
    
- Répertoire de site distant sur chaque ordinateur.
    
- Sur l’ordinateur héberge le dossier racine du site partagé.
    
- %ProgramFiles%\Skype entreprise version Cloud Connector
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Processus Microsoft. RTC. CCE. ManagementService. exe.
