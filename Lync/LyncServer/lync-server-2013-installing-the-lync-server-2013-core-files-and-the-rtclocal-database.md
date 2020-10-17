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
ms.openlocfilehash: fc12092e08980fcb1863b18805260ac307cc6d3d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534861"
---
# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Installation des fichiers principaux de Lync Server 2013 et de la base de données RTCLocal

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Pour installer les fichiers principaux de Lync Server 2013 sur un ordinateur, procédez comme suit. La base de données RTCLocal est installée automatiquement quand vous installez les fichiers principaux. Notez que vous n’avez pas besoin d’installer SQL Server sur les nœuds observateur. Au lieu de cela, SQL Server Express est automatiquement installé pour vous.

Pour installer les fichiers principaux de Lync Server 2013 et la base de données RTCLocal :

1.  Sur l’ordinateur sur lequel se trouve le nœud observateur, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée, en utilisant le chemin d’accès approprié à vos fichiers d’installation de Lync Server :
    
        D:\Setup.exe /BootstrapLocalMgmt

Pour vérifier que les composants principaux de Lync Server ont été correctement installés, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Lync Server 2013**, puis sur **Lync Server Management Shell**. Dans l’environnement de ligne de commande Lync Server 2013 Management Shell, tapez la commande Windows PowerShell suivante, puis appuyez sur entrée :

    Get-CsWatcherNodeConfiguration

La première fois que vous exécutez cette commande, elle ne renvoie aucune donnée, car vous n’avez encore configuré aucun nœud observateur. Tant que la commande s’exécute sans renvoyer d’erreur, vous pouvez supposer que l’installation de Lync Server a réussi.

Si votre ordinateur nœud observateur se trouve à l’intérieur de votre réseau de périmètre, vous pouvez exécuter la commande suivante pour vérifier l’installation de Lync Server 2013 :

    Get-CsPinPolicy

Vous recevrez des informations semblables aux suivantes, selon le nombre de stratégies de code confidentiel configurées dans votre organisation :

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Si des informations sur vos stratégies de code confidentiel sont affichées, cela signifie que vous avez correctement installé les composants principaux.

</div>

<span> </span>

</div>

</div>

</div>

