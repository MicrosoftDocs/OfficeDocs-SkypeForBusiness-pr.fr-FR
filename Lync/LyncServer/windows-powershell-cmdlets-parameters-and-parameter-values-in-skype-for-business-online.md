---
title: Applets de commande Windows PowerShell, paramètres et valeurs de paramètres dans Skype entreprise Online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ad45c9deecf364c273ff64e939c4379d169f3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499961"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Applets de commande Windows PowerShell, paramètres et valeurs de paramètres dans Skype entreprise Online

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-05_

Si vous êtes familiarisé avec la fenêtre de commande qui se trouve dans toutes les versions de Windows (ou si vous êtes familiarisé avec MS-DOS), vous aurez un point de départ pour apprendre à utiliser Windows PowerShell. Dans la fenêtre de commande, tapez une commande, puis appuyez sur entrée. En réponse, l’ordinateur exécute une commande ou un fichier exécutable. Par exemple, pour renvoyer des informations sur tous les fichiers et dossiers du répertoire actif, tapez la commande suivante à l’invite de commandes, puis appuyez sur entrée :

```console
dir
```

Vous obtenez ensuite des informations sur tous les fichiers et dossiers du répertoire actif :

```console
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

C’est un exemple de résultat lorsque vous tapez uniquement le nom d’une commande ou d’un fichier exécutable. Toutefois, de nombreuses commandes exécutées à partir de la fenêtre de commande acceptent également des *arguments*. Les arguments sont des informations supplémentaires qui sont transmises à la commande, qui modifient le comportement de la commande. Par exemple, si vous souhaitez uniquement afficher les noms des fichiers et des dossiers dans le répertoire actif (aucune autre information, telle que la taille du fichier ou du dossier) ou la date et l’heure de création du dossier ou du dossier. Dans ce cas, vous devez ajouter l’argument **/b** lors de l’exécution de la commande dir :

```console
dir /b
```

Lorsque vous incluez l’argument **/b** , la commande **dir** renvoie uniquement les noms des dossiers et des fichiers trouvés dans le répertoire actif :

```console
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
```

Dans la commande précédente, l’argument **/b** est la seule information requise pour limiter les données renvoyées aux noms de fichier et de dossier. Cela est souvent le cas avec les commandes de ligne de commande : la seule présence d’un argument est qu’il suffit de modifier le comportement de la commande. (Autrement dit, vous devez inclure l’argument **/b** pour masquer des informations supplémentaires ou exclure l’argument **/b** pour afficher les informations supplémentaires.) Toutefois, dans d’autres cas, vous devez spécifier une *valeur d’argument*. Une valeur d’argument est une information supplémentaire transmise à l’argument lui-même. Par exemple, l’argument **/o** vous permet de spécifier la manière dont vous souhaitez que la commande dir trie les données renvoyées. Entre autres options, vous pouvez utiliser la valeur d’argument **e** pour trier par extension de fichier ou la valeur d’argument **s** pour trier par taille de fichier. Par exemple, cette commande trie les données renvoyées par extension de fichier. Notez la façon dont la valeur **e** de l’argument est incluse immédiatement après l’argument **/o** :

```console
dir /oe
```

À l’aide de notre exemple de dossier, les données renvoyées ressemblent à ce qui suit, avec les fichiers triés par extension de fichier par ordre alphabétique :

```console
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

Ou, pour vous aider à identifier exactement ce dont nous parlons :

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Bien que Windows PowerShell utilise une terminologie différente, l’approche de base de l’utilisation de Windows PowerShell est identique à celle de la fenêtre de commande : vous tapez des commandes, vous incluez des arguments et des valeurs d’argument si nécessaire, puis appuyez sur entrée pour exécuter ces commandes. Comme indiqué précédemment, Windows PowerShell utilise une terminologie différente de celle utilisée par l’interface de commande. Dans Windows PowerShell, les commandes que vous exécutez sont connues sous le nom de *cmdlets*. En retour, les arguments transmis à une cmdlet sont appelés *paramètres*et les valeurs transmises à un paramètre sont connues sous le nom de *valeurs de paramètres*.

Les définitions précédentes sont quelque peu simplifiées. Les cmdlets sont essentiellement des mini-applications qui ne peuvent être exécutées qu’au sein de l’environnement Windows PowerShell. Toutefois, vous pouvez également exécuter d’autres commandes et applications à partir de Windows PowerShell, notamment la plupart des commandes et des applications qui peuvent être exécutées à partir d’une fenêtre de commande. Par exemple, si vous souhaitez démarrer le bloc-notes dans Windows PowerShell, il vous suffit de taper la commande suivante, puis appuyez sur entrée :

```console
notepad.exe
```

Toutefois, en ce qui concerne la gestion de Skype entreprise Online, la plupart des administrateurs recourent à des applets de commande Windows PowerShell pour effectuer des tâches d’administration. Au moment, il existe très peu d’autres types de commandes ou d’applications qui peuvent être utilisés pour gérer Skype entreprise online. Parfois, les applets de commande Skype entreprise Online peuvent être utilisées sans autres arguments (, comme indiqué, les arguments sont appelés paramètres dans Windows PowerShell). Par exemple, la commande suivante appelle la cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) sans aucun paramètre supplémentaire. La commande renvoie des informations sur tous vos utilisateurs de Skype entreprise Online :

```powershell
Get-CsOnlineUser
```

Toutefois, la plupart des applets de commande Skype entreprise Online acceptent également les paramètres (et les valeurs des paramètres). Envisagez la commande suivante :

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

Cette commande se compose de trois parties :

  - La cmdlet **Get-CsOnlineUser**.

  - Paramètre Identity. Notez que, dans Windows PowerShell, les paramètres sont toujours précédés d’un tiret (-). Cela signifie que, pour cette même cmdlet, le paramètre UnassignedUser est indiqué à l’aide de la syntaxe suivante :
    
    ```powershell
    -UnassignedUser
    ```
    
    Cela est utile, non seulement parce que les paramètres doivent être précédés d’un tiret, mais également, car cela diffère de la fenêtre de commande, où les arguments sont précédés d’une barre oblique (/) :
    
    ```console
    /b
    ```

  - La valeur de paramètre **kenmyer@litwareinc.com**.

Cette commande renvoie, par invariable, les informations relatives à un utilisateur spécifique : l’utilisateur ayant l’identité kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Voir aussi


[Présentation de Windows PowerShell et de Skype entreprise Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

