---
title: Fusion à l’aide de l’Assistant Fusion du générateur de topologie
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="41b01-102">Fusion à l’aide de l’Assistant Fusion du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="41b01-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41b01-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="41b01-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="41b01-104">Téléchargez le déploiement existant à l’aide du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="41b01-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="41b01-105">Dans le menu **Action**, sélectionnez **Fusionner Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="41b01-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="41b01-106">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="41b01-106">Click **Next**.</span></span>

4.  <span data-ttu-id="41b01-107">Dans **Spécifier la configuration Edge**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="41b01-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="41b01-108">![Assistant fusion de topologies, spécifier la page Configuration du serveur Edge](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistant fusion de topologies, spécifier la page Configuration du serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="41b01-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="41b01-p101">Dans **Spécifier le type Edge**, entrez le type de configuration du serveur Edge, puis cliquez sur **Suivant**. Cet exemple utilise l’option **Serveur Edge unique**.</span><span class="sxs-lookup"><span data-stu-id="41b01-p101">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**. This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41b01-p102">Un déploiement <STRONG>Edge étendu</STRONG> n’est pas une configuration prise en charge. Un serveur <STRONG>Edge étendu</STRONG> doit d’abord être converti en <STRONG>serveur Edge unique</STRONG> ou <STRONG>Edge consolidé à charge équilibrée</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="41b01-p102"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration. An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="41b01-113">Dans **spécifier les paramètres Edge internes** , entrez les informations pertinentes pour le nom de domaine complet interne et les ports du pool Edge si nécessaire, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="41b01-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="41b01-114">![Boîte de dialogue spécifier les paramètres Edge internes](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Boîte de dialogue spécifier les paramètres Edge internes")</span><span class="sxs-lookup"><span data-stu-id="41b01-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="41b01-115">Dans **Spécifier la configuration Edge externe**, entrez les informations relatives au nom de domaine complet (FQDN) pour votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="41b01-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41b01-p103">Avant de cliquer sur <STRONG>Suivant</STRONG>, effectuez l’étape suivante de cette procédure. Il est très important que vous ne manquiez pas cette étape 11.</span><span class="sxs-lookup"><span data-stu-id="41b01-p103">Before you click <STRONG>Next</STRONG>, do the next step in this procedure. It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="41b01-118">Activez la case à cocher **ce pool Edge est utilisé pour la Fédération et la connectivité PIC** si vous envisagez d’utiliser le serveur Edge Office Communications Server 2007 R2 hérité pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="41b01-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="41b01-119">Si vous avez plusieurs serveurs Edge déployés, un seul d’entre eux est alors activé pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="41b01-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="41b01-120">Si vous ne cochez pas cette case et que vous décidez d’activer plus tard une fédération, vous devez réexécuter l’Assistant Fusion du Générateur de topologie et republier votre topologie.</span><span class="sxs-lookup"><span data-stu-id="41b01-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="41b01-121">![Boîte de dialogue serveur Edge, spécifier la page Edge externe](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Boîte de dialogue serveur Edge, spécifier la page Edge externe")</span><span class="sxs-lookup"><span data-stu-id="41b01-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="41b01-122">Dans **Spécifier le tronçon suivant**, entrez le nom de domaine complet (FQDN) de l’emplacement du tronçon suivant dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="41b01-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="41b01-123">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="41b01-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="41b01-124">![Boîte de dialogue serveur Edge, spécifier la page du tronçon suivant](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Boîte de dialogue serveur Edge, spécifier la page du tronçon suivant")</span><span class="sxs-lookup"><span data-stu-id="41b01-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="41b01-125">Dans **spécifier la configuration Edge**, si tous vos serveurs Edge Office Communications Server 2007 R2 ont été ajoutés, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="41b01-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="41b01-126">Si vous avez d’autres serveurs Edge Office Communications Server 2007 R2 à ajouter, répétez cette procédure en commençant à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="41b01-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="41b01-127">Dans **spécifier le port SIP interne** , sélectionnez le paramètre par défaut (autrement dit, si vous n’avez pas modifié le port SIP par défaut).</span><span class="sxs-lookup"><span data-stu-id="41b01-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="41b01-128">Au besoin, effectuez la modification si le port par défaut n’est pas 5061, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="41b01-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="41b01-129">Dans **Sommaire**, cliquez sur **Suivant** pour commencer à fusionner les topologies.</span><span class="sxs-lookup"><span data-stu-id="41b01-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="41b01-130">La page de l’Assistant vérifie que la fusion des topologies a réussi.</span><span class="sxs-lookup"><span data-stu-id="41b01-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="41b01-131">Dans la colonne **Statut**, vérifiez que la valeur est **Opération réussie**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="41b01-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="41b01-132">Dans le volet gauche du générateur de topologie, vous devez maintenant voir la **BackCompatSite**, qui indique que votre environnement Office Communications Server 2007 R2 a été fusionné avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41b01-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="41b01-133">![Générateur de topologies affichant une topologie fusionnée](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Générateur de topologies affichant une topologie fusionnée")</span><span class="sxs-lookup"><span data-stu-id="41b01-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="41b01-134">Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="41b01-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="41b01-135">Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="41b01-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41b01-136">Il est important que vous terminiez la rubrique suivante, <A href="import-policies-and-settings.md">importer des stratégies et des paramètres</A>pour vous assurer que les paramètres de stratégie hérités sont importés dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41b01-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

