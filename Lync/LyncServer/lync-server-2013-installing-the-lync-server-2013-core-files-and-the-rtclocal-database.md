---
title: Installation des fichiers principaux de Lync Server 2013 et de la base de données RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8f0dd1fb83c595ed444a487d0321c571a09315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Installation des fichiers principaux de Lync Server 2013 et de la base de données RTCLocal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Pour installer les fichiers principaux de Lync Server 2013 sur un ordinateur, procédez comme suit. La base de données RTCLocal est automatiquement installée lors de l’installation des fichiers principaux. Notez que vous n’avez pas besoin d’installer SQL Server sur les nœuds d’observation. À la place, SQL Server Express est automatiquement installé pour vous.

Pour installer les fichiers principaux de Lync Server 2013 et la base de données RTCLocal :

1.  Sur l’ordinateur du nœud d’observation, cliquez sur **Démarrer**, sur **tous les programmes**, sur **accessoires**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée en utilisant le chemin approprié vers vos fichiers d’installation de Lync Server :
    
        D:\Setup.exe /BootstrapLocalMgmt

Pour vérifier que les composants principaux de Lync Server sont correctement installés, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Lync Server 2013**, puis sur **Lync Server Management Shell**. Dans Lync Server 2013 Management Shell, tapez la commande Windows PowerShell suivante, puis appuyez sur entrée :

    Get-CsWatcherNodeConfiguration

Lorsque vous exécutez cette commande pour la première fois, aucune donnée n’est renvoyée, car vous n’avez pas encore configuré de nœuds FileSystemWatcher. Tant que la commande est exécutée sans renvoyer d’erreur, vous pouvez supposer que le programme d’installation de Lync Server s’est terminé correctement.

Si votre ordinateur est situé à l’intérieur de votre réseau de périmètre, vous pouvez exécuter la commande suivante pour vérifier l’installation de Lync Server 2013 :

    Get-CsPinPolicy

Vous recevrez des informations similaires à ce qui suit, en fonction du nombre de stratégies de code confidentiel (PIN) configurées pour une utilisation au sein de votre organisation :

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Si vous voyez des informations relatives à vos stratégies de code confidentiel, cela signifie que vous avez correctement installé les composants principaux.

</div>

<span> </span>

</div>

</div>

</div>

