---
title: 'Lync Server 2013: préparation et installation des meilleures pratiques Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d1d2f86b579bfb0259c8ad3e4b26b051b47a8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Préparation de l’analyseur de meilleures pratiques et de son installation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Pour effectuer les tâches décrites dans cette rubrique, vous devez être connecté en tant que membre du groupe administrateurs.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>Configuration système requise pour l’installation de l’analyseur de meilleures pratiques

Pour exécuter Lync Server 2013, le protocole recommandé Analyzer pour analyser votre environnement, l’ordinateur doit exécuter une édition 64 bits d’un des systèmes d’exploitation suivants:

  - Système d’exploitation standard de Windows Server 2008 R2 avec Service Pack 1 (SP1)

  - Système d’exploitation Windows Server 2008 R2 avec SP1 entreprise

  - Système d’exploitation Windows Server 2008 R2 avec SP1 Datacenter

  - Système d’exploitation Windows Server 2012 Datacenter

  - Système d’exploitation Windows Server 2012 standard

  - Système d’exploitation Windows Server 2012 entreprise

  - Système d’exploitation Windows Server 2012 R2 Datacenter

  - Système d’exploitation Windows Server 2012 R2 Standard

  - Système d’exploitation Windows Server 2012 R2 entreprise

  - Système d’exploitation Windows 8

  - Système d’exploitation Windows 7

L’ordinateur doit également exécuter les éléments suivants:

  - Microsoft .NET Framework 4,5. Pour Lync Server 2013, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant de procéder à l’installation de Lync Server 2013.

  - Lync Server 2013, composants principaux.

  - Package de compatibilité descendante WMI. Pour plus d’informations, voir [installer le package de compatibilité descendante WMI](install-wmi-backward-compatibility-package.md) dans la documentation relative à la migration.

  - Windows PowerShell 3,0. Pour plus d’informations, consultez [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) dans la documentation de déploiement.

Vous pouvez installer l’outil Analyseur de meilleures pratiques sur les ordinateurs dotés d’un système d’exploitation pris en charge qui n’exécute pas Lync Server 2013, les composants principaux ou le package de compatibilité descendante WMI, mais vous pouvez utiliser l’analyseur de meilleures pratiques pour les ordinateurs uniquement pour afficher les rapports, et non pour effectuer des analyses.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Choix d’un ordinateur pour l’installation

Nous vous recommandons d’installer Lync Server 2013, le protocole recommandé Analyzer sur un ordinateur dédié à la gestion de Lync Server 2013. Vous pouvez installer l’outil sur un serveur exécutant Lync Server 2013 ou un ordinateur d’administration exécutant les outils d’administration de Lync Server 2013. Si vous installez l’outil sur un serveur exécutant Lync Server, nous vous conseillons d’utiliser l’outil pour analyser uniquement ce serveur.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Installation de l’analyseur de meilleures pratiques

Vous pouvez télécharger le recommandations Analyzer pour Lync Server 2013 à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539).

Pour installer la version recommandée de l’analyseur, démarrez le fichier Microsoft installer le fichier RtcBPA. msi sur l’ordinateur sur lequel vous souhaitez installer l’outil, puis suivez les instructions à l’écran. L’emplacement par défaut pour l’installation des fichiers \<programme est\>\\le fichier\\du programme de\\lecteur système Lync Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

