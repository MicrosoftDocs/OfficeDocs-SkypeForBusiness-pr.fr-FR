---
title: 'Lync Server 2013 : modification du diagramme de configuration réseau'
description: 'Lync Server 2013 : modification du diagramme de configuration réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead2b0b47ec0cb0a98c33d7fff0a644f05f92c71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570590"
---
# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="4896b-103">Modification du diagramme de configuration réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4896b-103">Editing the network configuration diagram in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4896b-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4896b-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4896b-105">La plupart du travail qu’un concepteur effectue dans l’outil de planification Lync Server 2013, consiste à définir les entrées des adresses IP et des noms de domaine complets (FQDN) pour les entrées sur le réseau de tâches.</span><span class="sxs-lookup"><span data-stu-id="4896b-105">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="4896b-106">Les informations qui sont entrées sur cette page sont reportées dans les rapports et les autres informations contenues dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="4896b-106">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="4896b-107">![Diagramme de réseau de l’outil de planification](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagramme de réseau de l’outil de planification")</span><span class="sxs-lookup"><span data-stu-id="4896b-107">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="4896b-108">L’outil de planification crée un diagramme de réseau avec le texte par défaut pour les adresses IP et les noms de domaine complets.</span><span class="sxs-lookup"><span data-stu-id="4896b-108">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="4896b-109">Pour modifier le diagramme de réseau et les valeurs entrées :</span><span class="sxs-lookup"><span data-stu-id="4896b-109">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="4896b-110">Choisissez la section du réseau sur laquelle vous souhaitez commencer à travailler.</span><span class="sxs-lookup"><span data-stu-id="4896b-110">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="4896b-111">Par exemple, double-cliquez sur le texte, **access1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="4896b-111">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="4896b-112">Dans la boîte de dialogue qui s’ouvre, tapez le nom de domaine complet réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant le 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="4896b-112">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="4896b-113">Cliquez sur **OK** pour enregistrer les entrées.</span><span class="sxs-lookup"><span data-stu-id="4896b-113">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="4896b-114">Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.</span><span class="sxs-lookup"><span data-stu-id="4896b-114">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="4896b-p103">Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4896b-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="4896b-117">Double-cliquez sur les serveurs frontaux du pool.</span><span class="sxs-lookup"><span data-stu-id="4896b-117">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="4896b-118">Lorsque la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.</span><span class="sxs-lookup"><span data-stu-id="4896b-118">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="4896b-119">Par exemple, la valeur de départ du premier serveur est fe0101.contoso.com et l’adresse IP 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="4896b-119">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="4896b-120">Tapez **Fe0.contoso.com** dans **nom de domaine complet du serveur frontal**, tapez **192.168.21.131** dans **adresse IP du serveur frontal**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4896b-120">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="4896b-121">La fonctionnalité d’auto-incrémentation met à jour tous les serveurs du pool vers entre FE01 via fe06 et toutes les adresses IP de 192.168.21.131 à 136.</span><span class="sxs-lookup"><span data-stu-id="4896b-121">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="4896b-122">Une fois que vous avez terminé toutes les modifications, enregistrez la topologie en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="4896b-122">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="4896b-123">Pour enregistrer la conception de l’outil de planification, cliquez sur **fichier**, puis sur **Enregistrer** la topologie ou sur **enregistrer la topologie sous**.</span><span class="sxs-lookup"><span data-stu-id="4896b-123">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="4896b-124">Si une boîte de dialogue **Enregistrer l’outil de planification sous le nom** s’affiche, tapez un nom pour le fichier dans **Nom du fichier**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4896b-124">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4896b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4896b-125">See Also</span></span>


[<span data-ttu-id="4896b-126">Modification de la conception dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4896b-126">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

