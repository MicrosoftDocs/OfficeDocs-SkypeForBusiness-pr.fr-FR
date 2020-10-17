---
title: Exécuter LyncPerfTool
description: Exécutez LyncPerfTool.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560080"
---
# <a name="run-lyncperftool"></a>Exécuter LyncPerfTool

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Avant d’exécuter l’outil stress and performance de Lync Server 2013 (LyncPerfTool.exe), vous devez créer des utilisateurs, des contacts et des scénarios. Pour plus d’informations sur l’utilisation des outils pour effectuer ces actions, consultez la rubrique [créer des utilisateurs et des contacts](create-users-and-contacts.md) et [configurer le profil utilisateur](configure-user-profile.md). L’exécution de ces outils génère également un fichier qui exécute LyncPerfTool.exe dans le cadre d’un fichier de commandes avec les paramètres requis inclus.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Exécution de l’outil de contrainte et de performances de Lync Server 2013

L’outil UserProfileGenerator.exe crée un fichier de commandes qui vous permet d’exécuter des LyncPerfTool.exe en enregistrant les compteurs de performance LyncPerfTool et en chargeant le fichier de configuration XML. Le fichier de commandes exécute une instance de LyncPerfTool.exe par fichier de configuration. Pour exécuter le fichier de commandes, procédez comme suit :

1.  Copiez le dossier qui contient les dossiers et les fichiers de configuration dans le répertoire qui contient LyncStressTool.exe sur chaque ordinateur client. (Par exemple, si vous avez généré les fichiers de configuration dans le dossier nommé 1,28 \_ 13.16.16, copiez ce dossier dans le dossier qui contient LyncPerfTool.exe sur chaque client.)

2.  Naviguez jusqu’au dossier client avec un numéro approprié et exécutez le script de commandes RunClient. Vous pouvez simplement double-cliquer sur le fichier de commandes dans l’Explorateur Windows et exécuter tous les fichiers de configuration pour ce numéro de client. Vous pouvez également exécuter le script à partir du dossier client approprié à l’aide de la syntaxe suivante :

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Pour exécuter LyncPerfTool.exe directement, ouvrez une invite de commandes, puis tapez la commande suivante dans la ligne de commande (lorsque vous effectuez cette opération pour la première fois, veillez à enregistrer les compteurs de performance regsvr32/i/n/s LyncPerfToolPerf.dll, comme indiqué dans la remarque plus loin dans cette rubrique) :LyncPerfTool.exe/file :\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Pour que l’outil affiche les valeurs dans le fichier de configuration, incluez le paramètre/displayfile sur la commande précédente, comme suit :
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Pour terminer le processus, appuyez sur Ctrl + C.

<div>


> [!NOTE]  
> Avant d’exécuter LyncPerfTool directement, vous devez enregistrer les compteurs de performance. Entrez la commande suivante pour enregistrer les compteurs de performances :



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Chaque instance de LyncPerfTool.exe que vous démarrez commence immédiatement à se connecter aux utilisateurs, généralement à une fréquence d’un utilisateur par seconde. Le taux de connexion de l’utilisateur maximal pour le pool est d’environ 12 par seconde. Cela signifie que vous ne devez pas démarrer plus de 12 instances LyncPerfTool en même temps, tandis que les utilisateurs se connectent toujours. 1000 les utilisateurs disposent d’environ 20 minutes pour se connecter complètement, un par un par seconde.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer des utilisateurs et des contacts](create-users-and-contacts.md)  
[Configurer le profil utilisateur](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

