---
title: 'Lync Server 2013 : installation des composants de Lync Server Server'
description: 'Lync Server 2013 : installation des composants de Lync Server Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1930926f3a46be868d838abf646eb8702c9713a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574120"
---
# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="68b16-103">Installer les composants serveur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68b16-103">Install server components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68b16-104">_**Dernière modification de la rubrique :** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="68b16-104">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="68b16-105">Avant de suivre cette procédure, assurez-vous que vous êtes connecté au serveur avec un compte d’utilisateur de domaine qui est à la fois un administrateur local et un membre du groupe RTCUniversalReadOnlyAdmins dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68b16-105">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="68b16-106">L’Assistant Déploiement de Lync Server est utilisé pour installer les composants nécessaires pour chaque rôle Lync Server et pour activer le serveur.</span><span class="sxs-lookup"><span data-stu-id="68b16-106">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="68b16-107">Cet article vous guide tout au long de la procédure de déploiement d’un serveur Standard Edition ou d’un serveur frontal dans votre infrastructure Lync.</span><span class="sxs-lookup"><span data-stu-id="68b16-107">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="68b16-108">Pour installer les composants Lync Server</span><span class="sxs-lookup"><span data-stu-id="68b16-108">To install Lync Server components</span></span>

1.  <span data-ttu-id="68b16-109">Si l’Assistant Déploiement de Lync Server n’est pas en cours d’exécution, démarrez-le sur le serveur sur lequel vous souhaitez installer Lync.</span><span class="sxs-lookup"><span data-stu-id="68b16-109">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="68b16-110">Cliquez sur **installer ou mettre à jour le système Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="68b16-110">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="68b16-111">Dans l’Assistant Déploiement, vérifiez que l' **étape 1 : installer le magasin de configurations local** a une coche verte, ce qui signifie que ce serveur a une copie locale de la banque installée.</span><span class="sxs-lookup"><span data-stu-id="68b16-111">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="68b16-112">Si ce n’est pas déjà fait, vous devez installer le magasin de configurations local sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="68b16-112">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="68b16-113">Suivez les étapes décrites [dans Install the local Configuration Store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) , puis revenez ici.</span><span class="sxs-lookup"><span data-stu-id="68b16-113">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="68b16-114">Lorsque vous êtes prêt à installer les composants Lync Server 2013 sur votre serveur, cliquez sur **exécuter** à côté de **étape 2 : installer ou supprimer des composants Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="68b16-114">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="68b16-115">Dans la page **configurer les composants Lync Server** , cliquez sur **suivant** pour configurer les composants comme défini dans votre topologie publiée.</span><span class="sxs-lookup"><span data-stu-id="68b16-115">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="68b16-116">La page **exécution de commandes** affiche un résumé des commandes et des informations d’installation à mesure que la configuration a lieu.</span><span class="sxs-lookup"><span data-stu-id="68b16-116">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="68b16-117">Une fois cette opération terminée, vous pouvez sélectionner un journal à afficher dans la liste, puis cliquer sur **afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="68b16-117">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="68b16-118">Lorsque le programme d’installation des composants Lync Server 2013 est terminé et que vous avez examiné les journaux selon vos besoins, cliquez sur **Terminer** pour effectuer cette étape dans l’installation.</span><span class="sxs-lookup"><span data-stu-id="68b16-118">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68b16-119">Si vous êtes invité à redémarrer le serveur (ce qui peut se produire si l’expérience de bureau Windows devait être installée), faites-le.</span><span class="sxs-lookup"><span data-stu-id="68b16-119">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="68b16-120">Lorsque l’ordinateur est en cours d’exécution, vous devez effectuer les opérations suivantes de nouveau, en commençant à l’étape 3 ci-dessus (exécutez l’étape 2 de l’Assistant Déploiement une fois de plus).</span><span class="sxs-lookup"><span data-stu-id="68b16-120">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

