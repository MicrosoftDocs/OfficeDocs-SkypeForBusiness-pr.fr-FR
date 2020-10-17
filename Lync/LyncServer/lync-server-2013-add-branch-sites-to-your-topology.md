---
title: 'Lync Server 2013 : ajout de sites de succursale à votre topologie'
description: 'Lync Server 2013 : ajoutez des sites de succursale à votre topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c7a12373c6a60a2902ee451d39c99f756e2b2f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544570"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="f0d4d-103">Ajouter des sites de succursale à votre topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0d4d-103">Add branch sites to your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0d4d-104">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f0d4d-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f0d4d-p101">Les sites de succursale représentent des filiales physiques qui sont connectées à vos bureaux principaux via une liaison réseau étendu. Pour ajouter un site de succursale à votre topologie Lync, exécutez la procédure suivante sur le site central.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-p101">Branch sites represent physical branch offices that are connected to your main offices over a WAN link. To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="f0d4d-107">Pour ajouter des sites de succursale à votre topologie</span><span class="sxs-lookup"><span data-stu-id="f0d4d-107">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="f0d4d-108">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f0d4d-109">Dans l’arborescence de la console, développez le site central, cliquez avec le bouton droit sur **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-109">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="f0d4d-110">Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez le nom du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-110">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="f0d4d-111">(Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-111">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="f0d4d-112">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-112">Click **Next**.</span></span>

6.  <span data-ttu-id="f0d4d-113">(Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0d4d-113">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="f0d4d-114">Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-114">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="f0d4d-115">Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-115">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="f0d4d-116">Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-116">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="f0d4d-117">Cliquez sur **Suivant** et effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0d4d-117">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="f0d4d-118">Si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, assurez-vous que la case à cocher **ouvrir l’Assistant Nouveau Survivable Branch Assistant à la fermeture de cet Assistant** est activée, cliquez sur **Terminer**, puis suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-118">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="f0d4d-119">Pour plus d’informations sur les éléments de l’Assistant, voir [define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0d4d-119">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="f0d4d-120">Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-120">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="f0d4d-121">Répétez les étapes précédentes pour chaque site de succursale que vous souhaitez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="f0d4d-121">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="f0d4d-122">**Étape suivante :**</span><span class="sxs-lookup"><span data-stu-id="f0d4d-122">**Next step:**</span></span>

<span data-ttu-id="f0d4d-123">Pour les serveurs Survivable Branch Appliances ou serveurs Survivable Branch [Server : Define a Survivable Branch Appliance or Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="f0d4d-123">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="f0d4d-124">Pour une connectivité PSTN non résiliente : [définition d’une passerelle PSTN pour un site de succursale dans Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)ou [configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="f0d4d-124">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

