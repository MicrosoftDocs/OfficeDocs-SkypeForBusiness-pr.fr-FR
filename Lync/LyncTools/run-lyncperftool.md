---
title: Exécuter LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daf46c5e34558a719cdf4fafa15a57f273c4030d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>Exécuter LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

Avant d’exécuter l’outil de stress et performance Lync Server 2013 (LyncPerfTool. exe), vous devez créer des utilisateurs, des contacts et des scénarios. Pour plus d’informations sur l’utilisation des outils pour effectuer ces actions, voir [créer des utilisateurs et des contacts](create-users-and-contacts.md) et [configurer le profil utilisateur](configure-user-profile.md). L’exécution de ces outils génère également un fichier qui exécute LyncPerfTool. exe dans le cadre d’un fichier de commandes avec les paramètres nécessaires inclus.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Exécution de l’outil de stress et de performance Lync Server 2013

L’outil UserProfileGenerator. exe crée un fichier de commandes qui vous permet d’exécuter LyncPerfTool. exe en inscrivant les compteurs de performance LyncPerfTool et en chargeant le fichier de configuration XML. Le fichier de commandes exécute une instance de LyncPerfTool. exe par fichier de configuration. Pour exécuter le fichier de commandes, procédez comme suit:

1.  Copiez le dossier contenant les dossiers de configuration et les fichiers dans le répertoire contenant LyncStressTool. exe sur chaque ordinateur client. Par exemple, si vous avez généré les fichiers de configuration dans le dossier nommé\_1,28 13.16.16, copiez ce dossier dans le dossier qui contient LyncPerfTool. exe sur chaque client.)

2.  Accédez au dossier client numéroté de manière appropriée et exécutez le script de commande RunClient. Il vous suffit de double-cliquer sur le fichier de commandes dans l’Explorateur Windows pour exécuter tous les fichiers de configuration pour ce numéro de client. Vous pouvez également exécuter le script à partir du dossier client approprié en utilisant la syntaxe suivante:

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Pour exécuter LyncPerfTool. exe directement, ouvrez une invite de commandes, puis tapez la commande suivante sur la ligne de commande (lorsque vous procédez ainsi pour la première fois, veillez à enregistrer les compteurs de performance regsvr32/i/n/s LyncPerfToolPerf. dll, comme illustré dans la note plus loin dans cet exemple. Topic): LyncPerfTool. exe/file:\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Pour que l’outil affiche les valeurs dans le fichier de configuration, incluez le paramètre/displayfile sur la commande précédente, comme suit:
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Pour mettre fin au processus, appuyez sur Ctrl + C.

<div>


> [!NOTE]  
> Avant d’exécuter LyncPerfTool directement, vous devez inscrire les compteurs de performance. Entrez la commande suivante pour inscrire les compteurs de performance:



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Dès lors que vous commencez à vous connecter aux utilisateurs de LyncPerfTool. exe, il est généralement possible de se connecter à un utilisateur par seconde. Le taux de connexion de l’utilisateur pointe pour le pool est d’environ 12 par seconde. Cela signifie que vous ne devez pas démarrer plus de 12 instances LyncPerfTool en même temps, tandis que les utilisateurs se connectent toujours. 1000 utilisateurs de plus de 20 minutes peuvent se connecter en une seule fois.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer des utilisateurs et des contacts](create-users-and-contacts.md)  
[Configurer un profil utilisateur](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

