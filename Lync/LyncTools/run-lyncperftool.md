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

# <a name="run-lyncperftool"></a><span data-ttu-id="2ace5-102">Exécuter LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="2ace5-102">Run LyncPerfTool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ace5-103">_**Dernière modification de la rubrique:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2ace5-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="2ace5-104">Avant d’exécuter l’outil de stress et performance Lync Server 2013 (LyncPerfTool. exe), vous devez créer des utilisateurs, des contacts et des scénarios.</span><span class="sxs-lookup"><span data-stu-id="2ace5-104">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="2ace5-105">Pour plus d’informations sur l’utilisation des outils pour effectuer ces actions, voir [créer des utilisateurs et des contacts](create-users-and-contacts.md) et [configurer le profil utilisateur](configure-user-profile.md).</span><span class="sxs-lookup"><span data-stu-id="2ace5-105">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="2ace5-106">L’exécution de ces outils génère également un fichier qui exécute LyncPerfTool. exe dans le cadre d’un fichier de commandes avec les paramètres nécessaires inclus.</span><span class="sxs-lookup"><span data-stu-id="2ace5-106">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="2ace5-107">Exécution de l’outil de stress et de performance Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ace5-107">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="2ace5-108">L’outil UserProfileGenerator. exe crée un fichier de commandes qui vous permet d’exécuter LyncPerfTool. exe en inscrivant les compteurs de performance LyncPerfTool et en chargeant le fichier de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="2ace5-108">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="2ace5-109">Le fichier de commandes exécute une instance de LyncPerfTool. exe par fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="2ace5-109">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="2ace5-110">Pour exécuter le fichier de commandes, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="2ace5-110">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="2ace5-111">Copiez le dossier contenant les dossiers de configuration et les fichiers dans le répertoire contenant LyncStressTool. exe sur chaque ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="2ace5-111">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="2ace5-112">Par exemple, si vous avez généré les fichiers de configuration dans le dossier nommé\_1,28 13.16.16, copiez ce dossier dans le dossier qui contient LyncPerfTool. exe sur chaque client.)</span><span class="sxs-lookup"><span data-stu-id="2ace5-112">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="2ace5-113">Accédez au dossier client numéroté de manière appropriée et exécutez le script de commande RunClient.</span><span class="sxs-lookup"><span data-stu-id="2ace5-113">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="2ace5-114">Il vous suffit de double-cliquer sur le fichier de commandes dans l’Explorateur Windows pour exécuter tous les fichiers de configuration pour ce numéro de client.</span><span class="sxs-lookup"><span data-stu-id="2ace5-114">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="2ace5-115">Vous pouvez également exécuter le script à partir du dossier client approprié en utilisant la syntaxe suivante:</span><span class="sxs-lookup"><span data-stu-id="2ace5-115">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="2ace5-116">Pour exécuter LyncPerfTool. exe directement, ouvrez une invite de commandes, puis tapez la commande suivante sur la ligne de commande (lorsque vous procédez ainsi pour la première fois, veillez à enregistrer les compteurs de performance regsvr32/i/n/s LyncPerfToolPerf. dll, comme illustré dans la note plus loin dans cet exemple. Topic): LyncPerfTool. exe/file:\<configXML\></span><span class="sxs-lookup"><span data-stu-id="2ace5-116">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="2ace5-117">Pour que l’outil affiche les valeurs dans le fichier de configuration, incluez le paramètre/displayfile sur la commande précédente, comme suit:</span><span class="sxs-lookup"><span data-stu-id="2ace5-117">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="2ace5-118">Pour mettre fin au processus, appuyez sur Ctrl + C.</span><span class="sxs-lookup"><span data-stu-id="2ace5-118">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ace5-119">Avant d’exécuter LyncPerfTool directement, vous devez inscrire les compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="2ace5-119">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="2ace5-120">Entrez la commande suivante pour inscrire les compteurs de performance:</span><span class="sxs-lookup"><span data-stu-id="2ace5-120">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="2ace5-121">Dès lors que vous commencez à vous connecter aux utilisateurs de LyncPerfTool. exe, il est généralement possible de se connecter à un utilisateur par seconde.</span><span class="sxs-lookup"><span data-stu-id="2ace5-121">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="2ace5-122">Le taux de connexion de l’utilisateur pointe pour le pool est d’environ 12 par seconde.</span><span class="sxs-lookup"><span data-stu-id="2ace5-122">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="2ace5-123">Cela signifie que vous ne devez pas démarrer plus de 12 instances LyncPerfTool en même temps, tandis que les utilisateurs se connectent toujours.</span><span class="sxs-lookup"><span data-stu-id="2ace5-123">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="2ace5-124">1000 utilisateurs de plus de 20 minutes peuvent se connecter en une seule fois.</span><span class="sxs-lookup"><span data-stu-id="2ace5-124">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ace5-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ace5-125">See Also</span></span>


[<span data-ttu-id="2ace5-126">Créer des utilisateurs et des contacts</span><span class="sxs-lookup"><span data-stu-id="2ace5-126">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="2ace5-127">Configurer un profil utilisateur</span><span class="sxs-lookup"><span data-stu-id="2ace5-127">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

