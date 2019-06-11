---
title: 'Lync Server 2013 : Définition et configuration d’une topologie dans le générateur de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee952eef30fc50f30448c98956899c3a1a06dc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="4d227-102">Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d227-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d227-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4d227-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4d227-104">L’exécution du générateur de topologie pour définir une nouvelle topologie ou la modification d’une topologie existante ne nécessite pas d’appartenance à un administrateur local ou à un groupe de domaine privilégié.</span><span class="sxs-lookup"><span data-stu-id="4d227-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="4d227-105">Le générateur de topologie vous guide au cours des étapes nécessaires à la définition de votre topologie pour une liste frontale Enterprise Edition ou une édition standard, en fonction de vos besoins en matière de configuration.</span><span class="sxs-lookup"><span data-stu-id="4d227-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="4d227-106">Vous devez utiliser le générateur de topologie pour achever et publier la topologie avant de pouvoir installer Lync Server 2013 sur des serveurs.</span><span class="sxs-lookup"><span data-stu-id="4d227-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="4d227-107">La procédure suivante présente les étapes nécessaires pour définir une nouvelle topologie.</span><span class="sxs-lookup"><span data-stu-id="4d227-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="4d227-108">Pour définir une topologie</span><span class="sxs-lookup"><span data-stu-id="4d227-108">To define a topology</span></span>

1.  <span data-ttu-id="4d227-109">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4d227-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4d227-110">Dans le générateur de topologie, sélectionnez **nouvelle topologie**.</span><span class="sxs-lookup"><span data-stu-id="4d227-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="4d227-111">Vous êtes invité à entrer un emplacement et un nom de fichier pour l’enregistrement de la topologie.</span><span class="sxs-lookup"><span data-stu-id="4d227-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="4d227-112">Donnez un nom significatif au fichier de topologie et acceptez l’extension par défaut de. tbxml.</span><span class="sxs-lookup"><span data-stu-id="4d227-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="4d227-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d227-113">Click **OK**.</span></span>

3.  <span data-ttu-id="4d227-114">Accédez à l’emplacement où vous voulez enregistrer le nouveau fichier XML de topologie, entrez un nom pour le fichier, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4d227-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="4d227-115">Dans la page **définir le domaine principal** , entrez le nom du domaine SIP principal de votre organisation, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4d227-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="4d227-116">Dans la page **spécifier d’autres domaines pris en charge** , entrez le nom des domaines supplémentaires, le cas échéant, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4d227-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="4d227-117">Dans la page **définir le premier site** , entrez un nom et une description pour le premier site, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4d227-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="4d227-118">Dans la page **spécifier les détails du site** , entrez les informations d’emplacement du site, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4d227-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="4d227-119">Dans la page **nouvelle topologie définie avec succès** , assurez-vous que la case à cocher **ouvrir l’Assistant Nouveau serveur frontal à la fermeture de cet Assistant** est activée, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4d227-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="4d227-120">Une fois que vous avez défini et enregistré la topologie, utilisez le nouvel Assistant frontal pour définir un pool frontal ou un serveur Standard Edition Server pour votre site.</span><span class="sxs-lookup"><span data-stu-id="4d227-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="4d227-121">Pour plus d’informations, reportez-vous à [la section définir et configurer un pool frontal ou un serveur Standard Edition Server dans Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="4d227-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

