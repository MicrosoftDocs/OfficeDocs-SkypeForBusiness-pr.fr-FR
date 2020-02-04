---
title: Cmdlets, paramètres et valeurs de paramètres Windows PowerShell dans Skype entreprise Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d607b4a7e7cf87a08082a820f3b3a216621de3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Cmdlets, paramètres et valeurs de paramètres Windows PowerShell dans Skype entreprise Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-05_

Si vous connaissez la fenêtre de commandes dans toutes les versions de Windows (ou si vous êtes familiarisé avec l’utilisation de MS-DOS), vous serez en mesure de vous familiariser avec Windows PowerShell. Dans la fenêtre de commande, vous tapez une commande, puis appuyez sur entrée. En réponse, l’ordinateur exécute une commande ou un fichier exécutable. Par exemple, pour renvoyer des informations sur tous les fichiers et dossiers du répertoire actif, tapez la commande suivante à l’invite de commandes, puis appuyez sur entrée :

    dir

En retour, vous obtenez des informations sur tous les fichiers et dossiers du répertoire actuel :

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

Il s’agit d’un exemple de résultat lorsque vous tapez uniquement le nom d’une commande ou d’un fichier exécutable. Toutefois, la plupart des commandes exécutées à partir de la fenêtre de commande acceptent également des *arguments*. Les arguments sont des éléments d’informations supplémentaires transmis à la commande, qui modifient le comportement de la commande. Par exemple, si vous souhaitez afficher uniquement les noms des fichiers et dossiers du répertoire actif (aucune autre information, telle que la taille du fichier ou dossier), ou la date et l’heure de création du dossier ou du dossier. Dans ce cas, vous devez ajouter l’argument **/b** lors de l’exécution de la commande dir :

    dir /b

Lorsque vous incluez l’argument **/b** , la commande **dir** renvoie uniquement les noms des dossiers et des fichiers figurant dans le répertoire actif :

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

Dans la commande précédente, l’argument **/b** est la seule information requise pour limiter les données renvoyées aux noms de fichier et de dossier. Il s’agit souvent de commandes de ligne de commande : le simple fait de posséder un argument est qu’il est nécessaire de modifier le comportement de la commande. (C’est-à-dire, si vous incluez l’argument **/b** pour masquer des informations supplémentaires, ou si vous excluez l’argument **/b** pour afficher les informations supplémentaires.) En revanche, vous devez spécifier une *valeur d’argument*à d’autres moments. Une valeur d’argument est une information supplémentaire transmise à l’argument lui-même. Par exemple, l’argument **/o** vous permet de spécifier la manière dont vous voulez que la commande dir trie les données renvoyées. Entre autres options, vous pouvez utiliser la valeur d’argument **e** pour trier par extension de fichier ou par valeur d’argument **s** pour trier par taille de fichier. Par exemple, cette commande trie les données renvoyées par extension de fichier. Notez que la valeur d’argument **e** est incluse immédiatement après l’argument **/o** :

    dir /oe

À l’aide de notre exemple de dossier, les données renvoyées se présentent comme suit, et les fichiers sont triés par ordre alphabétique par extension de fichier :

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

Pour vous aider à cerner exactement ce que nous parlons :

paramètre. **documentation**  
RHDSetup. **fichier**  
pldok. **Journal**

Même si Windows PowerShell utilise une terminologie différente, l’approche de base de l’utilisation de Windows PowerShell est la même que celle de l’utilisation de la fenêtre de commande : vous tapez les commandes, vous incluez des arguments et des valeurs d’argument selon les besoins, puis vous appuyez sur entrée pour exécuter ces commandes. Comme indiqué, Windows PowerShell utilise toutefois une terminologie différente de celle utilisée par l’interpréteur de commandes. Dans Windows PowerShell, les commandes que vous exécutez sont appelées *cmdlets*. À son tour, les arguments transmis à une cmdlet sont appelés *paramètres*et les valeurs transmises à un paramètre sont connues sous le nom de *valeurs*de paramètres.

Les définitions précédentes sont un peu simplifiées. Les applets de commande sont essentiellement des mini-applications qui ne peuvent être exécutées qu’à partir de l’environnement Windows PowerShell. Toutefois, vous pouvez également exécuter d’autres commandes et applications à partir de Windows PowerShell, y compris la plupart des commandes et applications qui peuvent être exécutées à partir d’une fenêtre de commande. Par exemple, si vous voulez démarrer le bloc-notes dans Windows PowerShell, il vous suffit de taper la commande suivante, puis d’appuyer sur entrée :

    notepad.exe

En ce qui concerne la gestion de Skype entreprise Online, la plupart des administrateurs se fient aux cmdlets Windows PowerShell pour effectuer les tâches d’administration. En temps, d’autres types de commandes ou applications peuvent être utilisés pour gérer Skype entreprise online. Il est parfois possible d’utiliser les applets de applet Skype entreprise Online sans arguments supplémentaires (comme indiqué, les arguments sont appelés paramètres dans Windows PowerShell). Par exemple, la commande suivante appelle l’applet de commande [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) sans aucun paramètre supplémentaire. En soi, la commande renvoie des informations sur tous les utilisateurs de Skype entreprise Online :

    Get-CsOnlineUser

Toutefois, la plupart des applets de commande Skype entreprise Online acceptent également des paramètres (et des valeurs de paramètres). Envisagez la commande suivante :

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

Cette commande est composée de trois éléments :

  - Cmdlet **Get-CsOnlineUser**.

  - Paramètre Identity. Notez que, dans Windows PowerShell, les paramètres sont toujours précédés d’un tiret (-). Cela signifie que, pour cette même applet de cmdlet, le paramètre UnassignedUser serait indiqué en utilisant la syntaxe suivante :
    
        -UnassignedUser
    
    C’est utile de savoir, pas seulement que les paramètres doivent être précédés d’un tiret, mais également de la même façon que dans la fenêtre de commande, où les arguments sont précédés par une barre oblique (/) :
    
    ```console 
    /b
    ```

  - Valeur de paramètre **kenmyer@litwareinc.com**.

Cette commande renvoie une information concernant un utilisateur spécifique : l’utilisateur ayant l’identité kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Voir aussi


[Présentation de Windows PowerShell et Skype Entreprise Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

