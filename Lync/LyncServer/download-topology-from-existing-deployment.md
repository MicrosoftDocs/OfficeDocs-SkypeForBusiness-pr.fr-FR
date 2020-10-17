---
title: Télécharger la topologie à partir d’un déploiement existant
description: Télécharger la topologie à partir d’un déploiement existant.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22d746f8faf3fdf14a44e751eeb3c88bf3eef4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551180"
---
# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="d0756-103">Télécharger la topologie à partir d’un déploiement existant</span><span class="sxs-lookup"><span data-stu-id="d0756-103">Download topology from existing deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0756-104">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="d0756-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="d0756-105">Lors de la création d’un pool Lync Server 2013, vous utiliserez le magasin central de gestion associé à Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d0756-105">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="d0756-106">Lorsque vous démarrez le Générateur de topologies pour la première fois et lors des sessions de modification ultérieures, le système vous invite à spécifier l’emplacement où le Générateur de topologies doit charger le document de configuration actuel.</span><span class="sxs-lookup"><span data-stu-id="d0756-106">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="d0756-107">Étant donné que vous avez déjà défini une topologie Lync Server 2010 et que vous avez établi le magasin central de gestion, vous devez choisir de télécharger une topologie à partir d’un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="d0756-107">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="d0756-108">Le Générateur de topologies lit la base de données et récupère la définition actuelle.</span><span class="sxs-lookup"><span data-stu-id="d0756-108">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="d0756-109">**Pour télécharger une topologie à partir d’un déploiement existant**</span><span class="sxs-lookup"><span data-stu-id="d0756-109">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="d0756-110">Ouvrez l’**Assistant Déploiement Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d0756-110">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="d0756-111">ݸݮÀ partir de la page **Lync Server 2013 – Assistant Déploiement**, cliquez sur **Installer les outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="d0756-111">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="d0756-112">Démarrez le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013** , puis sur **Générateur de topologies Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d0756-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="d0756-113">Sélectionnez **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="d0756-113">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="d0756-114">![Paramètres du générateur de topologie de l’Assistant Déploiement](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Paramètres du générateur de topologie de l’Assistant Déploiement")</span><span class="sxs-lookup"><span data-stu-id="d0756-114">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="d0756-115">Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier .tbxml par défaut.</span><span class="sxs-lookup"><span data-stu-id="d0756-115">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="d0756-116">Développez le nœud Lync Server, comme indiqué, pour découvrir les différents rôles de serveur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="d0756-116">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="d0756-117">![Propriétés générales du rôle serveur du générateur de topologies](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propriétés générales du rôle serveur du générateur de topologies")</span><span class="sxs-lookup"><span data-stu-id="d0756-117">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

