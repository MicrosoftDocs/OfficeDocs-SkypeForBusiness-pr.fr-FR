---
title: Transition d’un serveur de médiation colocalisé vers un serveur de médiation autonome (facultatif)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="22938-102">Transition d’un serveur de médiation colocalisé vers un serveur de médiation autonome (facultatif)</span><span class="sxs-lookup"><span data-stu-id="22938-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22938-103">_**Dernière modification de la rubrique:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="22938-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="22938-104">Utilisez la procédure ci-dessous pour migrer votre serveur de médiation, en colocalisé sur votre serveur Standard Edition ou votre liste frontale, vers un serveur de médiation autonome pour un déploiement sur site unique.</span><span class="sxs-lookup"><span data-stu-id="22938-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="22938-105">Pour migrer un serveur de médiation colocalisé vers un serveur de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="22938-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="22938-106">Ouvrez une topologie existante à partir du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="22938-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="22938-107">Dans le volet gauche, accédez à **pools de médiation**.</span><span class="sxs-lookup"><span data-stu-id="22938-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="22938-108">Cliquez avec le bouton droit sur pools de **médiation** et sélectionnez **nouveau serveur de médiation**.</span><span class="sxs-lookup"><span data-stu-id="22938-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="22938-109">Dans la page **définir une nouvelle réserve de médiation** , indiquez le nom de domaine complet du nouveau pool de serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="22938-109">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool.</span></span> <span data-ttu-id="22938-110">Déterminez également si ce pool sera un serveur unique ou un pool multiserveur, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="22938-110">Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="22938-111">Sélectionnez le pool de serveurs front end du prochain tronçon vers lequel le nouveau serveur de médiation va diriger les appels entrants, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="22938-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="22938-112">Sélectionnez le pool de bords à utiliser par le serveur de médiation, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="22938-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="22938-113">Sur la page **Specify PSTN passerelles** , associez la passerelle RTC précédente au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="22938-113">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server.</span></span> <span data-ttu-id="22938-114">Sélectionnez la passerelle, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="22938-114">Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="22938-115">Cliquez sur **Terminer** pour fermer l’Assistant **définir un nouveau pool de médiation** .</span><span class="sxs-lookup"><span data-stu-id="22938-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="22938-116">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="22938-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="22938-117">Dans le volet **actions** , sélectionnez **publier la topologie** et terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="22938-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="22938-118">Suivez les étapes décrites dans l' [article installer les fichiers pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="22938-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="22938-119">Une fois les fichiers installés sur le serveur de médiation, revenez au générateur de topologie et dans le volet gauche, accédez au pool.</span><span class="sxs-lookup"><span data-stu-id="22938-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="22938-120">Cliquez avec le bouton droit sur la liste, puis sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="22938-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="22938-121">Sous **serveur de médiation**, décochez la case Activer le **serveur de médiation** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="22938-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="22938-122">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="22938-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="22938-123">Dans le menu **action** , sélectionnez **publier la topologie** et terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="22938-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

