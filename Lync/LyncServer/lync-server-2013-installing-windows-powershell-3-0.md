---
title: 'Lync Server 2013 : installation de Windows PowerShell 3,0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de45679983221d80171dde8dd37397a8b3a965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534781"
---
# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="d3b5a-102">Installation de Windows PowerShell 3,0 pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3b5a-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3b5a-103">_**Dernière modification de la rubrique :** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="d3b5a-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="d3b5a-104">Pour déployer Lync Server 2013 avec succès, vous aurez besoin de Windows PowerShell 3,0 sur chaque ordinateur qui fait partie de votre topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3b5a-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="d3b5a-105">À présent, pour les systèmes exécutant Windows Server 2012 ou Windows Server 2012 R2, vous n’avez rien à faire, et vous pouvez passer à l’étape suivante du déploiement, car PowerShell 3,0 est inclus dans ces systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="d3b5a-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3b5a-106">Toutefois, pour les systèmes exécutant Windows Server 2008 R2 SP1, vous devez installer PowerShell 3,0 comme condition préalable avant d’installer Lync Server 2013, sinon les choses ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="d3b5a-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="d3b5a-107">Pour installer PowerShell 3,0, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>.</span><span class="sxs-lookup"><span data-stu-id="d3b5a-107">To install PowerShell 3.0, see <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="d3b5a-108">Il s’agit d’un lien direct vers la page de téléchargement de PowerShell 3,0, ainsi que des informations relatives à son installation.</span><span class="sxs-lookup"><span data-stu-id="d3b5a-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="d3b5a-109">Une fois que vous avez terminé l’installation de ou si vous souhaitez simplement vérifier et vous assurer avant de poursuivre le déploiement de Lync Server, il est facile de vérifier que PowerShell 3,0 se trouve sur un serveur si vous procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3b5a-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="d3b5a-110">Sur le serveur que vous souhaitez vérifier, cliquez sur **Démarrer**, **tous les programmes**, **accessoires**, **Windows PowerShell**, puis sur **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d3b5a-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="d3b5a-111">Dans la console Windows PowerShell, tapez la commande suivante à l’invite de commandes, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="d3b5a-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="d3b5a-112">Si Windows PowerShell 3,0 est installé, la sortie ressemblera à ceci :</span><span class="sxs-lookup"><span data-stu-id="d3b5a-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

