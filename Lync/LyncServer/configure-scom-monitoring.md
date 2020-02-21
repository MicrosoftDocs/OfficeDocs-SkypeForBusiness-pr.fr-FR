---
title: Configurer la surveillance SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c83adcd4241f6a8c447265715bba26f87cc20f09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="f6a0c-102">Configurer la surveillance SCOM</span><span class="sxs-lookup"><span data-stu-id="f6a0c-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6a0c-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f6a0c-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f6a0c-104">Après avoir effectué la migration vers Microsoft Lync Server 2013, vous devez effectuer quelques tâches pour configurer Lync Server 2013 de manière à ce qu’il fonctionne avec System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="f6a0c-105">Appliquez les mises à jour de Lync Server 2010 à un serveur choisi pour gérer la logique de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="f6a0c-106">Mettez à jour la clé de Registre du serveur candidat de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="f6a0c-107">Configurez votre serveur de gestion principal de System Center Operations Manager pour remplacer le nœud de découverte centrale candidat.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="f6a0c-108">Des instructions pour mener à bien chacune de ces tâches sont fournies ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="f6a0c-109">**Appliquez les mises à jour de Lync Server 2010 à un serveur choisi pour gérer la logique de détection centrale.**</span><span class="sxs-lookup"><span data-stu-id="f6a0c-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="f6a0c-110">Choisissez un serveur sur lequel les fichiers de l’agent System Center Operations Manager sont installés et qui est configuré en tant que nœud candidat de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="f6a0c-111">Appliquez les mises à jour de Lync Server 2010 à ce serveur.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="f6a0c-112">Voir la rubrique [appliquer les mises à jour de Lync Server 2010](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="f6a0c-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="f6a0c-113">**Mettez à jour la clé de Registre du serveur candidat de détection centrale.**</span><span class="sxs-lookup"><span data-stu-id="f6a0c-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="f6a0c-114">Sur le serveur choisi pour gérer la logique de découverte centrale, ouvrez une fenêtre de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="f6a0c-115">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f6a0c-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="f6a0c-p102">À chaque modification du Registre, une erreur liée à l’échec de la commande risque de se produire si la clé de Registre existe déjà. Dans ce cas, vous pouvez ignorer cette erreur sans risque.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="f6a0c-118">**Configurez votre serveur de gestion principal de System Center Operations Manager pour remplacer le nœud du service Observateur de découverte centrale candidat.**</span><span class="sxs-lookup"><span data-stu-id="f6a0c-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="f6a0c-119">Sur un ordinateur doté de la console System Center Operations Manager, développez **Objets du pack d’administration**, puis sélectionnez **Détections d’objets**.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="f6a0c-120">Cliquez sur **Modifier l’étendue...**.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="f6a0c-121">Dans la page **Étendre les objets du pack d’administration**, sélectionnez **Candidat de détection LS**.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="f6a0c-122">Remplacez la **Valeur effective du candidat de détection LS** par le nom du serveur candidat choisi dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="f6a0c-123">Enfin, pour finaliser vos modifications, redémarrez le service de contrôle d’intégrité sur le serveur d’administration racine System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f6a0c-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

