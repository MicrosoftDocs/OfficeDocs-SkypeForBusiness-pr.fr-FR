---
title: Désactiver TLS 1.0/1.1 dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Préparez et implémentez la désactivation de TLS 1.0 et 1.1 dans vos environnements.
ms.openlocfilehash: 27c0b0a0650e2d2481c2e34c32ab6176e53956d7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401928"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Désactiver TLS 1.0/1.1 dans Skype Entreprise Server 2015

Cet article vous aide à préparer et à implémenter la désactivation de TLS 1.0 et 1.1 dans vos environnements. Ce processus nécessite une planification et une préparation complètes. Examinez attentivement toutes les informations de cet article lorsque vous planifiez la désactivation de TLS 1.0 et 1.1 pour votre organisation. Il existe de nombreuses dépendances externes et conditions de connectivité qui peuvent être touchées par la désactivation de TLS 1.0/1.1, de sorte que la planification et les tests approfondis sont justifiés.

- [Arrière-plan et étendue](#background-and-scope)
- [Conditions préalables et processus](#prerequisites-and-process)
- [Scénarios de déploiement avancés](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>Arrière-plan et étendue

Les principaux facteurs de désactivation de TLS 1.0 et 1.1 pour Skype Entreprise Server Local sont les exigences du Conseil des normes de sécurité PCI (Payment Card Industry) et des normes fédérales de traitement des informations. Pour plus d’informations sur les exigences PCI, voir [ici](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft ne peut pas fournir de conseils sur la nécessité ou non pour votre organisation de respecter ces exigences ou d’autres. Vous devez déterminer s’il est nécessaire de désactiver TLS 1.0 et/ou 1.1 dans vos environnements.

Microsoft a publié un livre blanc sur TLS disponible [ici, et](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/) nous vous recommandons également la lecture en arrière-plan disponible dans [ce blog Exchange.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)

## <a name="supportability-scope"></a>Étendue de prise en charge

*L’étendue* fait référence aux limites de prise en charge. *Les tests complets* et pris en charge signifient que nous activons entièrement et avons testé la désactivation de TLS 1.0 et 1.1 pour les versions de produits répertoriées. *L’examen en cours* signifie simplement cela ; Nous sommes activement en train d’examiner l’application de ces produits dans l’étendue de la désactivation de la prise en charge de TLS. *Hors de portée signifie* que ces versions de produit ne sont pas en charge de la désactivation de TLS 1.0 ou 1.1 et ne fonctionneront pas, avec des exceptions notées.

### <a name="fully-tested-and-supported-servers"></a>Serveurs entièrement testés et pris en charge

- Skype Entreprise Server CU1 2019 17.0.2046.123 (juin 2019) ou une date supérieure
- Skype Entreprise Server 2015 CU9 6.0.9319.548 (mai 2019) ou version supérieure sur Windows Server 2012 (avec mise à jour de [la 3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou de la mise à jour de la mise à jour de la Ko), 2012 R2 ou 2016.
- Mise à niveau sur place Skype Entreprise Server 2015, avec CU9 6.0.9319.548 (mai 2019) ou version supérieure sur Windows Server 2008 R2, 2012 (avec mise à jour de [la 3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou de la mise à jour de la mise à jour de la KB) ou 2012 R2.
- Exchange connectivité et Outlook Web App avec Exchange Server 2010 SP3 RU19 ou une édition supérieure, [conseils](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/) ici
- Survivable Branch Appliance (SBA) avec Skype Entreprise Server 2015 CU6 HF2 ou version supérieure (confirmez auprès de votre fournisseur qu’il a empaqueté les mises à jour appropriées et qu’il a été mis à disposition pour votre appliance)
- Serveur Survivable Branch Server (SBS) avec Skype Entreprise Server CU6 2015 HF2 ou supérieur
- Rôle **Edge** Lync Server 2013 uniquement, car le rôle Edge n’a pas de dépendance sur Windows Fabric 1.0.

### <a name="fully-tested-and-supported-clients"></a>Clients entièrement testés et pris en charge

- Client de bureau Lync 2013 (Skype Entreprise), MSI et C2R, y compris Basic [15.0.5023.1000 ou version supérieure](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype Entreprise client de bureau 2016, MSI [16.0.4678.1000 ou version supérieure](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), y compris De base
- Skype Entreprise 2016 Click to Run Nécessite les [mises à jour d’avril 2018](/officeupdates/release-notes-office365-proplus) : 
    - Mensuelle et Semi-Annual ciblée, 16091262152\.\.\. ou supérieure
    - Semi-Annual canal différé, 16084312242\.\.\. ou supérieur
- Skype Entreprise mac 16.15 ou supérieur
- Skype Entreprise pour iOS et Android 6.19 ou version supérieure
- Salles Microsoft Teams (précédemment appelé Skype Room System V2 SRS V2) 4.0.64.0 (décembre 2018) ou une édition supérieure
- Surface Hub mise à jour pour l’édition Team basée sur KB4499162 (mai 2019, version du système d’exploitation 15063.1835) ou version supérieure
- Skype Web App 2015 CU6 HF2 ou une valeur supérieure (est intégré au serveur)

### <a name="currently-being-investigated"></a>Actuellement en cours d’examen

- Tableau de bord de qualité des appels (nouvelle installation après la désactivation de TLS 1.0, 1.1, voir ci-dessous)*
 
### <a name="out-of-scope"></a>Non compris

Sauf remarque, les produits suivants ne sont pas dans l’étendue de la désactivation de TLS 1.0/1.1 et ne fonctionnent pas dans un environnement où TLS 1.0 et 1.1 ont été désactivés. Cela signifie que si vous utilisez toujours des serveurs ou des clients hors étendue, vous devez les mettre à jour ou les supprimer si vous devez désactiver TLS 1.0/1.1 n’importe où dans votre déploiement local Skype Entreprise Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 ou inférieur
- Lync pour Mac 2011
- Lync 2013 pour mobile - iOS, iPad, Android ou Windows Phone
- Client Lync « MX » Windows Store
- Lync Room System (alias SRSv1). LRS a atteint la fin de la prise en charge le 9 octobre 2018 et ne sera pas mis à jour pour prendre en charge TLS 1.2.
- Tous les clients Lync 2010
- Lync Téléphone Edition : conseils mis à [jour ici](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- Survivable Branch Appliance (SBA) ou Survivable Branch Server (SBS) 2013
- Cloud Connector Edition (CCE)
- Skype Entreprise pour Windows Phone

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 prend une dépendance Windows Fabric version 1.0.  Lors de la phase de conception de Lync Server 2013, Windows Fabric 1.0 a été choisi pour son architecture distribuée attrayante et nouvelle pour fournir la réplication, la haute disponibilité et la tolérance de panne.  Au fil du temps, les Skype Entreprise Server et Windows Fabric ont considérablement amélioré cette architecture conjointe avec une nouvelle conception significative dans les versions suivantes.  Current Skype Entreprise Server 2015 utilise Windows Fabric 3.0, par exemple.

Malheureusement, Windows Fabric 1.0 ne prend pas en **charge TLS 1.2.  Toutefois, nous mettons à jour Lync Server 2013 pour fonctionner avec TLS 1.2**. Cette mise à jour sera prochainement mise à jour cumulative pour Lync Server 2013.  Nous fournissons la prise en charge de TLS 1.2 pour activer la coexistence, la migration, la fédération et les scénarios hybrides.

Si votre organisation est tenue de désactiver TLS 1.0 et 1.1 et que vous utilisez actuellement Lync Server 2013, nous vous recommandons de commencer le processus de planification, avec la possibilité de devoir mettre à niveau sur place ou migrer côte à côte (nouveaux pools, déplacer des utilisateurs) vers Skype Entreprise Server 2015 ou version supérieure.  Vous pouvez également accélérer la migration vers Skype Entreprise Online.

#### <a name="call-quality-dashboard"></a>Tableau de bord de la qualité des appels

Le tableau de bord de qualité des appels local dépend actuellement de TLS 1.0 lors de la nouvelle installation (première installation dans vos environnements locaux).  Nous enquêtons actuellement sur ce problème et prévoyons de publier un correctif dans un futur proche.  Si vous envisagez d’installer le CQD et de désactiver TLS 1.0, nous vous recommandons d’effectuer d’abord l’installation du CQD, puis de procéder à la désactivation de TLS 1.0.

#### <a name="skype-for-business-sdn-manager"></a>Skype Entreprise SDN Manager

Skype Entreprise gestionnaire SDN utilisant SQL base de données a une dépendance sur TLS 1.0 lors de la nouvelle installation. Si vous envisagez d’installer Skype Entreprise SDN Manager à l’aide de SQL une base de données et de désactiver TLS 1.0, nous vous recommandons d’effectuer Skype Entreprise SDN Manager d’abord, puis de procéder à la désactivation de TLS 1.0. Si TLS 1.0 est désactivé avant l’installation, vous devez activer temporairement TLS 1.0 sur le serveur principal SQL Server qui sera utilisé pour héberger la base de données SQL du Gestionnaire SDN Skype Entreprise.

#### <a name="third-party-devices"></a>Appareils tiers

Sur les appareils tiers tels que les téléphones 3PIP, la vidéoconférence, les proxies inverses et les équilibreurs de charge, assurez-vous de valider la prise en charge de TLS 1.2, de tester attentivement et de contacter le fournisseur si nécessaire.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considérations sur la fédération lors de la désactivation de TLS 1.0/1.1 sur les serveurs Edge

Vous devez soigneusement planifier et prendre en compte l’impact de la désactivation de TLS 1.0/1.1 sur vos serveurs Edge.  Une fois que TLS 1.0 et 1.1 sont désactivés, il se peut que vous trouviez que d’autres organisations ne peuvent plus se fédérer avec votre organisation.

Vous pouvez choisir de conserver TLS 1.0/1.1 activé sur vos serveurs Edge pour maintenir la compatibilité ascendante avec les systèmes externes non corrigés (SfB 2015, Lync 2013) ou plus anciens (2010).

Microsoft ne peut pas fournir de conseils ou de recommandations sur le fait que votre réseau Edge (ou tout autre réseau) tombe ou non sous la norme PCI ; qui doit être déterminé par la société individuelle.

Skype Entreprise Online est capable de TLS 1.2 aujourd’hui, donc aucun impact sur l’environnement hybride/la fédération avec Online n’est attendu.

PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Les passerelles Microsoft PIC sont déjà capables de TLS 1.2.

## <a name="prerequisites-and-process"></a>Conditions préalables et processus

Sauf remarque ci-dessus, une fois que les serveurs hors étendue TLS 1.0 et 1.1 sont désactivés, les clients et les appareils fonctionnent plus correctement ou du tout. Cela peut signifier que vous devez suspendre et attendre les conseils mis à jour de Microsoft. Une fois que vous êtes satisfait de répondre à toutes les exigences et que vous avez un plan pour corriger les lacunes, continuez.

À un niveau élevé, alors que Skype Entreprise Server 2019 est prêt pour la procédure d’installation, Skype Entreprise Server 2015 nécessite l’installation de cu9, l’application des mises à jour prérequises à .NET et SQL, le déploiement des clés de Registre prérequises et enfin une série distincte de mises à jour de configuration du système d’exploitation (c’est-à-dire la désactivation de TLS 1.0 et 1.1 via le fichier de Registre).  ). Il est essentiel de terminer l’installation de toutes les conditions préalables, y compris Skype Entreprise Server 2015 CU6 HF2, avant de désactiver TLS 1.0 et 1.1 sur n’importe quel serveur de votre environnement. Chaque serveur Skype Entreprise, y compris le rôle Edge et les serveurs SQL principal, nécessite les mises à jour. Assurez-vous également que tous les clients pris en charge (dans l’étendue) ont été mis à jour vers les versions minimales requises. N’oubliez pas également de mettre à jour les stations de travail de gestion.

Nous voulons suivre l’ordre habituel des opérations de « intérieur » pour la mise à niveau Skype Entreprise serveurs. Traitez les pools directeurs, la conversation permanente et les pools associés de la même manière que normalement. L’ordre et les méthodes de mise à niveau sont [traités ici](topology.md) et [ici](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processus de haut niveau

1. Testez toutes les étapes de votre atelier avant de configurer les serveurs de production.
2. Sauvegarder et conserver une copie du Registre exporté sur chaque serveur à mettre à jour. Vous ne pouvez pas partager des Registres entre des serveurs ; Elles contiennent des clés uniques basées sur l’ordinateur.
3. Mettre à niveau Skype Entreprise serveurs 2015 vers cu9 ou version supérieure. Pour Skype Entreprise Server 2019, mise à niveau vers CU1 ou version supérieure.
4. Installez tous les prérequis sur tous les serveurs.
5. Déployez les clés de Registre prérequises.
6. Assurez-vous que tous les clients dans l’étendue sont mis à jour.
7. Désactivez TLS 1.0 et 1.1 via l’importation du Registre.
8. Vérifier que les charges de travail fonctionnent comme prévu.
    - Si des problèmes sont rencontrés, résolvez et résolvez les problèmes, ou
    - Restaurer le Registre à partir de l’étape 2 pour ré-activer TLS 1.0 et 1.1
9. Vérifier que seul TLS 1.2 est utilisé.

### <a name="install-prerequisites-to-all-servers"></a>Installer les conditions préalables sur tous les serveurs

Une mise à jour complète des dépendances est nécessaire avant de commencer à désactiver TLS 1.0 et 1.1 au niveau du système d’exploitation dans vos déploiements Skype Entreprise Server 2015. Voici les versions minimales qui peuvent prendre en charge TLS 1.2. Déployez toutes les mises à jour préalables sur chaque serveur Skype Entreprise de votre environnement avant de commencer à désactiver TLS 1.0 et 1.1.

- Skype Entreprise Server CU9 2015 6.0.9319.548 (mai 2019) ou une valeur supérieure
- [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) ou supérieur avec SchUseStrongCrypto activé dans le Registre (fourni ci-dessous)
- SQL doit être mis à jour sur tous Skype Entreprise serveurs et serveurs back-end 2015. Mettez à Êdition Entreprise les SQL pool, puis leurs FES respectives. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), ou supérieur / SQL Server 2012 SP2 + CU16 ou supérieur / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), ou supérieur / SQL Server 2014 SP2
     - [SQL Server Native Client pour SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Pilote ODBC Microsoft 11 pour SQL Server](https://www.microsoft.com/download/details.aspx?id=36434) ou supérieur
     - [Objets de gestion partagés pour SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes pour SQL server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Étapes de base pour installer les conditions préalables, dans l’ordre recommandé des opérations

1. Installez la mise Skype Entreprise Server cu9 sur tous les serveurs. 
    1. Installez la mise à jour sur les composants à l’aide du programme de mise à jour.
    2. Mettre à jour les bases de données en fonction des procédures documentées. Pour Skype Entreprise Server 2015, voir la 3061064 de [la 3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Valider les fonctionnalités du produit dans le déploiement avant d’apporter d’autres modifications.
2. Téléchargez le programme d’installation hors connexion .NET 4.7. 
    1. Référence : [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Assurez-vous Skype Entreprise Server services 2015 sont arrêtés sur le serveur frontal.
    3. Référence : [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Édition Standard) :```Stop-CsWindowsService```
    5. Ex (Êdition Entreprise) :```Invoke-CsComputerFailover```
    6. Exécutez le package d’installation.
    7. Redémarrez le serveur.
3. Mettez à SQL Express 2014 sur tous les serveurs. 
    1. Référence : [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Télécharger SQL 2014 SP2 
        - Référence : [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copiez le support d’installation dans un dossier sur le serveur (ex : C:\01_2014SqlSp2)
    4. Vérifier Skype Entreprise Server services 2015 sont arrêtés sur le serveur frontal 
        - Ex (Édition Standard) :```Stop-CsWindowsService```
        - Ex (Êdition Entreprise) :```Invoke-CsComputerFailover```
    5. Ouvrez une invite de commandes d’administration et mettre à niveau tous les composants et instances installés 
        - Exemple : C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. Mettez à jour SQL Native Client. 
    1. Référence : [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Téléchargement à partir de [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Assurez Skype Entreprise Server services 2015 sont arrêtés sur le serveur frontal. 
        - Ex (Édition Standard) :```Stop-CsWindowsServices```
        - Ex (Êdition Entreprise) :```Invoke-CsComputerFailover```
    4. Arrêter l’exécution SQL instances installées 
        - Par exemple : ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Par exemple : ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (Édition Standard uniquement) :```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Installez la mise à jour.
5. Mettez à jour le pilote ODBC 11 SQL Server pour inclure la prise en charge de TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. [Téléchargez le pilote ODBC 11 pour SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Assurez-vous Skype Entreprise Server services 2015 sont arrêtés sur le serveur frontal.
        - Exemple (Édition Standard) :```Stop-CsWindowsService```
        - Exemple (Êdition Entreprise) :```Invoke-CsComputerFailover```
    3. Installez la mise à jour.
6. Déployez les clés de Registre prérequises.

### <a name="pre-requisite-registry-keys"></a>Clés de Registre pré-requises

Copiez/collez le test suivant dans Bloc-notes puis renommez TLSPreReq.reg ou un nom de votre choix, puis importez :

```console
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

Pour SQL back end pour les pools Êdition Entreprise, les conditions préalables et la désactivation de TLS doivent être traitées comme n’importe quelle SQL ou mises à jour du système d’exploitation ; reportez-vous à :[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)

Bien que les étapes de désactivation de l’application prérequise et de TLS soient combinées, nous vous recommandons vivement d’appliquer toutes les conditions préalables avant de poursuivre la désactivation de TLS 1.0 et 1.1 au niveau du système d’exploitation. La meilleure approche consiste à préparer l’environnement en déployant tous les prérequis, en validant que toutes les charges de travail fonctionnent correctement et comme prévu, puis en désactivant TLS 1.0/1.1 ultérieurement.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Désactiver TLS 1.0 et 1.1 via l’importation du Registre

Avant de passer aux étapes suivantes, assurez-vous que vous avez rempli toutes les conditions préalables et mis à *jour Skype Entreprise Serveurs*.

Copiez le texte suivant dans un fichier Bloc-notes et renommez-le **TLSDisable.reg** :

```console
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

Importez le fichier .reg sur chaque serveur pour désactiver TLS 1.0 et 1.1. Redémarrez le serveur. Une fois les services de retour en ligne, déplacez-vous vers le serveur suivant. L’approche pour Êdition Entreprise pools de systèmes d’exploitation est la même que pour toute mise à jour du système d’exploitation.

Vous avez peut-être remarqué que nous n’avons pas simplement désactivé TLS 1.0 et 1.1 ici. Nous activons l’ordre de re-commande de la suite de chiffrement (comme illustré ci-dessus) et la désactivation de certains chiffrements faibles plus anciens. C’est la première fois que nous  supported officiellement ces modifications apportées à SCHANNEL et Crypto API sur Skype Entreprise Server, et il est important de noter que ces modifications sont les seules que nous  supportons et que nous avons testées pour le moment. Nous envisagerons peut-être des configurations supplémentaires à l’avenir, mais pour l’instant, ne modifiez pas le fichier d’importation du Registre dans votre implémentation.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Vérifier que les charges de travail fonctionnent comme prévu

Une fois que TLS 1.0 et 1.1 ont été désactivés dans votre environnement, assurez-vous que toutes vos charges de travail principales fonctionnent comme prévu, telles que la présence de & de messagerie instantanée, les appels P2P, les Voix Entreprise, etc.

**Valider que seul TLS 1.2 est utilisé**

Votre équipe de sécurité effectue un nouvel audit du trafic Skype Entreprise pour vous assurer que les anciens protocoles TLS 1.0 et 1.1 ne sont plus utilisés.

Vous pouvez également utiliser Internet Explorer pour tester les connexions TLS aux services web à partir de Skype Entreprise Server 2015 après la désactivation de TLS 1.0 et TLS 1.1.

1. Lancez Internet Explorer.
2. Sélectionnez **Outils** > **Options Internet**.
3. Sélectionnez l’onglet **Avancé**.
4. Sous **Paramètres**, faites défiler vers le bas.
5. Vérifiez que TLS 1.0, TLS 1.1 et TLS 1.2 sont activés.
6. Parcourez l’URL du service Web interne de votre pool SfB 2015 (doit se connecter correctement).
7. Revenir dans Internet Explorer et désactiver l’option d’utilisation de **TLS 1.2** uniquement.
8. Parcourez à nouveau l’URL du service Web interne de votre pool SfB 2015 (si la connexion échoue).

![Options Internet.](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Scénarios de déploiement avancés

Étant donné que certaines conditions préalables de dépendance sont requises pour prendre en charge TLS 1.2 dans Skype Entreprise Server 2015, l’installation à partir d’un support RTM échouera sur n’importe quel système où TLS 1.0 et 1.1 ont été désactivés.

**Déploiement de nouveaux serveurs Édition Standard ou pools Êdition Entreprise une fois que TLS 1.0 et 1.1 ont été désactivés dans votre environnement.**

**Option 1 :** Utilisez [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Notez que nous mettons à jour SmartSetup pour prendre en charge les binaires SQL mis à jour dans une prochaine mise à jour de mise à jour, et que nous mettons à jour cet article à l’avenir.

**Option 2 :** Préinstaller les instances SQL locales (RTCLOCAL et LYNCLOCAL)

1. Téléchargez et copiez SQL Express 2014 SP2 (SQLEXPR_x64.exe) dans le dossier local sur FE. Supposons que le chemin d’accès <SQL_FOLDER_PATH>.
2. Lancez PowerShell ou invite de commandes et accédez à <SQL_FOLDER_PATH>.
3. Créez l’instance SQL RTCLOCAL en exécutant la commande ci-dessous. Attendez que SQLEXPR_x64.exe se termine avant de poursuivre :

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="AUTORITÉNT\NetworkService » /SQLSYSADMINACCOUNTS="Builtin\Administrators » /BROWSERSVCSTARTUPTYPE="Automatic » /AGTSVCACCOUNT="NTAUTHORITY\NetworkService » /SQLSVCSTARTUPTYPE=Automati
1. Créez l’instance SQL LYNCLOCAL en exécutant la commande ci-dessous. Attendez que SQLEXPR_x64.exe se termine avant de procéder à l’étape suivante :

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService » /SQLSYSADMINACCOUNTS="Builtin\Administrators » /BROWSERSVCSTARTUPTYPE="Automatic » /AGTSVCACCOUNT="NTAUTHORITY\NetworkService » /SQLSVCSTARTUPTYPE=Automatic
1. Exécutez Skype Entreprise Server configuration RTM 2015.
2. Suivez les étapes restantes de la section prérequise ci-dessus.

**Option 3 :** Vous pouvez également remplacer manuellement les binaires dans un répertoire multimédia d’installation local comme suit :

1. [Installer les conditions préalables pour Skype Entreprise Server](../../deploy/install/install-prerequisites.md)  
2. Installez .NET 4.7 : 
      - **Remarque :** Nous avons introduit la prise en charge de .NET 4.7 dans Skype Entreprise Server CU5 2015 (6.0.9319.281). Par conséquent, dans les étapes ultérieures ci-dessous, nous mettons à jour les composants principaux avant l’installation principale.
      - Téléchargement : https://www.microsoft.com/download/details.aspx?id=55167. 
      - Référence : [logiciel à installer avant un déploiement Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiez les fichiers/dossiers ISO : 
    - Avec la Skype Entreprise Server 2015 ISO attachée, ouvrez le répertoire racine du lecteur sous le nom (Ex : D:\) dans l’Explorateur de fichiers.
    - Copiez tous les dossiers et fichiers dans un dossier sur un disque local (ex : C:\SkypeForBusiness2015ISO).
    - **Remarque :** Avant d’installer les composants, certains fichiers doivent être mis à jour pour la prise en charge de TLS 1.2.
4. Remplacez les packages MSI/EXE : 
    - Remplacez les packages MSI et EXE existants dans le dossier /Setup/amd64/ du support d’installation sur l’ordinateur local.
    - SQL 2014 SP2 Express :https://www.microsoft.com/download/details.aspx?id=53167 
        - Renommez-SQLEXPR_x64 sur l’ordinateur local et remplacez le fichier existant dans le dossier Setup/amd64/ du support d’installation.
    - SQL Native Client :https://www.microsoft.com/download/details.aspx?id=50402 
        - **Remarque :** Renommez-le si nécessaire sqlncli.msi, puis remplacez le fichier existant dans le dossier Setup/amd64/ du support d’installation.
    - SQL Management Objects :https://www.microsoft.com/download/details.aspx?id=53164 
        - **Remarque :** Le Feature Pack aura un grand nombre d’éléments qui peuvent être téléchargés. Sélectionnez pour télécharger SharedManagementObjects.msi uniquement.
        - **Remarque :** Remplacez le fichier existant qui existe dans le dossier Setup/amd64/ du support d’installation.
    - SQL types CLR :https://www.microsoft.com/download/details.aspx?id=53164 
        - **Remarque :** Le Feature Pack aura un grand nombre d’éléments qui peuvent être téléchargés. Sélectionnez pour télécharger CQLSysClrTypes.msi uniquement
        - **Remarque** : remplacez le fichier existant qui existe dans le dossier Setup/amd64/ du support d’installation.
5. Installez les composants principaux : 
    - Exécutez Setup.exe à partir du dossier Setup/amd64/ du support d’installation. Suivez les instructions pour installer les composants principaux
    - Fermez les composants principaux.
6. Mettre à jour les composants principaux : 
    - Téléchargez le programme Skype Entreprise update installer.
    - Exécutez le programme d’installation pour mettre à jour les composants principaux et installer les compteurs de performances.
    - **Remarque :** À la publication de CU6HF2, la fonctionnalité de mise à jour automatique ne s’installe actuellement que jusqu’à CU6. Par conséquent, le programme de mise à jour doit être exécuté séparément pour mettre à jour les composants principaux vers 6.0.9319.516.
    - Référence : https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Installer les outils d’administration (facultatif) : 
    - Cela installera les types Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) et Microsoft System CLR Types pour SQL Server 2014 (x64) à l’aide des fichiers mis à jour. En outre, le Skype Entreprise Server de topologie 2015 et le Panneau de contrôle seront disponibles sur l’ordinateur local.
8. Installer le magasin de configurations local (étape 1) : 
     - Ouvrez l’Assistant Déploiement, cliquez sur Installer ou mettre à jour Skype Entreprise Server système, puis cliquez  sur Exécuter à l’étape 1 : Installer le magasin de configurations local.
     - Cliquez **sur Suivant** dans la **boîte de dialogue Installer le magasin de configurations** local.
     ![Boîte de dialogue Installer le magasin de configurations local.](../../media/local-configuration-store.png)
     - Examinez les résultats et assurez-vous que l’état de la tâche est terminé. Examinez le fichier journal résultant en cliquant sur **Afficher le journal**.
     ![L’état de la tâche s’affiche comme Terminé.](../../media/local-configuration-task-completed.png)
     - Cliquez sur **Terminer**.
9. Configurer ou supprimer Skype Entreprise Server composants (étape 2) :
    - Ouvrez l’Assistant Déploiement, cliquez sur Installer ou mettre à jour **Skype Entreprise Server système**,  puis cliquez sur Exécuter à l’étape 2 : Installer ou supprimer Skype Entreprise Server composants
    - Cliquez **sur Suivant** dans la boîte de dialogue Skype Entreprise Server composants.
    ![fenêtre Configurer Skype Entreprise Server composants.](../../media/set-up-skype-for-business-server-components-window.png)
    - Consultez le journal à l’aide du journal d’affichage et validez que le programme d’installation s’est terminé sans problème. 
    - Cliquez sur **Terminer**.
10. Procédez à l’installation et à la configuration supplémentaires si nécessaire (vous pouvez reprendre les procédures d’installation normales à ce stade).