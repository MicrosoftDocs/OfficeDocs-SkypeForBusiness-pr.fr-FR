---
title: Configuration de la surveillance SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73bbf1ae1a487f8e6dcf8560e37cf5c7a73ba04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="251e7-102">Configuration de la surveillance SCOM</span><span class="sxs-lookup"><span data-stu-id="251e7-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="251e7-103">_**Dernière modification de la rubrique:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="251e7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="251e7-104">Après avoir effectué une migration vers Microsoft Lync Server 2013, vous devez effectuer quelques tâches pour configurer Lync Server 2013 de manière à utiliser System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="251e7-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="251e7-105">Appliquez les mises à jour de Lync Server 2010 à un serveur élu pour gérer la logique de découverte centrale.</span><span class="sxs-lookup"><span data-stu-id="251e7-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="251e7-106">Mettez à jour la clé de Registre du serveur prototype de découverte central.</span><span class="sxs-lookup"><span data-stu-id="251e7-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="251e7-107">Configurer votre serveur de gestion Operations Manager principal de System Center pour remplacer le nœud de découverte central.</span><span class="sxs-lookup"><span data-stu-id="251e7-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="251e7-108">Vous trouverez ci-dessous des instructions pour chacune de ces tâches.</span><span class="sxs-lookup"><span data-stu-id="251e7-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="251e7-109">**Appliquez les mises à jour de Lync Server 2010 à un serveur élu pour gérer la logique de découverte centrale.**</span><span class="sxs-lookup"><span data-stu-id="251e7-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="251e7-110">Électionnez un serveur sur lequel les fichiers de l’agent Operations Manager System Center Operations Manager sont installés et est configuré en tant que nœud de découverte candidat.</span><span class="sxs-lookup"><span data-stu-id="251e7-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="251e7-111">Appliquez les mises à jour de Lync Server 2010 à ce serveur.</span><span class="sxs-lookup"><span data-stu-id="251e7-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="251e7-112">Voir la rubrique [appliquer les mises à jour de Lync Server 2010](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="251e7-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="251e7-113">**Mettez à jour la clé de Registre du serveur prototype de découverte central.**</span><span class="sxs-lookup"><span data-stu-id="251e7-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="251e7-114">Sur le serveur choisi pour gérer la logique de découverte centralisée, ouvrez une fenêtre de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="251e7-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="251e7-115">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="251e7-115">At the command line, type the following:</span></span>
    
       ```
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="251e7-116">Dès lors que vous modifiez le registre, il est possible que la commande échoue si la clé de Registre existe déjà.</span><span class="sxs-lookup"><span data-stu-id="251e7-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="251e7-117">Si vous êtes à l’abri de cela, vous pouvez ignorer l’erreur.</span><span class="sxs-lookup"><span data-stu-id="251e7-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="251e7-118">**Configurez votre serveur de gestion du gestionnaire d’opérations principales pour remplacer le nœud du centre de découverte central.**</span><span class="sxs-lookup"><span data-stu-id="251e7-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="251e7-119">Sur un ordinateur sur lequel est installé la console System Center Operations Manager, développez **objets du pack d’administration** , puis sélectionnez découvertes d' **objets**.</span><span class="sxs-lookup"><span data-stu-id="251e7-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="251e7-120">Cliquez sur **modifier l’étendue...**</span><span class="sxs-lookup"><span data-stu-id="251e7-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="251e7-121">Dans la page d' **objets du pack d’administration d’étendue** , sélectionnez **ls découverte candidate**.</span><span class="sxs-lookup"><span data-stu-id="251e7-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="251e7-122">Remplacez la **valeur effective** de la fonction de découverte (LS) par le nom du serveur candidat élu dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="251e7-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="251e7-123">Enfin, pour finaliser vos modifications, redémarrez le service d’intégrité sur le serveur de gestion de racines System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="251e7-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

