---
title: 'Lync Server 2013 : mise à jour à partir de la version d’évaluation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 703362f34c367d301e7d47e1bdc65f16a497ce88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="01883-102">Mise à jour à partir de la version d’évaluation de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01883-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01883-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="01883-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="01883-104">Si vous avez installé la version d’évaluation de Microsoft Lync Server 2013, vous aurez peut-être besoin de mettre à jour cette installation en tant que copie sous licence du logiciel ; Cela est dû au fait que la version d’évaluation expire 180 jours après son installation.</span><span class="sxs-lookup"><span data-stu-id="01883-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="01883-105">Toutefois, vous ne devrez pas désinstaller complètement la version d’évaluation, puis installer la version sous licence.</span><span class="sxs-lookup"><span data-stu-id="01883-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="01883-106">Au lieu de cela, une fois que vous avez obtenu une clé de licence valide, vous pouvez mettre à jour la version d’évaluation de Lync Server 2013 en exécutant la procédure suivante sur chaque ordinateur jouant le rôle de serveur frontal, directeur ou serveur Edge Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01883-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="01883-107">Il n’est pas nécessaire de mettre à jour les ordinateurs ayant d’autres rôles serveur, tels qu’un serveur de surveillance ou un serveur d’archivage.</span><span class="sxs-lookup"><span data-stu-id="01883-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="01883-108">Mise à jour à partir de la version d’évaluation de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01883-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="01883-109">Pour mettre à jour un ordinateur à partir de la version d’évaluation de Lync Server 2013 vers la version sous licence du logiciel, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="01883-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="01883-110">**Mise à jour à partir de la version d’évaluation de Microsoft Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="01883-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="01883-111">Ouvrez une session sur l’ordinateur en tant qu’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="01883-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="01883-112">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="01883-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="01883-113">Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="01883-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="01883-114">Il se peut que vous deviez spécifier le chemin d’accès complet au fichier server.msi.</span><span class="sxs-lookup"><span data-stu-id="01883-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="01883-115">Ce fichier se trouve dans le dossier Setup des fichiers d’installation des médias de volume Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01883-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="01883-116">Une fois l’installation terminée, tapez la commande suivante depuis l’invite de commande, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="01883-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="01883-117">Répétez cette procédure sur tout autre serveur frontal, directeur ou serveur Edge exécutant une copie d’évaluation de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01883-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="01883-118">Cette procédure doit également être exécutée sur les serveurs de succursale déployés à l’aide des fichiers d’installation multimédia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01883-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="01883-119">Si vous n’êtes pas certain que la version d’évaluation de Lync Server est en cours d’exécution sur un ordinateur donné, vous pouvez vérifier qu’en exécutant la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="01883-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="01883-120">L’applet de commande [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analyse l’ordinateur local et spécifie les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="01883-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="01883-121">Que la clé de licence en volume Lync Server a été installée sur l’ordinateur, ce qui signifie qu’aucune mise à jour n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="01883-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="01883-122">Que la clé de licence d’évaluation Lync Server a été installée, ce qui signifie que l’ordinateur doit être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="01883-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="01883-p104">Aucune clé de licence en volume n’est requise sur l’ordinateur. La mise à jour de la version d’évaluation vers la version sous licence est uniquement nécessaire sur les serveurs frontaux, les directeurs et les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="01883-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

