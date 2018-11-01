---
title: Désactiver TLS 1.0/1.1 dans Skype pour Business Server 2015
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Préparer et implémenter la désactivation TLS 1.0 et 1.1 dans votre environnement.'
ms.openlocfilehash: 50d4da536bbfcd112057464b3d4142b3eeed2b44
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839690"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Désactiver TLS 1.0/1.1 dans Skype pour Business Server 2015

L’objectif de cet article est de fournir les instructions nécessaires pour préparer et implémenter la désactivation TLS 1.0 et 1.1 dans votre environnement. Ce processus nécessite une planification étendue et préparation. Veuillez lire attentivement toutes les informations contenues dans cet article lorsque vous effectuez votre plan pour désactiver TLS 1.0 et 1.1 pour votre organisation. Notez que plusieurs dépendances externes et les conditions de connectivité qui peuvent être affectées en désactivant TLS 1.0/1.1, importantes, planification et test se justifie.

## <a name="in-this-article"></a>Dans cet article

- [Arrière-plan et étendue](#background)
- [Conditions préalables et les processus](#prerequisites-and-process)
- [Scénarios de déploiement avancé](#advanced-deployment-scenarios)

## <a name="background"></a>Arrière-plan

Les pilotes principales permettant de TLS 1.0 et 1.1 disable prise en charge de Skype pour Business Server localement sont Conseil de sécurité des normes du secteur PCI (Payment Card) et Federal Information Processing Standards requise. Vous pouvez trouver plus d’informations pour les exigences PCI [ici](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft ne peut pas fournissent des recommandations ou non votre organisation est obligée de respecter ces ou d’autres composants requis. Vous devez déterminer si elle est nécessaire pour désactiver TLS 1.0 ou 1.1 dans votre environnement.

Microsoft a produit un livre blanc sur TLS disponible [ici](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), et il est également recommandé de l’arrière-plan de la lecture disponibles dans ce [blog Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Prise en charge étendue

*La portée* fait référence aux limites de prise en charge. Pour Skype pour Business Server localement, *dans la portée* signifie nous entièrement à prendre en charge et testés désactivation de TLS 1.0 et 1.1 pour les versions de produits répertoriées. *En cours d’étude* signifie simplement que ; Nous étudions activement transfert de ces produits dans la portée pour désactiver la prise en charge TLS. *Hors de portée* signifie que ces versions de produit ne prennent pas en charge la désactivation TLS 1.0 ou 1.1 et ne fonctionnent pas, avec les exceptions indiquées.

### <a name="fully-tested-and-supported-servers"></a>Serveurs entièrement testées et pris en charge

- Skype pour Business Server 2019
- Skype pour Business Server 2015 CU6 HF2 6.0.9319.516 ([mise à jour de mars 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) ou ultérieure sur : 
    - Windows Server 2012 (avec 3140245 Ko ou mise à jour de remplacement), 2012 R2 ou 2016
- Skype de mise à niveau sur place pour Business Server 2015, avec CU6 HF2 et versions ultérieures sur 
    - Windows Server 2008 R2, 2012 (avec KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou mise à jour de remplacement) ou 2012 R2
- Connectivité de Microsoft Exchange et Outlook Web App avec Exchange Server 2010 SP3 RU19 ou ultérieur, instructions [ici](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
 
### <a name="fully-tested-and-supported-clients"></a>Entièrement testées et prises en charge des clients

- Client de bureau Lync 2013 (Skype pour les entreprises), MSI et C2R, y compris Basic [15.0.5023.1000 et plus](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype pour le Client de bureau Business 2016, MSI [16.0.4678.1000 et versions ultérieures](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), y compris Basic
- Skype pour Business 2016, cliquez sur Exécuter nécessitent les mises à jour [d’avril 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Tous les mois et annuel séparées ciblé, 16\.0\.9126\.2152 et versions ultérieures
    - Annuel séparées et canal différé, 16\.0\.8431\.2242 et versions ultérieures
- Skype pour les entreprises des 16.15 Mac
- Skype pour l’entreprise pour iOS et Android 6.19 et versions ultérieures
- Skype Web application 2015 CU6 HF2 et supérieur (fourni avec serveur)

### <a name="currently-being-investigated"></a>En cours d’étude

#### <a name="devices"></a>Périphériques

- Le système Lync salle (également appelé SRSv1)
- Systèmes de salle Skype v2 (également appelé SRSv2)
- Surface Hub
- en fonction de 2015 Survivable Branch Appliance (SBA) ou serveur Survivable Branch Server (SBS)

#### <a name="other"></a>Autre

- Tableau de bord qualité des appels (nouvelle installation après TLS 1.0, 1.1 ont été désactivées, voir ci-dessous) *
 
### <a name="out-of-scope"></a>Hors de portée

Sauf mention contraire, les produits suivants ne sont pas dans la portée de prise en charge de la désactiver TLS 1.0/1.1 et ne fonctionnent pas dans un environnement où TLS 1.0 et 1.1 ont été désactivés.  Cela signifie que : Si vous utilisez toujours des clients ou serveurs hors de portée, vous devez mettre à jour ou supprimer ces si vous devez désactiver TLS 1.0/1.1 n’importe où dans votre Skype pour Business Server déploiement local.

- Lync Server 2013
- Windows Server 2008 et inférieur
- Lync pour Mac 2011
- Lync 2013 pour Mobile - iOS, iPad, Android ou Windows Phone
- Client Lync « MX » Windows Store
- Tous les clients Lync 2010
- Lync Phone Edition - conseils mis à jour [ici](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- en fonction de 2013 Survivable Branch Appliance (SBA) ou serveur Survivable Branch Server (SBS)

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 prend en charge une dépendance Windows Fabric version 1.0.  Dans la phase de conception pour Lync Server 2013 Windows Fabric 1.0 a été sélectionné pour son architecture distribuée attrayants et nouveau pour une réplication, haute disponibilité et tolérance de pannes.  Au fil du temps, les deux Skype pour Business Server et Windows Fabric ont considérablement amélioré cette architecture commune avec redéfinissez significatif dans les versions ultérieures.  Cours Skype pour Business 2015 Server utilise Windows Fabric 3.0, par exemple.

Malheureusement, Windows Fabric 1.0 **ne prend pas en charge TLS 1.2.  Toutefois, nous mettrons à jour Lync Server 2013 pour fonctionner avec TLS 1.2**. Il sera bientôt dans la prochaine mise à jour Cumulative pour Lync Server 2013.  Nous vous fournissons prise en charge TLS 1.2 pour activer les scénarios de coexistence, la migration, la fédération et hybrides.

Si votre organisation est obligée de désactiver TLS 1.0 et 1.1 et que vous utilisez actuellement Lync Server 2013, nous vous recommandons de commencer votre processus de planification, la possibilité vous devrez peut-être mise à niveau sur place ou côte à côte vers Skype pour (de nouveaux pools, déplacer les utilisateurs) Business Server 2015 ou version ultérieure.  Ou vous souhaiterez peut-être accélérer la migration vers Skype pour Business Online.

#### <a name="call-quality-dashboard"></a>Tableau de bord de la qualité des appels

Tableau de bord qualité d’appel local a actuellement une dépendance sur TLS 1.0 pendant l’installation du nouveau (première installation dans vos environnements sur site).  Nous étudions ce problème et planifier la publication d’un correctif dans un avenir proche.  Si vous prévoyez d’installer CQD et également désactiver TLS 1.0, nous vous recommandons que vous effectuez installation CQD tout d’abord, puis poursuivez la désactivation de TLS 1.0.

#### <a name="third-party-devices"></a>Périphériques tiers

Sur des appareils tiers tels que des téléphones 3PIP, vidéoconférence, proxys inverses et les équilibreurs de charge, veillez à valider la prise en charge TLS 1.2, tester avec soin et contactez le fournisseur, le cas échéant.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considérations relatives à la fédération lors de la désactivation TLS 1.0/1.1 sur les serveurs Edge

Vous devez soigneusement planifier et prendre en compte l’impact de la désactivation TLS 1.0/1.1 sur vos serveurs de périphérie.  Une fois que TLS 1.0 et 1.1 sont désactivés, vous pouvez trouver d’autres organisations sont ne plus être en mesure de se fédérer avec votre organisation.

Vous pouvez choisir pour conserver TLS 1.0/1.1 activé sur vos serveurs de périphérie pour maintenir la compatibilité descendante avec non corrigées (SfB 2015, Lync 2013) ou plus anciens systèmes externes (2010).

Microsoft ne peuvent pas fournir des conseils ou des recommandations sur ou non votre réseau de périmètre (ou n’importe quel réseau) relève PCI standard ; qui doit être déterminée par la société.

Skype pour Business Online est capable de TLS 1.2 aujourd'hui, donc aucun impact sur hybride/fédération avec Online n’est prévu.

PIC (Public IM Connectivity) au service des utilisateurs de Skype : nous ne prévoyez pas de désactivation TLS 1.0/1.1 pour avoir un impact sur la [Connectivité Skype](../../deploy/deploy-skype-connectivity.md); Microsoft PIC passerelles sont déjà capables de TLS 1.2.

## <a name="prerequisites-and-process"></a>Conditions préalables et les processus

Sauf mention contraire ci-dessus, une fois TLS 1.0 et 1.1 sont désactivés serveurs hors de portée, clients et périphériques fonctionnent plus correctement, ou tout. Cela signifie que vous deviez suspendre et attendre pour obtenir des conseils mis à jour de Microsoft. Une fois que vous êtes satisfait de tous les éléments requis et un plan à combler des lacunes, passez.

À un niveau élevé, tandis que Skype pour Business Server 2019 est prêt pour la procédure à l’installation, Skype pour Business Server 2015 nécessite que vous installez HF2 CU6, mise à jour prérequis .NET et SQL, les clés de Registre requis déploiement et enfin distincte Round de configuration du système d’exploitation met à jour (c'est-à-dire désactivation TLS 1.0 et 1.1 via l’importation des fichiers de Registre). Il est essentiel de procéder à l’installation de tous les éléments prérequis, notamment Skype pour Business Server 2015 CU6 HF2, avant la désactivation TLS 1.0 et 1.1 sur n’importe quel serveur dans votre environnement. Chaque Skype pour Business server, y compris le rôle de serveur Edge et les serveurs principaux SQL, nécessite les mises à jour. Vérifiez également que tous les clients (dans la portée) pris en charge ont été mis à jour pour les versions minimales requises. N’oubliez pas de mettre à jour ainsi que les stations de gestion.

Nous voulons à suivre l’ordre des opérations de « connaître » normal de mise à niveau Skype des serveurs d’entreprise. Traite les pools directeur, conversation permanente et les Pools associés de la même manière que vous le feriez normalement. Ordre et les méthodes de mise à niveau sont abordées [ici](topology.md) et [ici](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processus de haut niveau

1. Testez toutes les étapes dans votre laboratoire avant la configuration des serveurs de production.
2. Sauvegarder et de conserver une copie du Registre exporté sur chaque serveur individuel à mettre à jour. Vous ne pouvez pas partager registres entre serveurs ; elles contiennent des touches uniques sur l’ordinateur.
3. Mettre à niveau tous les Skype pour les serveurs d’entreprise 2015 CU6 HF2 ou supérieur. (Pour Skype pour Business Server 2019, aucune mise à jour Cumulative n’est nécessaire)
4. Installer tous les composants requis sur tous les serveurs.
5. Déployer des clés de Registre requis.
6. Assurez-vous que tous les clients dans la portée sont mis à jour.
7. Désactiver TLS 1.0 et 1.1 par le biais d’importation dans le Registre.
8. Valider les charges de travail fonctionnent comme prévu.
    - Si vous rencontrez des problèmes, dépannage et la résolution, ou
    - Restaurer à partir de l’étape 2 pour réactiver TLS 1.0 et 1.1
9. Valider qu’uniquement TLS 1.2 est utilisé.

### <a name="install-prerequisites-to-all-servers"></a>Installer les composants requis sur tous les serveurs

Dépendance importante mise à jour est requise avant de commencer à désactiver TLS 1.0 et 1.1 niveau le système d’exploitation dans votre Skype pour les déploiements Business Server 2015. Voici les versions minimales pouvant prendre en charge TLS 1.2. Déployer toutes les mises à jour requis sur chaque Skype pour Business server dans votre environnement avant de commencer la désactivation TLS 1.0 et 1.1.

- Skype pour Business Server 2015 CU6 HF2 6.0.9319.516 ([mise à jour de mars 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) ou supérieur
- [.NET framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) ou supérieure avec SchUseStrongCrypto activé dans le Registre (fourni ci-dessous)
- SQL doit être mis à jour sur tous les Skype pour Business 2015 serveurs et les serveurs principaux. Mettre à jour les serveurs principaux du SQL Enterprise Edition Pool tout d’abord, puis leur ces respectifs. 
    - SQL Server 2014 SP1 + CU5 ([lien](https://support.microsoft.com/help/3130926)) ou supérieur / SQL Server 2012 SP2 + CU16 ou supérieur / SQL Server 2014 RTM + CU12 ([lien](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) ou supérieur / SQL Server 2014 SP2
    - SQL Server Native Client pour SQL Server 2012 ([lien](https://www.microsoft.com/en-us/download/details.aspx?id=50402))
    - 11 de pilote ODBC Microsoft SQL Server ([lien](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) ou supérieur
    - Partagé des objets de gestion pour SQL Server 2014 SP2 ([lien](https://www.microsoft.com/en-in/download/details.aspx?id=42295))
    - SQLSysClrTypes pour SQL server 2014 SP2 ([lien](https://www.microsoft.com/en-in/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Étapes de base pour installer les composants requis, dans l’ordre recommandé des opérations

1. Installer le Skype pour Business Server CU6HF2 (6.0.9319.516) mise à jour à tous les serveurs. 
    1. Installez la mise à jour à l’aide de la mise à jour des composants.
    2. Mettre à jour les bases de données en fonction des procédures documentées. Instructions sont documentées à [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).
    3. Valider les fonctionnalités du produit dans le déploiement avant de poursuivre les modifications.
2. Téléchargez .NET 4.7 programme d’installation en mode hors connexion. 
    1. Référence :[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)
    2. Assurez-vous que Skype pour les services Business Server 2015 sont arrêtés sur le serveur frontal.
    3. Référence :[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition) : Stop-CsWindowsServices
    5. Ex (Enterprise Edition) : Invoke-CsComputerFailover
    6. Exécutez le package d’installation.
    7. Redémarrez le serveur.
3. Mettre à jour SQL Express 2014 sur tous les serveurs. 
    1. Référence :[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Télécharger SQL 2014 SP2 
        - Référence :[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)
    3. Copiez le support d’installation dans un dossier sur le serveur (Ex : C:\01_2014SqlSp2)
    4. Assurez-vous de Skype pour Business Server 2015 services sont arrêtés sur le serveur frontal 
        - Ex (Standard Edition) : Stop-CsWindowsService
        - Ex (Enterprise Edition) : Invoke-CsComputerFailove
    5. Ouvrez une invite de commandes d’administration et de mettre à niveau tous les composants installés et instances 
        - Exemple : C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = Patch /AllInstances
4. Mise à jour SQL Native Client. 
    1. Référence : [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Télécharger à partir de[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)
    3. Vérifiez que Skype pour Business Server 2015 services sont arrêtés sur le serveur frontal. 
        - Ex (Standard Edition) : Stop-CsWindowsServices
        - Ex (Enterprise Edition) : Invoke-CsComputerFailove
    4. Arrêter les instances SQL installés à partir de l’exécution 
        - Ex : Get-Service « MSSQL$ RTCLOCAL » | STOP-service
        - Ex : Get-Service « MSSQL$ LYNCLOCAL » | STOP-service
        - Ex (Standard Edition seulement) : Get-Service « MSSQL$ RTC » | STOP-service
    5. Installez la mise à jour.
5. Mettre à jour le pilote ODBC 11 pour SQL Server. 
    1. Référence : [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Télécharger à partir de[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)
    3. Assurez-vous que Skype pour les services Business Server 2015 sont arrêtés sur le serveur frontal 
        - Ex (Standard Edition) : Stop-CsWindowsService
        - Ex (Enterprise Edition) : Invoke-CsComputerFailove
    4. Installez la mise à jour.
6. Déployer des clés de Registre requis.

### <a name="pre-requisite-registry-keys"></a>Clés de Registre requis

Copier/coller le test suivant dans le bloc-notes et renommer TLSPreReq.reg ou un nom de votre choix, puis importer :

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

Pour SQL back désactiver extrémités pour TLS, les conditions préalables et les Pools d’entreprise Edition doit être traitée comme le feriez pour les mises à jour SQL ou du système d’exploitation ; reportez-vous à :[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Alors que l’application requise et TLS désactivation des étapes peuvent être combinés, nous vous recommandons vivement d’appliquer toutes les conditions préalables avant de procéder à la désactivation de TLS 1.0 et 1.1 au niveau du système d’exploitation. La meilleure pratique serait pour préparer l’environnement en déployant tous les éléments prérequis, valider que toutes les charges de travail fonctionnent comme prévu et correctement, puis continuer avec TLS 1.0/1.1 désactiver à une date ultérieure.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Désactiver TLS 1.0 et 1.1 par le biais d’importation dans le Registre

Avant de poursuivre avec les étapes suivantes, *Assurez-vous que vous avez terminé toutes les conditions préalables et mis à jour Skype des serveurs d’entreprise*.

Copiez le texte suivant dans un fichier Bloc-notes et renommez-le **TLSDisable.reg**:

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

Importez le fichier .reg sur chaque serveur que vous souhaitez désactiver TLS 1.0 et 1.1. Redémarrez le serveur. Une fois que les services ont remis en ligne, déplacer vers le serveur suivant. L’approche pour les Pools d’entreprise Edition est la même que risque de prendre pour une mise à jour du système d’exploitation.

Vous avez remarqué que nous faisons plus de désactiver TLS 1.0 et 1.1 ici. Nous effectuons prenant en charge la Suite de chiffrement réorganiser (comme indiqué ci-dessus) et la désactivation de certains anciens chiffrement faible. Il s’agit de la première fois que nous avons officiellement pris en charge ces modifications à SCHANNEL et API de chiffrement sur Skype pour Business Server, et il est important de noter que ces modifications sont les seuls à nous prennent en charge et testés à ce stade. Il peut prendre en compte les configurations supplémentaires à l’avenir, mais pour l’instant, ne modifiez pas le fichier d’importation dans le Registre dans votre implémentation.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Valider les charges de travail fonctionnent comme prévu

Une fois que TLS 1.0 et 1.1 ont été désactivés dans votre environnement, assurez-vous que toutes vos charges de travail principales fonctionnent comme prévu, telles que la messagerie instantanée et présence, P2P appelle, Enterprise Voice, etc..

**Valider uniquement TLS 1.2 est utilisé**

Demandez à votre équipe de sécurité de procéder à une nouvelle vérification de Skype pour le trafic d’entreprise pour s’assurer que les anciens protocoles TLS 1.0 et 1.1 ne sont plus utilisés.

Sinon, vous pouvez utiliser Internet Explorer pour tester les connexions TLS aux services web à partir de Skype Business Server 2015 après que TLS 1.0 et 1.1 TLS ont été désactivés.

1. Lancez Internet Explorer.
2. Sélectionnez **Outils** > **Options Internet**.
3. Sélectionnez l’onglet **Options avancées** .
4. Sous **paramètres**, faites défiler vers le bas.
5. Vérifiez que TLS 1.0, TLS 1.1 et TLS 1.2 sont activés.
6. Accédez à l’URL du Service Web interne de votre pool 2015 SfB (doivent se connecter correctement).
7. Revenez dans Internet Explorer et désactiver l’option pour **utiliser TLS 1.2** uniquement.
8. Accédez à l’URL de Service Web interne de votre pool SfB 2015 à nouveau (défaillance pour se connecter).

![Options Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Scénarios de déploiement avancé

Étant donné que certains logiciels de dépendance sont nécessaires pour prendre en charge TLS 1.2 Skype pour Business Server 2015, l’installation à partir du média RTM échoue sur n’importe quel système où TLS 1.0 et 1.1 ont été désactivés.

**Déploiement de nouveaux serveurs Standard Edition Server ou Enterprise Edition Pools une fois que TLS 1.0 et 1.1 ont été désactivés dans votre environnement.**

**Option 1 :** Utilisez [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Notez que nous SmartSetup pour prendre en charge les mises à jour binaires SQL dans une mise à jour Cumulative future mise à jour et met à jour cet article à l’avenir.

**Option 2 :** Installation locales instances SQL (RTCLOCAL et LYNCLOCAL)

1. Télécharger et copier SQL Express 2014 SP2 (SQLEXPR_x64.exe) dans un dossier local sur FE. Supposons que le chemin d’accès du dossier < SQL_FOLDER_PATH >.
2. Lancer PowerShell ou invite de commandes et accédez au < SQL_FOLDER_PATH >.
3. Créer l’instance SQL RTCLOCAL en exécutant la commande ci-dessous. Attendez que SQLEXPR_x64.exe se termine avant de continuer :

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = installer/fonctionnalités = SQLEngine, outils/InstanceName = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = « NT\SERVICE » /SQLSYSADMINACCOUNTS = Builtin\ » Les administrateurs » /BROWSERSVCSTARTUPTYPE = /AGTSVCACCOUNT « Automatique » = « NTAUTHORITY\NetworkService » /SQLSVCSTARTUPTYPE = Automati
1. Créer l’instance SQL LYNCLOCAL en exécutant la commande ci-dessous. Attendez que SQLEXPR_x64.exe se termine avant de passer à l’étape suivante :

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = installer/fonctionnalités = SQLEngine, outils/InstanceName = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = « NT\SERVICE » /SQLSYSADMINACCOUNTS = Builtin\ » Les administrateurs » /BROWSERSVCSTARTUPTYPE = /AGTSVCACCOUNT « Automatique » = « NTAUTHORITY\NetworkService » /SQLSVCSTARTUPTYPE = automatique
1. Exécutez Skype pour le programme d’installation Business Server 2015 RTM.
2. Suivez les étapes restantes dans la section conditions préalables ci-dessus.

**Option 3 :** Vous pouvez remplacer manuellement les fichiers binaires dans un répertoire de support d’installation locale comme suit :

1. [Installer les éléments prérequis pour Skype pour Business Server](../../deploy/install/install-prerequisites.md)  
2. 2. Installer .NET 4.7 : 
      - **Remarque :** Tout d’abord, nous avons introduit la prise en charge de .NET 4.7 dans Skype pour Business Server 2015 CU5 + (6.0.9319.281). Par conséquent, dans les étapes ultérieures ci-dessous nous mettrons à jour des composants principaux avant l’installation principale.
      - Téléchargement : https://www.microsoft.com/en-us/download/details.aspx?id=55167.
      - Référence : [logiciel qui doit être installé avant un Skype pour le déploiement de Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiez les fichiers/dossiers ISO : 
    - Skype pour Business Server 2015 ISO attaché, ouvrez le répertoire racine du lecteur, il est joint sous (Ex : d :\) dans l’Explorateur de fichiers.
    - Copiez tous les fichiers et dossiers dans un dossier sur un disque local (Ex : C:\SkypeForBusiness2015ISO).
    - **Remarque :** Avant d’installer les composants, certains fichiers devront être mis à jour pour la prise en charge de TLS 1.2.
4. Remplacez les Packages MSI/EXE : 
    - Remplacez les packages MSI et EXE existants dans le dossier/amd64//Setup du support d’installation sur l’ordinateur local.
    - SQL 2014 SP2 Express :https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Renommez SQLEXPR_x64 sur l’ordinateur local et remplacez le fichier existant dans l’installation/amd64/dossier du support d’installation.
    - SQL Native Client :https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Remarque :** Renommez ce si nécessaire pour sqlncli.msi et remplacez le fichier existant qui existe dans l’installation/amd64/dossier du support d’installation.
    - Objets de gestion SQL :https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Remarque :** Le pack de fonctionnalités aura un grand nombre d’éléments qui peuvent être téléchargés. Sélectionnez cette option pour télécharger SharedManagementObjects.msi uniquement.
        - **Remarque :** Remplacer le fichier existant qui existe dans l’installation/amd64/dossier du support d’installation.
    - Types CLR SQL :https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Remarque :** Le pack de fonctionnalités aura un grand nombre d’éléments qui peuvent être téléchargés. Sélectionnez cette option pour télécharger CQLSysClrTypes.msi uniquement
        - **Remarque**: remplacer le fichier existant qui existe dans l’installation/amd64/dossier du support d’installation.
5. Installez les composants principaux : 
    - Exécutez Setup.exe à partir de l’installation/amd64/dossier du support d’installation. Suivez les instructions pour installer les composants principaux
    - Fermez les composants principaux.
6. Mettre à jour des composants principaux : 
    - Téléchargez le Skype pour le programme d’installation de Business mise à jour.
    - Exécutez le programme d’installation pour mettre à jour les composants principaux et installer les compteurs de performance.
    - **Remarque :** La version de CU6HF2, la fonctionnalité de mise à jour automatique actuellement uniquement installera jusqu'à CU6. Par conséquent, la mise à jour doit être exécuté séparément pour mettre à jour des composants principaux pour 6.0.9319.516.
    - Référence :https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Installer les outils d’administration (facultatifs) : 
    - Vous allez installer le Client natif Microsoft SQL Server 2012, SQL Server 2014 Management Objects (x64) et Types CLR du système Microsoft pour SQL Server 2014 (x64) en utilisant les fichiers de mise à jour. En outre, le Skype pour le Générateur de topologie Business Server 2015 et le panneau de configuration sera disponible sur l’ordinateur local.
8. Magasin de configurations Local Installation (étape 1) : 
     - Ouvrir l’Assistant déploiement, cliquez sur Installer ou mettre à jour Skype pour le système de serveur d’entreprise, puis cliquez sur **exécuter** à l’étape 1 : installer le magasin de Configuration Local.
     - Cliquez sur **suivant** dans la boîte de dialogue **Installer le magasin de Configuration Local** .
     ![Boîte de dialogue installer le magasin de configurations Local](../../media/local-configuration-store.png)
     - Passez en revue les résultats et assurez-vous que l’état de la tâche est terminée. Passez en revue le fichier journal en cliquant sur **Afficher le journal**.
     ![État de la tâche apparaisse comme terminé](../../media/local-configuration-task-completed.png)
     - Cliquez sur **Terminer**.
9. Définir ou supprimer Skype pour les composants de serveur d’entreprise (étape 2) :
    - Ouvrir l’Assistant déploiement, cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, cliquez sur **exécuter** à l’étape 2 : configurer ou supprimer Skype pour les composants de serveur d’entreprise
    - Cliquez sur **suivant** dans Définissez les Skype pour la boîte de dialogue composants Business Server.
    ![Définir des Skype pour fenêtre composants Business Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Passez en revue le journal à l’aide d’afficher le journal et valider que le programme d’installation terminé sans problème. 
    - Cliquez sur **Terminer**.
10. Poursuivre l’installation supplémentaire et la configuration selon les besoins (vous pouvez reprendre des procédures d’installation normal à ce stade).
