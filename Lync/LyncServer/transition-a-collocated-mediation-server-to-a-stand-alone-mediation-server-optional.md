---
title: Transition d’un serveur de médiation colocalisé à un serveur de médiation autonome (facultatif)
description: Transition d’un serveur de médiation colocalisé à un serveur de médiation autonome (facultatif).
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99eb445e8377a52901f54f52ca3933babe15571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559420"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="9d314-103">Transition d’un serveur de médiation colocalisé à un serveur de médiation autonome (facultatif)</span><span class="sxs-lookup"><span data-stu-id="9d314-103">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d314-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9d314-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9d314-105">Appliquez la procédure qui suit pour effectuer la transition de votre serveur de médiation, colocalisé sur votre serveur Standard Edition ou pool frontal, vers un serveur de médiation autonome pour un déploiement sur un seul site.</span><span class="sxs-lookup"><span data-stu-id="9d314-105">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="9d314-106">Pour passer d’un serveur de médiation colocalisé à un serveur de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="9d314-106">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="9d314-107">Ouvrez une topologie existante à partir du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9d314-107">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="9d314-108">Dans le volet gauche, naviguez jusqu’à **Pools de médiation**.</span><span class="sxs-lookup"><span data-stu-id="9d314-108">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="9d314-109">Cliquez avec le bouton droit sur **Pools de médiation**, puis cliquez sur **Nouveau serveur de médiation**.</span><span class="sxs-lookup"><span data-stu-id="9d314-109">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="9d314-p101">Dans la page **Définir un nouveau pool de médiation**, spécifiez le nom de domaine complet du nouveau pool de serveurs de médiation. Indiquez également s’il s’agit d’un pool de serveur unique ou de plusieurs serveurs, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9d314-p101">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="9d314-112">Sélectionnez le pool de serveurs frontaux du tronçon suivant vers lequel le nouveau serveur de médiation acheminera les appels entrants, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9d314-112">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="9d314-113">Sélectionnez le pool Edge que doit utiliser le serveur de médiation, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9d314-113">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="9d314-p102">Dans la page **Spécifier des passerelles PSTN**, associez la passerelle PSTN précédente au serveur de médiation. Sélectionnez la passerelle, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9d314-p102">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="9d314-116">Cliquez sur **Terminer** pour fermer l’Assistant **Définir un nouveau pool de médiation**.</span><span class="sxs-lookup"><span data-stu-id="9d314-116">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="9d314-117">Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="9d314-117">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="9d314-118">Dans le volet **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="9d314-118">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="9d314-119">Suivez les étapes décrites dans [install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="9d314-119">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="9d314-120">Une fois les fichiers installés sur le serveur de médiation, revenez dans le Générateur de topologie et, dans le volet gauche, accédez au pool.</span><span class="sxs-lookup"><span data-stu-id="9d314-120">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="9d314-121">Cliquez avec le bouton droit sur le pool et sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9d314-121">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="9d314-122">Sous **Serveur de médiation**, décochez la case **Activation de la fonctionnalité de cohabitation du serveur de médiation**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d314-122">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="9d314-123">Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="9d314-123">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="9d314-124">Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="9d314-124">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

