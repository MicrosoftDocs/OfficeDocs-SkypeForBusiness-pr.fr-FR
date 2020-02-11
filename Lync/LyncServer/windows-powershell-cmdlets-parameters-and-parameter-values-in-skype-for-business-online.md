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
ms.openlocfilehash: e9fadf59b353458b2e7c48f597c11b92342e7edc
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="d9a9b-102">Cmdlets, paramètres et valeurs de paramètres Windows PowerShell dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d9a9b-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9a9b-103">_**Dernière modification de la rubrique :** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="d9a9b-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="d9a9b-104">Si vous connaissez la fenêtre de commandes dans toutes les versions de Windows (ou si vous êtes familiarisé avec l’utilisation de MS-DOS), vous serez en mesure de vous familiariser avec Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="d9a9b-105">Dans la fenêtre de commande, vous tapez une commande, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="d9a9b-106">En réponse, l’ordinateur exécute une commande ou un fichier exécutable.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="d9a9b-107">Par exemple, pour renvoyer des informations sur tous les fichiers et dossiers du répertoire actif, tapez la commande suivante à l’invite de commandes, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="d9a9b-108">En retour, vous obtenez des informations sur tous les fichiers et dossiers du répertoire actuel :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="d9a9b-109">Il s’agit d’un exemple de résultat lorsque vous tapez uniquement le nom d’une commande ou d’un fichier exécutable.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="d9a9b-110">Toutefois, la plupart des commandes exécutées à partir de la fenêtre de commande acceptent également des *arguments*.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="d9a9b-111">Les arguments sont des éléments d’informations supplémentaires transmis à la commande, qui modifient le comportement de la commande.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="d9a9b-112">Par exemple, si vous souhaitez afficher uniquement les noms des fichiers et dossiers du répertoire actif (aucune autre information, telle que la taille du fichier ou dossier), ou la date et l’heure de création du dossier ou du dossier.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="d9a9b-113">Dans ce cas, vous devez ajouter l’argument **/b** lors de l’exécution de la commande dir :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="d9a9b-114">Lorsque vous incluez l’argument **/b** , la commande **dir** renvoie uniquement les noms des dossiers et des fichiers figurant dans le répertoire actif :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="d9a9b-115">Dans la commande précédente, l’argument **/b** est la seule information requise pour limiter les données renvoyées aux noms de fichier et de dossier.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="d9a9b-116">Il s’agit souvent de commandes de ligne de commande : le simple fait de posséder un argument est qu’il est nécessaire de modifier le comportement de la commande.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="d9a9b-117">(C’est-à-dire, si vous incluez l’argument **/b** pour masquer des informations supplémentaires, ou si vous excluez l’argument **/b** pour afficher les informations supplémentaires.) En revanche, vous devez spécifier une *valeur d’argument*à d’autres moments.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="d9a9b-118">Une valeur d’argument est une information supplémentaire transmise à l’argument lui-même.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="d9a9b-119">Par exemple, l’argument **/o** vous permet de spécifier la manière dont vous voulez que la commande dir trie les données renvoyées.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="d9a9b-120">Entre autres options, vous pouvez utiliser la valeur d’argument **e** pour trier par extension de fichier ou par valeur d’argument **s** pour trier par taille de fichier.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="d9a9b-121">Par exemple, cette commande trie les données renvoyées par extension de fichier.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="d9a9b-122">Notez que la valeur d’argument **e** est incluse immédiatement après l’argument **/o** :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="d9a9b-123">À l’aide de notre exemple de dossier, les données renvoyées se présentent comme suit, et les fichiers sont triés par ordre alphabétique par extension de fichier :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="d9a9b-124">Pour vous aider à cerner exactement ce que nous parlons :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="d9a9b-125">Même si Windows PowerShell utilise une terminologie différente, l’approche de base de l’utilisation de Windows PowerShell est la même que celle de l’utilisation de la fenêtre de commande : vous tapez les commandes, vous incluez des arguments et des valeurs d’argument selon les besoins, puis vous appuyez sur entrée pour exécuter ces commandes.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="d9a9b-126">Comme indiqué, Windows PowerShell utilise toutefois une terminologie différente de celle utilisée par l’interpréteur de commandes.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="d9a9b-127">Dans Windows PowerShell, les commandes que vous exécutez sont appelées *cmdlets*.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="d9a9b-128">À son tour, les arguments transmis à une cmdlet sont appelés *paramètres*et les valeurs transmises à un paramètre sont connues sous le nom de *valeurs*de paramètres.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="d9a9b-129">Les définitions précédentes sont un peu simplifiées.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="d9a9b-130">Les applets de commande sont essentiellement des mini-applications qui ne peuvent être exécutées qu’à partir de l’environnement Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="d9a9b-131">Toutefois, vous pouvez également exécuter d’autres commandes et applications à partir de Windows PowerShell, y compris la plupart des commandes et applications qui peuvent être exécutées à partir d’une fenêtre de commande.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="d9a9b-132">Par exemple, si vous voulez démarrer le bloc-notes dans Windows PowerShell, il vous suffit de taper la commande suivante, puis d’appuyer sur entrée :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="d9a9b-133">En ce qui concerne la gestion de Skype entreprise Online, la plupart des administrateurs se fient aux cmdlets Windows PowerShell pour effectuer les tâches d’administration.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="d9a9b-134">En temps, d’autres types de commandes ou applications peuvent être utilisés pour gérer Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="d9a9b-135">Il est parfois possible d’utiliser les applets de applet Skype entreprise Online sans arguments supplémentaires (comme indiqué, les arguments sont appelés paramètres dans Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d9a9b-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="d9a9b-136">Par exemple, la commande suivante appelle l’applet de commande [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="d9a9b-137">En soi, la commande renvoie des informations sur tous les utilisateurs de Skype entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="d9a9b-138">Toutefois, la plupart des applets de commande Skype entreprise Online acceptent également des paramètres (et des valeurs de paramètres).</span><span class="sxs-lookup"><span data-stu-id="d9a9b-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="d9a9b-139">Envisagez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="d9a9b-140">Cette commande est composée de trois éléments :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="d9a9b-141">Cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="d9a9b-142">Paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-142">The Identity parameter.</span></span> <span data-ttu-id="d9a9b-143">Notez que, dans Windows PowerShell, les paramètres sont toujours précédés d’un tiret (-).</span><span class="sxs-lookup"><span data-stu-id="d9a9b-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="d9a9b-144">Cela signifie que, pour cette même applet de cmdlet, le paramètre UnassignedUser serait indiqué en utilisant la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="d9a9b-145">C’est utile de savoir, pas seulement que les paramètres doivent être précédés d’un tiret, mais également de la même façon que dans la fenêtre de commande, où les arguments sont précédés par une barre oblique (/) :</span><span class="sxs-lookup"><span data-stu-id="d9a9b-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="d9a9b-146">Valeur de paramètre **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="d9a9b-147">Cette commande renvoie une information concernant un utilisateur spécifique : l’utilisateur ayant l’identité kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d9a9b-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d9a9b-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9a9b-148">See Also</span></span>


<span data-ttu-id="d9a9b-149">[Présentation de Windows PowerShell et Skype Entreprise Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d9a9b-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

