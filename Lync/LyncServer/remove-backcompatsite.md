---
title: Supprimer BackCompatSite
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 792fcf29033a7495a7da340decb561e25084612d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="0b05c-102">Supprimer BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="0b05c-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b05c-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0b05c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0b05c-104">Une fois tous les pools désactivés et tous les serveurs Edge désinstallés, exécutez l’Assistant Fusion du Générateur de topologie pour supprimer **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="0b05c-105">Pour supprimer le site BackCompat à partir du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="0b05c-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="0b05c-106">Ouvrez un déploiement existant à partir du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="0b05c-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="0b05c-107">Dans le menu **Actions**, cliquez sur **Fusionner la topologie 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="0b05c-108">Cliquez sur **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="0b05c-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="0b05c-p101">Dans la page **Spécifier la configuration Edge héritée**, vérifiez que la liste des serveurs Edge est vide. Si elle ne l’est pas, utilisez le bouton **Supprimer** pour supprimer tous les serveurs Edge hérités, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-p101">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="0b05c-111">![Assistant fusion de topologies, spécifier la page Configuration du serveur Edge](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistant fusion de topologies, spécifier la page Configuration du serveur Edge")</span><span class="sxs-lookup"><span data-stu-id="0b05c-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="0b05c-112">Dans la page **Spécifier le port SIP interne**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="0b05c-113">Sur la page **Résumé** , cliquez sur **suivant** pour commencer à fusionner les topologies afin de supprimer le site hérité.</span><span class="sxs-lookup"><span data-stu-id="0b05c-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="0b05c-114">Dans la colonne **Statut**, vérifiez que la valeur est **Opération réussie**, puis cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="0b05c-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="0b05c-115">Dans le volet de gauche du Générateur de topologie, développez BackCompatSite et vérifiez qu’aucun serveur n’est répertorié.</span><span class="sxs-lookup"><span data-stu-id="0b05c-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="0b05c-116">Cliquez avec le bouton droit sur **BackCompatSite**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="0b05c-117">Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="0b05c-118">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0b05c-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="0b05c-119">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="0b05c-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

