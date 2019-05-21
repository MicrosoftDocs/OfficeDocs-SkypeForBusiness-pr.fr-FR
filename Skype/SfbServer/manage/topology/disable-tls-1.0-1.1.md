---
title: Désactiver TLS 1.0/1.1 dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé: Préparez-vous à la désactivation de TLS 1,0 et 1,1 dans vos environnements.'
ms.openlocfilehash: 3f12642a5abf944ddbcddfdca0745998a8b634ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275240"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Désactiver TLS 1.0/1.1 dans Skype entreprise Server 2015

Dans le cadre de cet article, vous devez fournir les recommandations nécessaires pour vous préparer à la désactivation de TLS 1,0 et 1,1 dans votre environnement. Ce processus nécessite une planification et une préparation complètes. Veuillez lire attentivement toutes les informations contenues dans cet article lorsque vous planifiez la désactivation de TLS 1,0 et 1,1 pour votre organisation. Notez qu’il existe de nombreuses dépendances externes et conditions de connectivité qui peuvent être affectées en désactivant TLS 1.0/1.1, de telle sorte que la planification et le test de grande envergure se garantissent.

## <a name="in-this-article"></a>Dans cet article

- [Arrière-plan et étendue](#background)
- [Conditions préalables et processus](#prerequisites-and-process)
- [Scénarios de déploiement avancés](#advanced-deployment-scenarios)

## <a name="background"></a>Arrière-plan

Les principaux pilotes pour la mise à niveau de TLS 1,0 et 1,1 la prise en charge de Skype entreprise Server sur site sont les exigences en matière de cartes de paiement (PCI) et de Processing information standards. Pour plus d’informations sur la configuration requise pour PCI, consultez la [page suivante](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft ne peut pas vous fournir des conseils quant à la nécessité ou non que votre organisation respecte ces conditions. Vous devez déterminer s’il est nécessaire de désactiver TLS 1,0 et/ou 1,1 dans votre environnement.

Microsoft a créé un livre blanc sur TLS disponible [ici](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)et nous recommandons également la lecture en arrière-plan disponible sur ce [blog Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Étendue de la prise en charge

*Scope* fait référence aux limites de prise en charge. *Dans le cadre* de Skype entreprise Server sur site, la prise en charge totale et la désactivation de TLS 1,0 et 1,1 pour les versions de produit répertoriées sont entièrement prises en charge. Pour le moment, il n’y a *pas d’étude* ; Nous étudions activement la mise en oeuvre de ces produits pour la prise en charge de la mise à niveau de TLS. *Hors de l’objectif* signifie que ces versions de produit ne prennent pas en charge la désactivation de TLS 1,0 ou 1,1 et ne fonctionne pas, avec les exceptions indiquées.

### <a name="fully-tested-and-supported-servers"></a>Serveurs entièrement testés et pris en charge

- Skype Entreprise Server 2019
- Skype entreprise Server 2015 CU6 HF2 6.0.9319.516 ([mise à jour de mars 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) et versions ultérieures: 
    - Windows Server 2012 (avec KB 3140245 ou mise à jour de remplacement), 2012 R2 ou 2016
- Mise à niveau sur place du serveur Skype entreprise Server 2015 avec CU6 HF2 ou version ultérieure 
    - Windows Server 2008 R2, 2012 (avec KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou mise à jour de remplacement) ou 2012 R2
- Connectivité Exchange et Outlook Web App avec Exchange Server 2010 SP3 RU19 ou une version ultérieure, aide [ici](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Appareil de branchement survivant (SBA) avec Skype entreprise Server 2015 CU6 HF2 ou une version ultérieure (vérifiez auprès de votre fournisseur qu’il a mis à jour les mises à jour de votre application.)
- Serveur de succursales survivables (SBS) avec Skype entreprise Server 2015 CU6 HF2 ou version ultérieure
- Le **rôle Edge**de Lync Server 2013 uniquement, car le rôle Edge n’a pas de dépendance sur Windows Fabric 1,0.


### <a name="fully-tested-and-supported-clients"></a>Clients entièrement testés et pris en charge

- Client de bureau Lync 2013 (Skype entreprise), MSI et C2R, notamment [les numéro 15.0.5023.1000 de base et versions ultérieures](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Client de bureau 2016 de Skype entreprise, MSI [16.0.4678.1000 et versions ultérieures](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), y compris de base
- Skype entreprise 2016 Cliquer pour exécuter nécessite les mises à jour d' [avril 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Cibles mensuelles et semestrielles, 16\.0\.9126\.2152 ou version ultérieure
    - Un canal semi-annuel et un canal différé\.,\.16\.0 8431 2242 ou version ultérieure
- Skype entreprise pour Mac 16,15 et version ultérieure
- Skype entreprise pour iOS et Android 6,19 ou version ultérieure
- Skype Web App 2015 CU6 HF2 ou une version ultérieure (fournie avec le serveur)

### <a name="currently-being-investigated"></a>Examen en cours

#### <a name="devices"></a>Appareils

- Système de salle Lync (alias SRSv1)
- Salles Microsoft Teams
- Surface Hub
- Application de succursales Survivables 2015 (SBA) ou serveur de succursales Survivables (SBS)

#### <a name="other"></a>Autre

- Tableau de bord de qualité des appels (nouvelle installation après le 1,0 de TLS, 1,1 a été désactivé, voir ci-dessous) *
 
### <a name="out-of-scope"></a>Hors de l’objectif

Sauf indication contraire, les produits suivants ne peuvent pas être utilisés pour la prise en charge de TLS 1.0/1.1 et ne fonctionnent pas dans un environnement où les protocoles TLS 1,0 et 1,1 ont été désactivés.  Ce qui signifie que: Si vous utilisez toujours des serveurs ou des clients hors plage, vous devez les mettre à jour ou supprimer si vous devez désactiver TLS 1.0/1.1 n’importe où dans votre déploiement Skype entreprise Server local.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 et version antérieure
- Lync pour Mac 2011
- Lync 2013 pour mobile-iOS, iPad, Android ou Windows Phone
- Client Windows Store MX Lync
- Tous les clients Lync 2010
- Lync Phone Edition: conseils mis à jour [ici](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- Application de succursales Survivables 2013 (SBA) ou serveur de succursales Survivables (SBS)
- Édition Cloud Connector (CCE)
- Skype entreprise pour Windows Phone

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 est dépendant du Windows Fabric version 1,0.  Dans la phase de conception de Lync Server 2013, Windows Fabric 1,0 a été choisi pour sa nouvelle architecture distribuée et attrayante pour fournir une réplication, une disponibilité élevée et une tolérance de panne.  Au fil du temps, Skype entreprise Server et Windows Fabric ont considérablement amélioré cette architecture commune grâce à une nouvelle conception importante dans les versions ultérieures.  Le serveur Skype entreprise 2015 actuel utilise le Windows Fabric 3,0, par exemple.

Malheureusement, Windows Fabric 1,0 **ne prend pas en charge TLS 1,2.  Toutefois, nous allons mettre à jour Lync Server 2013 pour fonctionner avec TLS 1,2**. Cette opération sera disponible dans la prochaine mise à jour cumulative pour Lync Server 2013.  Nous proposons une prise en charge de la prise en charge des 1,2 TLS pour les scénarios de coexistence, de migration, de Fédération et hybride.

Si votre organisation est tenue de désactiver TLS 1,0 et 1,1, et que vous utilisez actuellement Lync Server 2013, nous vous conseillons de commencer le processus de planification, il est possible que vous deviez effectuer une mise à niveau sur place ou une migration côte à côte (nouveaux utilisateurs, déplacer des utilisateurs) vers Skype Business Server 2015 ou version ultérieure.  Vous pouvez également accélérer la migration vers Skype entreprise online.

#### <a name="call-quality-dashboard"></a>Tableau de bord de la qualité des appels

Le tableau de bord de qualité des appels sur site comporte actuellement une dépendance sur TLS 1,0 lors de l’installation (première utilisation dans votre environnement local).  Nous étudions actuellement ce problème et vous envisagez de publier un correctif à un avenir proche.  Si vous envisagez d’installer bord et que vous avez également désactivé TLS 1,0, nous vous recommandons de terminer d’abord l’installation d’bord, puis de procéder à la désactivation de TLS 1,0.

#### <a name="third-party-devices"></a>Appareils tiers

Sur les appareils tiers tels que les téléphones 3PIP, les conférences vidéo, les proxys inversés et les équilibreurs de charge, assurez-vous de valider la prise en charge de TLS 1,2, de tester soigneusement et de contacter le fabricant si nécessaire.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considérations relatives à la Fédération lors de la désactivation de TLS 1.0/1.1 sur les serveurs Edge

Vous devez soigneusement planifier et réfléchir à l’impact de la désactivation de TLS 1.0/1.1 sur votre serveur Edge.  Après la désactivation de TLS 1,0 et 1,1, il est possible que d’autres organisations ne soient plus en mesure de fédérer avec votre organisation.

Vous pouvez opter pour la conservation de TLS 1.0/1.1 sur votre serveur Edge pour assurer la compatibilité descendante avec les systèmes externes non corrigés (marketing 2015, Lync 2013) ou les systèmes externes plus anciens (2010).

Microsoft ne peut pas vous fournir des conseils ou des recommandations concernant l’utilisation de votre réseau Edge (ou de tout autre réseau) en standard PCI; Ce doit être déterminé par la société en particulier.

Skype entreprise Online est désormais compatible avec le protocole TLS 1,2, donc aucun impact sur l’hybride/la Fédération avec en ligne n’est attendu.

La connectivité PIC (Public IM Connectivity) au service grand public Skype: nous ne attendons pas la désactivation de TLS 1.0/1.1 pour influer sur la [connectivité Skype](../../deploy/deploy-skype-connectivity.md). Les passerelles Microsoft PIC sont déjà compatibles avec TLS 1,2.

## <a name="prerequisites-and-process"></a>Conditions préalables et processus

À l’exception des cas indiqués ci-dessus, une fois que TLS 1,0 et 1,1 ont été désactivés, les clients et les appareils fonctionneront plus correctement ou du tout. Cela signifie que vous devez patienter avant de mettre à jour les instructions de Microsoft. Lorsque vous avez terminé de répondre à toutes les exigences et que vous avez un plan de résolution des problèmes, continuez.

À un niveau élevé, lorsque Skype entreprise Server 2019 est prêt pour la procédure d’installation, Skype entreprise Server 2015 nécessite l’installation d’CU6 HF2, l’application des mises à jour requises pour .NET et SQL, le déploiement de clés de Registre prérequises et enfin d’un autre arrondi des mises à jour de configuration du système d’exploitation (par exemple, la désactivation de TLS 1,0 et 1,1 par importation de fichier de registre). Il est essentiel de procéder à l’installation de tous les éléments requis, y compris Skype entreprise Server 2015 CU6 HF2, avant de désactiver TLS 1,0 et 1,1 sur n’importe quel serveur de votre environnement. Tout Skype entreprise Server, y compris les rôles Edge et SQL end, nécessite les mises à jour. Assurez-vous également que tous les clients pris en charge (dans l’étendue) ont été mis à jour avec les versions minimales requises. N’oubliez pas non plus de mettre à jour les stations de travail de gestion.

Nous voulons suivre l’ordre habituel des opérations «à l’intérieur» pour la mise à niveau de vos serveurs Skype entreprise. Traitez les pools de réalisateurs, les discussions permanentes et les pools couplés de la même manière que dans le sens normal. L’ordre et les méthodes de mise à niveau sont abordés [ici](topology.md) et [ici](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processus de haut niveau

1. Testez toutes les étapes de votre laboratoire avant de configurer des serveurs de production.
2. Sauvegardez et conservez une copie du Registre exporté sur chaque serveur individuel à mettre à jour. Vous ne pouvez pas partager des registres entre serveurs; ils contiennent des clés basées sur un ordinateur uniques.
3. Effectuez la mise à niveau de tous les serveurs Skype entreprise 2015 vers CU6 HF2 ou version ultérieure. (Pour Skype entreprise Server 2019, aucune CU n’est nécessaire)
4. Installez toutes les conditions préalables pour tous les serveurs.
5. Déployez les clés de Registre prérequises.
6. Assurez-vous que tous les clients dans l’étendue sont mis à jour.
7. Désactivez TLS 1,0 et 1,1 par le biais de l’importation du Registre.
8. Vérifiez que les charges de travail fonctionnent comme prévu.
    - Si des problèmes sont détectés, résoudre des problèmes et résoudre ou
    - Restaurez le registre à partir de l’étape 2 pour réactiver TLS 1,0 et 1,1
9. Vérifiez que seule la 1,2 TLS est utilisée.

### <a name="install-prerequisites-to-all-servers"></a>Installer les éléments requis sur tous les serveurs

Il est nécessaire de mettre à jour les dépendances complètes avant de désactiver TLS 1,0 et 1,1 au niveau du système d’exploitation dans vos déploiements Skype entreprise Server 2015. Voici les versions minimales qui peuvent prendre en charge TLS 1,2. Déployez toutes les mises à jour prérequises pour chaque serveur Skype entreprise dans votre environnement avant de commencer à désactiver TLS 1,0 et 1,1.

- Skype entreprise Server 2015 CU6 HF2 6.0.9319.516 ([mise à jour de mars 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) ou version ultérieure
- [.NET Framework 4,7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) ou version ultérieure avec SchUseStrongCrypto activé dans le registre (fourni ci-dessous)
- SQL doit être mis à jour sur tous les serveurs et les serveurs Skype entreprise 2015. Mettez à jour les mises à jour du pool Enterprise Edition en premier, puis leurs FEs respectives. 
    - SQL Server 2014 SP1 + CU5 ([lien](https://support.microsoft.com/help/3130926)) ou version ultérieure/sql Server 2012 SP2 + CU16 ou version ultérieure/sql Server 2014 RTM + CU12 ([lien](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) ou version ultérieure/SQL Server 2014 SP2
    - Client natif SQL Server pour SQL Server 2012 ([lien](https://www.microsoft.com/en-us/download/details.aspx?id=50402))
    - Pilote ODBC Microsoft 11 pour SQL Server ([lien](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) ou version ultérieure
    - Objets de gestion partagés pour SQL Server 2014 SP2 ([lien](https://www.microsoft.com/en-in/download/details.aspx?id=42295))
    - SQLSysClrTypes pour SQL Server 2014 SP2 ([lien](https://www.microsoft.com/en-in/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Étapes de base pour l’installation des conditions préalables, dans l’ordre des opérations recommandées

1. Installez la mise à jour de Skype entreprise Server CU6HF2 (6.0.9319.516) sur tous les serveurs. 
    1. Installez la mise à jour des composants à l’aide du programme de mise à jour.
    2. Mettez à jour les bases de données en fonction de procédures détaillées. Les instructions sont documentées à l’adresse [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).
    3. Validez les fonctionnalités de produit du déploiement avant de continuer avec d’autres modifications.
2. Télécharger le programme d’installation hors connexion de .NET 4,7. 
    1. Référence[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)
    2. Vérifiez que les services 2015 de Skype entreprise Server sont arrêtés sur le serveur frontal.
    3. Référence[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (édition standard): Stop-CsWindowsServices
    5. Ex (édition entreprise): Invoke-CsComputerFailover
    6. Exécutez le package d’installation.
    7. Redémarrez le serveur.
3. Mettez à jour SQL Express 2014 sur tous les serveurs. 
    1. Référence[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Télécharger SQL 2014 SP2 
        - Référence[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)
    3. Copiez le contenu multimédia d’installation dans un dossier sur le serveur (par exemple: C:\01_2014SqlSp2).
    4. Vérifiez que les services 2015 de Skype entreprise Server sont arrêtés sur le serveur frontal 
        - Ex (édition standard): Stop-CsWindowsService
        - Ex (édition entreprise): Invoke-CsComputerFailove
    5. Ouvrez une invite de commandes d’administration et mettez à niveau tous les composants et instances installés 
        - Par exemple: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/QS/IAcceptSQLServerLicenseTerms/action = patch/AllInstances
4. Mettez à jour le client natif SQL. 
    1. Référence: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Télécharger à partir de[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)
    3. Vérifiez que les services 2015 de Skype entreprise Server sont arrêtés sur le serveur frontal. 
        - Ex (édition standard): Stop-CsWindowsServices
        - Ex (édition entreprise): Invoke-CsComputerFailove
    4. Empêcher l’exécution des instances SQL installées 
        - Par exemple: get-service’MSSQL $ RTCLOCAL' | Arrêt-service
        - Par exemple: get-service’MSSQL $ LYNCLOCAL' | Arrêt-service
        - Par exemple (édition standard uniquement): get-service’MSSQL-RTC' | Arrêt-service
    5. Installez la mise à jour.
5. Mettez à jour le pilote ODBC 11 pour SQL Server. 
    1. Référence: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Télécharger à partir de[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)
    3. Vérifiez que les services 2015 de Skype entreprise Server sont arrêtés sur le serveur frontal 
        - Ex (édition standard): Stop-CsWindowsService
        - Ex (édition entreprise): Invoke-CsComputerFailove
    4. Installez la mise à jour.
6. Déployez les clés de Registre prérequises.

### <a name="pre-requisite-registry-keys"></a>Clés de Registre préalables

Copiez/collez le test suivant dans le bloc-notes, puis renommez TLSPreReq. reg ou un nom de votre choix, puis importez les éléments suivants:

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

Pour les terminaisons SQL pour les pools d’éditions Enterprise Edition, les prérequis et la désactivation de la TLS doivent être considérés comme des mises à jour de SQL ou du système d’exploitation. reportez-vous à:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Tant que l’application requise et les étapes de désactivation de la fonction de mise en réseau TLS peuvent être combinées, nous vous recommandons vivement d’appliquer tous les éléments requis avant de procéder à la désactivation de TLS 1,0 et 1,1 au niveau du système d’exploitation. La meilleure pratique consiste à préparer l’environnement en déployant toutes les conditions préalables, en validant celle-ci de façon correcte et comme prévu, puis en poursuivant la désactivation de TLS 1.0/1.1 ultérieurement.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Désactiver TLS 1,0 et 1,1 par le biais de l’importation du Registre

Avant de passer aux étapes suivantes, assurez- *vous d’avoir rempli toutes les conditions préalables et mis à jour les serveurs Skype entreprise*.

Copiez le texte suivant dans un fichier bloc-notes, puis renommez-le **TLSDisable. reg**:

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

Importez le fichier. reg sur chaque serveur pour lequel vous souhaitez désactiver TLS 1,0 et 1,1. Redémarrez le serveur. Une fois les services reconnectés, accédez au serveur suivant. Dans le cas d’une mise à jour du système d’exploitation, l’approche pour les pools Enterprise Edition est identique.

Il est possible que vous ayez remarqué que nous ne puissions pas simplement désactiver TLS 1,0 et 1,1. Nous prenons en charge la réorganisation de la suite de chiffrement (comme illustré ci-dessus) et la désactivation de certains chiffrements faibles plus anciens. C’est la première fois que nous avons officiellement pris en charge ces modifications apportées à l’API SCHANNEL et crypto sur Skype entreprise Server, et il est important de noter que ces modifications sont les seules prises en charge et testées pour le moment. Il est possible que nous puissions envisager des configurations supplémentaires à l’avenir, mais pour l’instant, ne modifiez pas le fichier d’importation du Registre dans votre implémentation.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Valider le fonctionnement normal des charges de travail

Une fois que les protocoles TLS 1,0 et 1,1 ont été désactivés dans votre environnement, assurez-vous que l’ensemble des charges de travail principales fonctionnent comme prévu, par exemple & de messagerie instantanée, les appels P2P, voix entreprise, etc.

**Valider uniquement le 1,2 TLS est utilisé**

Faire en sorte que votre équipe de sécurité effectue un nouvel audit du trafic Skype entreprise pour s’assurer que les anciens protocoles TLS 1,0 et 1,1 ne sont plus utilisés.

Par ailleurs, vous pouvez utiliser Internet Explorer pour tester les connexions TLS aux services Web à partir de Skype entreprise Server 2015 après la désactivation de TLS 1,0 et de TLS 1,1.

1. Lancez Internet Explorer.
2. Sélectionnez **Outils** > **Options Internet**.
3. Sélectionnez l’onglet **avancé** .
4. Sous **paramètres**, faites défiler vers le bas.
5. Vérifiez que les protocoles TLS 1,0, TLS 1,1 et TLS 1,2 sont activés.
6. Parcourez l’URL du service Web interne de votre marketing 2015 (connexion réussie).
7. Revenez dans Internet Explorer et désactivez l’option d' **utilisation de TLS 1,2** uniquement.
8. Parcourez de nouveau l’URL du service Web interne de votre marketing 2015 (il est impossible de se connecter).

![Options Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Scénarios de déploiement avancés

Dans la mesure où certains éléments requis de dépendance sont requis pour la prise en charge de TLS 1,2 dans Skype entreprise ser 2015, l’installation à partir du support RTM peut échouer sur tout système sur lequel TLS 1,0 et 1,1 a été désactivé.

**Le déploiement de nouveaux serveurs Standard Edition Server ou de pools Enterprise Edition après la désactivation de TLS 1,0 et 1,1 dans votre environnement.**

**Option 1:** Utilisez [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Notez que nous mettons à jour SmartSetup pour prendre en charge les fichiers binaires SQL mis à jour dans une mise en cuivre future, et vous mettrez à jour cet article ultérieurement.

**Option 2:** Pré-installation des instances SQL locales (RTCLOCAL et LYNCLOCAL)

1. Téléchargez et copiez SQL Express 2014 SP2 (SQLEXPR_x64. exe) dans le dossier local sur FE. Par exemple, le chemin d’accès du dossier <SQL_FOLDER_PATH>.
2. Lancez PowerShell ou l’invite de commandes et accédez à <SQL_FOLDER_PATH>.
3. Créez l’instance SQL RTCLOCAL en exécutant la commande suivante. Attendez la fin de SQLEXPR_x64. exe avant de procéder comme suit:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = installer/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "AUTORITE AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "builtin \ Administrateurs "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = AUTOi
1. Créez l’instance SQL LYNCLOCAL en exécutant la commande suivante. Attendez la fin de SQLEXPR_x64. exe avant de passer à l’étape suivante:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = installer/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "AUTORITE AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "builtin \ Administrateurs "/BROWSERSVCSTARTUPTYPE =" Automatic "/AGTSVCACCOUNT =" NTAUTHORITY\NetworkService "/SQLSVCSTARTUPTYPE = Automatic
1. Exécutez le programme d’installation de Skype entreprise Server 2015 RTM.
2. Suivez les étapes restantes décrites ci-dessus.

**Option 3:** Vous pouvez également remplacer manuellement des fichiers binaires dans un répertoire d’installation local en procédant comme suit:

1. [Installer la configuration requise pour Skype entreprise Server](../../deploy/install/install-prerequisites.md)  
2. 2. Installez .NET 4,7: 
      - **Remarque:** Nous avons introduit le support pour .NET 4,7 dans Skype entreprise Server 2015 CU5 + (6.0.9319.281). Par conséquent, dans les étapes suivantes, nous allons mettre à jour les principaux composants avant l’installation principale.
      - Télécharger: https://www.microsoft.com/en-us/download/details.aspx?id=55167.
      - Référence: [logiciels qui doivent être installés avant le déploiement de Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiez les fichiers ISO/dossiers: 
    - Lorsque le fichier ISO 2015 de Skype entreprise Server est connecté, ouvrez le répertoire racine du lecteur qui lui est associé (par exemple:\) D: dans l’Explorateur de fichiers.
    - Copiez tous les dossiers et fichiers dans un dossier sur un disque local (par exemple: C:\SkypeForBusiness2015ISO).
    - **Remarque:** Avant l’installation des composants, certains fichiers devront être mis à jour pour prendre en charge le protocole TLS 1,2.
4. Remplacez les packages MSI/EXE: 
    - Remplacez les packages MSI et EXE existants dans le dossier/Setup/amd64/du support d’installation sur l’ordinateur local.
    - SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Renommez-le SQLEXPR_x64 sur l’ordinateur local et remplacez le fichier existant dans le dossier Setup/amd64/du support d’installation.
    - Client natif SQL:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Remarque:** Renommez-le si nécessaire pour sqlncli. msi, puis remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.
    - Objets de gestion SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Remarque:** Le Feature Pack dispose de nombreux éléments qui peuvent être téléchargés. Sélectionnez pour télécharger SharedManagementObjects. msi uniquement.
        - **Remarque:** Remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.
    - Types CLR SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Remarque:** Le Feature Pack dispose de nombreux éléments qui peuvent être téléchargés. Sélectionnez pour télécharger CQLSysClrTypes. msi uniquement
        - **Remarque**: remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.
5. Installer les composants principaux: 
    - Exécutez setup. exe à partir du dossier Setup/amd64/du support d’installation. Suivez les instructions pour installer les composants principaux
    - Fermez les composants principaux.
6. Mettre à jour les composants principaux: 
    - Téléchargez le programme d’installation de la mise à jour de Skype entreprise.
    - Exécutez le programme d’installation pour mettre à jour les composants principaux et installer les compteurs de performance.
    - **Remarque:** Depuis la publication de CU6HF2, la fonctionnalité de mise à jour automatique ne peut être installée que sur CU6. Par conséquent, l’outil de mise à jour doit être exécuté séparément pour mettre à jour les composants principaux sur 6.0.9319.516.
    - Référencehttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Installer les outils d’administration (facultatif): 
    - Cette opération permet d’installer le client natif Microsoft SQL Server 2012, les objets de gestion SQL Server 2014 (x64) et les types CLR du système Microsoft pour SQL Server 2014 (x64) à l’aide des fichiers mis à jour. Par ailleurs, le générateur de topologie 2015 de Skype entreprise Server et le panneau de configuration seront disponibles sur l’ordinateur local.
8. Installez le magasin de configurations local (étape 1): 
     - Ouvrez l’Assistant Déploiement, cliquez sur installer ou mettre à jour le système Skype entreprise Server, puis cliquez sur **exécuter** à l’étape 1: installer le magasin de configuration local.
     - Cliquez sur **suivant** dans la boîte de dialogue **installer le magasin de configuration local** .
     ![Boîte de dialogue installer le magasin de configuration local](../../media/local-configuration-store.png)
     - Passez en revue les résultats et assurez-vous que l’état de la tâche est terminé. Examinez le fichier journal obtenu en cliquant sur **afficher le journal**.
     ![L’état de la tâche est terminé](../../media/local-configuration-task-completed.png)
     - Cliquez sur **Terminer**.
9. Configurer ou supprimer des composants de Skype entreprise Server (étape 2):
    - Ouvrez l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, puis cliquez sur **exécuter** à l’étape 2: configurer ou supprimer des composants Skype entreprise Server
    - Cliquez sur **suivant** dans la boîte de dialogue Configurer les composants serveur Skype entreprise.
    ![fenêtre Configurer les composants de Skype entreprise Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Examinez le journal à l’aide de l’affichage du journal et confirmez que le programme d’installation s’est terminé sans problème. 
    - Cliquez sur **Terminer**.
10. Poursuivez l’installation et la configuration supplémentaires requises (vous pouvez reprendre les procédures d’installation normales à ce stade).
