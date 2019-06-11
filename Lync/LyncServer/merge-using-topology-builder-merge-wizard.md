---
title: Fusionner à l’aide de l’Assistant Fusion du générateur de topologie
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a65dab8cb99b35821f12c5871ae52f608ae344
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="71c89-102">Fusionner à l’aide de l’Assistant Fusion du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="71c89-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71c89-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="71c89-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="71c89-104">Téléchargez le déploiement existant à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="71c89-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="71c89-105">Dans le menu **action** , sélectionnez **fusionner Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="71c89-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="71c89-106">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="71c89-106">Click **Next**.</span></span>

4.  <span data-ttu-id="71c89-107">Dans **spécifier le programme d’installation**de Microsoft Edge, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="71c89-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="71c89-108">![Assistant Fusion-topologie-définir la page de configuration du bord] (images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistant Fusion-topologie-définir la page de configuration du bord")</span><span class="sxs-lookup"><span data-stu-id="71c89-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="71c89-109">Dans **spécifier le type de bord**, entrez le type de configuration de serveur Edge, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="71c89-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="71c89-110">Cet exemple utilise l’option **serveur Edge unique** .</span><span class="sxs-lookup"><span data-stu-id="71c89-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="71c89-111">Le <STRONG>déploiement Edge étendu</STRONG> n’est pas une configuration prise en charge.</span><span class="sxs-lookup"><span data-stu-id="71c89-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="71c89-112">Un <STRONG>serveur Edge étendu</STRONG> doit d’abord être converti sur un <STRONG>serveur Edge unique</STRONG> ou un serveur <STRONG>Edge consolidé équilibré</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="71c89-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="71c89-113">Dans **spécifier les paramètres de bord interne** , entrez les informations pertinentes pour le nom de domaine complet (FQDN) du pool de bords et les ports nécessaires, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="71c89-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="71c89-114">![Boîte de dialogue spécifier les paramètres de bord interne] (images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Boîte de dialogue spécifier les paramètres de bord interne")</span><span class="sxs-lookup"><span data-stu-id="71c89-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="71c89-115">Dans **spécifier le bord externe**, entrez les informations de nom de domaine complet pour les conférences Web pour votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="71c89-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="71c89-116">Avant de cliquer sur <STRONG>suivant</STRONG>, exécutez l’étape suivante de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="71c89-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="71c89-117">Il est très important que vous ne manquez pas cette étape.</span><span class="sxs-lookup"><span data-stu-id="71c89-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="71c89-118">Activez la case à cocher **ce pool Edge est utilisé pour la connectivité de Fédération et de messagerie instantanée publique** si vous envisagez d’utiliser l’ancien serveur Office Communications Server 2007 R2 pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="71c89-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="71c89-119">Si vous avez déployé plusieurs serveurs Edge, seul l’un d’eux sera activé pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="71c89-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="71c89-120">Si vous n’activez pas cette case à cocher et que vous décidez par la suite d’activer la Fédération, vous devez exécuter l’Assistant Fusion du générateur de topologie et publier de nouveau votre topologie.</span><span class="sxs-lookup"><span data-stu-id="71c89-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="71c89-121">![Boîte de dialogue serveur Edge, spécifiez la page de bord externe] (images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Boîte de dialogue serveur Edge, spécifiez la page de bord externe")</span><span class="sxs-lookup"><span data-stu-id="71c89-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="71c89-122">Dans **spécifier le tronçon suivant**, entrez le nom de domaine complet (FQDN) de l’emplacement du tronçon suivant dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="71c89-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="71c89-123">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="71c89-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="71c89-124">![Boîte de dialogue serveur Edge, page spécifier le tronçon suivant] (images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Boîte de dialogue serveur Edge, page spécifier le tronçon suivant")</span><span class="sxs-lookup"><span data-stu-id="71c89-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="71c89-125">Dans **spécifier le programme d’installation**de Microsoft Edge, si vous avez ajouté tous vos serveurs Edge Office Communications Server 2007 R2, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="71c89-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="71c89-126">Si vous avez d’autres serveurs Office Communications Server 2007 R2 à ajouter, répétez cette procédure en commençant à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="71c89-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="71c89-127">Dans **spécifier le port SIP interne** , sélectionnez le paramètre par défaut (autrement dit, si vous n’avez pas modifié le port SIP par défaut).</span><span class="sxs-lookup"><span data-stu-id="71c89-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="71c89-128">Changez le cas échéant si vous n’utilisez pas un port par défaut de 5061, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="71c89-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="71c89-129">En **Résumé**, cliquez sur **suivant** pour commencer à fusionner les topologies.</span><span class="sxs-lookup"><span data-stu-id="71c89-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="71c89-130">La page de l’Assistant vérifie que la fusion des topologies a abouti.</span><span class="sxs-lookup"><span data-stu-id="71c89-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="71c89-131">Dans la colonne **État** , assurez-vous que la valeur est **succès**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="71c89-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="71c89-132">Dans le volet gauche du générateur de topologie, vous devez maintenant voir le **BackCompatSite**, qui indique que votre environnement Office Communications Server 2007 R2 a été fusionné avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71c89-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="71c89-133">![Générateur de topologie présentant une topologie fusionnée] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Générateur de topologie présentant une topologie fusionnée")</span><span class="sxs-lookup"><span data-stu-id="71c89-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="71c89-134">Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="71c89-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="71c89-135">À la fin de l' **Assistant Publication** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="71c89-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71c89-136">Il est important que vous complétiez la rubrique suivante, importez les <A href="import-policies-and-settings.md">stratégies et paramètres</A>, pour vous assurer que les paramètres de stratégie hérités sont importés dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71c89-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

