---
title: 'Lync Server 2013 : préparation et installation de Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59bcaca40414c9bd99e451846c0339d0af6e7bf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Préparation et installation de Best Practices Analyzer dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Vous devez être connecté en tant que membre du groupe Administrateurs pour pouvoir effectuer les tâches qui sont décrites dans cette rubrique.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>Configuration requise pour l’installation de l’outil Best Practices Analyzer

Pour exécuter Lync Server 2013, Best Practices Analyzer pour analyser votre environnement, l’ordinateur doit exécuter une édition 64 bits de l’un des systèmes d’exploitation suivants :

  - Système d’exploitation Windows Server 2008 R2 avec Service Pack 1 (SP1) standard

  - Système d’exploitation Windows Server 2008 R2 avec SP1 Enterprise

  - Système d’exploitation Windows Server 2008 R2 avec SP1 Datacenter

  - Système d’exploitation Windows Server 2012 Datacenter

  - Système d’exploitation Windows Server 2012 standard

  - Système d’exploitation Windows Server 2012 Enterprise

  - Système d’exploitation Windows Server 2012 R2 Datacenter

  - Système d’exploitation Windows Server 2012 R2 Standard

  - Système d’exploitation Windows Server 2012 R2 Enterprise

  - Système d’exploitation Windows 8

  - système d’exploitation Windows 7

L’ordinateur doit également exécuter ce qui suit :

  - Microsoft .NET Framework 4.5. Pour Lync Server 2013, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant d’installer Lync Server 2013.

  - Lync Server 2013, composants principaux.

  - Package de compatibilité descendante WMI. Pour plus d’informations, consultez la rubrique [installer WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) dans la documentation de migration.

  - Windows PowerShell 3.0. Pour plus d’informations, voir [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) dans la documentation de déploiement.

Vous pouvez installer Best Practices Analyzer sur des ordinateurs avec un système d’exploitation pris en charge qui n’exécute pas Lync Server 2013, composants principaux ou un package de compatibilité descendante WMI, mais vous pouvez utiliser Best Practices Analyzer sur ces ordinateurs uniquement pour afficher les rapports, et non pour exécuter des analyses.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Choix d’un ordinateur pour l’installation

Nous vous recommandons d’installer Lync Server 2013, Best Practices Analyzer sur un ordinateur dédié à la gestion de Lync Server 2013. Vous pouvez installer l’outil sur un serveur exécutant Lync Server 2013 ou un ordinateur d’administration exécutant les outils d’administration Lync Server 2013. Si vous installez l’outil sur un serveur qui exécute Lync Server, nous vous recommandons d’utiliser l’outil pour analyser uniquement ce serveur.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Installation de l’outil Best Practices Analyzer

Vous pouvez télécharger Best Practices Analyzer pour Lync Server 2013 à l' [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539)adresse.

Pour installer l’outil Best Practices Analyzer, démarrez l’exécution du fichier d’installation Microsoft RtcBPA.msi sur l’ordinateur où vous souhaitez installer l’outil, puis suivez les instructions à l’écran. L’emplacement par défaut pour l’installation des fichiers \<programme est\>\\le lecteur\\système fichiers programme\\de Lync Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

