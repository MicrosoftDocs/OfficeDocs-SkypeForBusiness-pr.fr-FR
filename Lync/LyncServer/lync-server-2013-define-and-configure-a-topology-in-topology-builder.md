---
title: 'Lync Server 2013 : définition et configuration d’une topologie dans le générateur de topologies'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3877b19bac01991856313302378c92065bacf22
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="64846-102">Définition et configuration d’une topologie dans le générateur de topologies pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64846-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64846-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="64846-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="64846-104">L’exécution du générateur de topologie pour définir une nouvelle topologie ou la modification d’une topologie existante ne nécessite pas l’appartenance à un administrateur local ou à un groupe de domaines privilégiés.</span><span class="sxs-lookup"><span data-stu-id="64846-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="64846-105">Le générateur de topologies vous guide tout au long des étapes nécessaires à la définition de votre topologie pour un pool frontal Enterprise Edition ou une édition standard, en fonction de vos besoins de configuration.</span><span class="sxs-lookup"><span data-stu-id="64846-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="64846-106">Vous devez utiliser le générateur de topologies pour terminer et publier la topologie avant de pouvoir installer Lync Server 2013 sur des serveurs.</span><span class="sxs-lookup"><span data-stu-id="64846-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="64846-107">La procédure suivante inclut les étapes nécessaires à la définition d’une nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="64846-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="64846-108">Pour définir une topologie</span><span class="sxs-lookup"><span data-stu-id="64846-108">To define a topology</span></span>

1.  <span data-ttu-id="64846-109">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="64846-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="64846-110">Dans le générateur de topologies, sélectionnez **nouvelle topologie**.</span><span class="sxs-lookup"><span data-stu-id="64846-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="64846-111">Vous êtes invité à indiquer un emplacement et un nom de fichier pour l’enregistrement de la topologie.</span><span class="sxs-lookup"><span data-stu-id="64846-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="64846-112">Donnez un nom significatif au fichier de topologie et acceptez l’extension par défaut. tbxml.</span><span class="sxs-lookup"><span data-stu-id="64846-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="64846-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64846-113">Click **OK**.</span></span>

3.  <span data-ttu-id="64846-114">Naviguez jusqu’à l’emplacement où vous souhaitez enregistrer le nouveau fichier XML de topologie, entrez un nom pour le fichier, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="64846-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="64846-115">Dans la page **définir le domaine principal** , entrez le nom du domaine SIP principal de votre organisation, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="64846-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="64846-116">Sur la page **spécifier d’autres domaines pris en charge** , entrez les noms des domaines supplémentaires, le cas échéant, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="64846-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="64846-117">Dans la page **définir le premier site** , entrez un nom et une description pour le premier site, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="64846-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="64846-118">Sur la page **spécifier les détails du site** , entrez les informations d’emplacement du site, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="64846-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="64846-119">Sur la page **nouvelle topologie correctement définie** , vérifiez que la case à cocher **ouvrir l’Assistant Nouveau serveur frontal à la fermeture de cet Assistant** est activée, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="64846-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="64846-120">Une fois que vous avez défini et enregistré la topologie, utilisez l’Assistant Nouveau serveur frontal pour définir un pool frontal ou un serveur Standard Edition pour votre site.</span><span class="sxs-lookup"><span data-stu-id="64846-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="64846-121">Pour plus d’informations, reportez-vous à [la rubrique define and Configure a front end pool or Standard Edition Server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="64846-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

