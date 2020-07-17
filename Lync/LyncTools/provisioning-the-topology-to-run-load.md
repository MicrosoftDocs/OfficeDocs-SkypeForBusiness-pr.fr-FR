---
title: Mise en service de la topologie pour exécuter la charge
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3e08a66397e5c6e7fb5b6111fbdcf6d11d3632a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="4a7f3-102">Mise en service de la topologie pour exécuter la charge</span><span class="sxs-lookup"><span data-stu-id="4a7f3-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a7f3-103">_**Dernière modification de la rubrique :** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="4a7f3-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="4a7f3-104">Mise en service de la topologie pour exécuter la charge</span><span class="sxs-lookup"><span data-stu-id="4a7f3-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="4a7f3-105">En fonction de vos paramètres et de la configuration existants de Lync Server 2013, vous devrez peut-être effectuer les modifications suivantes dans votre environnement :</span><span class="sxs-lookup"><span data-stu-id="4a7f3-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="4a7f3-106">Définissez la stratégie d’exécution Windows PowerShell sur Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="4a7f3-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="4a7f3-107">Pour vérifier les paramètres de la stratégie d’exécution, ouvrez Lync Server Management Shell et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4a7f3-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="4a7f3-108">Si cette commande ne renvoie pas la valeur Unrestricted, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4a7f3-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="4a7f3-109">Pour configurer de manière efficace Lync Server 2013, vous devez :</span><span class="sxs-lookup"><span data-stu-id="4a7f3-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="4a7f3-110">Se familiariser avec la topologie Lync Server 2013 (par exemple, les noms d’ordinateur, les instances de service, les noms de site et les stratégies).</span><span class="sxs-lookup"><span data-stu-id="4a7f3-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="4a7f3-111">Affectez certains des utilisateurs qui ont été créés à des groupes, tels que les groupes de postes Response Group (par exemple, URI SIP).</span><span class="sxs-lookup"><span data-stu-id="4a7f3-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="4a7f3-112">Pour exécuter le script à partir de la ligne de commande, vous pouvez utiliser les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4a7f3-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="4a7f3-113">En règle générale, après l’exécution d’un des scripts de ce package, les traces résultantes du script sont stockées dans un fichier dans le même chemin d’accès que celui à partir duquel le script a été appelé \<scriptname\> $h $ m $s.txt.</span><span class="sxs-lookup"><span data-stu-id="4a7f3-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="4a7f3-114">Par exemple, l’exécution de ArchivingPolicy.ps1 à 12:15 P.M.</span><span class="sxs-lookup"><span data-stu-id="4a7f3-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="4a7f3-115">générera un fichier journal tel que ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="4a7f3-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="4a7f3-116">Enfin, Notez que même si nous avons fourni des exemples pour configurer le serveur, vous êtes responsable de la modification ou de la suppression de la configuration une fois le chargement terminé.</span><span class="sxs-lookup"><span data-stu-id="4a7f3-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

