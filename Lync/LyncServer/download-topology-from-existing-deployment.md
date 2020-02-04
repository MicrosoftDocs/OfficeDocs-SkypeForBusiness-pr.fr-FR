---
title: Téléchargement de la topologie à partir d’un déploiement existant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a8bd95af99b6b79b91f84231120c6981eeedb7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="29214-102">Téléchargement de la topologie à partir d’un déploiement existant</span><span class="sxs-lookup"><span data-stu-id="29214-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29214-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="29214-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="29214-104">Lors de la création d’un pool Lync Server 2013, vous allez utiliser le magasin de gestion central associé à Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="29214-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="29214-105">Lorsque vous démarrez le générateur de topologie lors de la première utilisation et des sessions d’édition ultérieures, vous êtes invité à indiquer l’emplacement où vous voulez que le générateur de topologie charge le document de configuration actuel.</span><span class="sxs-lookup"><span data-stu-id="29214-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="29214-106">Dans la mesure où une topologie Lync Server 2010 est déjà définie et qu’elle a établi le magasin central de gestion, vous devez choisir de télécharger une topologie à partir d’un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="29214-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="29214-107">Le générateur de topologie lira la base de données et récupérera la définition actuelle.</span><span class="sxs-lookup"><span data-stu-id="29214-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="29214-108">**Pour télécharger une topologie à partir d’un déploiement existant**</span><span class="sxs-lookup"><span data-stu-id="29214-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="29214-109">Ouvrez l' **Assistant Déploiement de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="29214-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="29214-110">Dans la page **Lync Server 2013 – Assistant Déploiement** , cliquez sur **installer les outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="29214-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="29214-111">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013** , puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="29214-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="29214-112">Sélectionnez **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="29214-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="29214-113">![Paramètres du générateur de topologie de l’Assistant Déploiement](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Paramètres du générateur de topologie de l’Assistant Déploiement")</span><span class="sxs-lookup"><span data-stu-id="29214-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="29214-114">Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="29214-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="29214-115">Développez le nœud Lync Server, comme illustré, pour révéler les différents rôles serveur du déploiement.</span><span class="sxs-lookup"><span data-stu-id="29214-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="29214-116">![Propriétés générales du rôle serveur du générateur de topologie](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propriétés générales du rôle serveur du générateur de topologie")</span><span class="sxs-lookup"><span data-stu-id="29214-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

