---
title: Préparation pour Best Practices Analyzer et installation
TOCTitle: Préparation pour Best Practices Analyzer et installation
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg591347(v=OCS.15)
ms:contentKeyID: 49297225
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation pour Best Practices Analyzer et installation

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous devez être connecté en tant que membre du groupe Administrateurs pour pouvoir effectuer les tâches qui sont décrites dans cette rubrique.

## Configuration requise pour l’installation de l’outil Best Practices Analyzer

Pour permettre l’exécution de l’outil Best Practices Analyzer de Lync Server 2013 afin d’analyser votre environnement, l’ordinateur doit exécuter une édition 64 bits de l’un des systèmes d’exploitation suivants :

  - Windows Server 2008 R2 Standard avec Service Pack 1 (SP1)

  - Windows Server 2008 R2 Enterprise avec SP1

  - Windows Server 2008 R2 Datacenter avec SP1

  - Windows Server 2012 Datacenter

  - Windows Server 2012 Standard

  - Windows Server 2012 Enterprise

  - Système d’exploitation Windows Server 2012 R2 Datacenter

  - Système d’exploitation Windows Server 2012 R2 Standard

  - Système d’exploitation Windows Server 2012 R2 Enterprise

  - Windows 8 

  - Windows 7 

L’ordinateur doit également exécuter ce qui suit :

  - Microsoft .NET Framework 4.5. Pour Lync Server 2013, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4.5 sur le serveur avant d’installer Lync Server 2013.

  - Composants principaux de Lync Server 2013.

  - Package de compatibilité descendante WMI. Pour plus d’informations, voir [Installation du package de compatibilité descendante WMI](install-wmi-backward-compatibility-package.md) dans la documentation de migration.

  - Windows PowerShell 3.0. Pour plus d’informations, voir [Installation de Windows PowerShell 3.0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) dans la documentation de déploiement.

Vous pouvez installer l’outil Best Practices Analyzer sur les ordinateurs disposant d’un système d’exploitation pris en charge et qui n’exécutent pas les composants principaux ou le package de compatibilité descendante WMI de Lync Server 2013. Toutefois, vous ne pouvez utiliser l’outil Best Practices Analyzer sur ces ordinateurs que pour afficher des rapports, pas pour exécuter des analyses.

## Choix d’un ordinateur pour l’installation

Nous vous recommandons d’installer l’outil Best Practices Analyzer de Lync Server 2013 sur un ordinateur dédié à la gestion de Lync Server 2013. Vous pouvez installer l’outil sur un serveur exécutant Lync Server 2013 ou sur un ordinateur d’administration exécutant les outils d’administration Lync Server 2013. Si vous installez l’outil sur un serveur qui exécute Lync Server, nous vous recommandons d’utiliser l’outil pour analyser uniquement ce serveur.

## Installation de l’outil Best Practices Analyzer

Vous pouvez télécharger l’outil Best Practices Analyzer pour Lync Server 2013 à l’adresse [http://go.microsoft.com/fwlink/?linkid=266539\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=266539%26clcid=0x40c).

Pour installer l’outil Best Practices Analyzer, démarrez l’exécution du fichier d’installation Microsoft RtcBPA.msi sur l’ordinateur où vous souhaitez installer l’outil, puis suivez les instructions à l’écran. L’emplacement par défaut pour l’installation des fichiers programme est *\<lecteur\_système\>*\\Program Files\\Lync Server 2013\\BPA.

