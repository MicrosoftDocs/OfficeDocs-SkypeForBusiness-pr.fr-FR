---
title: 'Lync Server 2013 : Installation de la base de données de serveur Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="9e3fe-102">Installation de la base de données de serveur Standard Edition pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e3fe-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e3fe-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9e3fe-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9e3fe-104">La configuration d’un serveur Standard Edition Server en tant que serveur unique dans votre infrastructure qui est identique à celle d’autres installations de serveur dans le cadre de l' **Assistant Déploiement** est une sélection spécifique à la configuration du serveur initial.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="9e3fe-105">Pour installer un serveur Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="9e3fe-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="9e3fe-106">Ouvrez une session sur le serveur sur lequel vous allez installer Standard Edition Server en tant qu’administrateur local ou un domaine équivalent.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="9e3fe-107">Si vous n’avez pas encore préparé les services de domaine Active Directory, vous devez d’abord effectuer ces procédures.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="9e3fe-108">Pour plus d’informations, consultez [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="9e3fe-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="9e3fe-109">Dans l’Assistant Déploiement de Lync Server, cliquez sur **préparer le premier serveur Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="9e3fe-110">Sur la page **préparer Single Standard Edition Server** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="9e3fe-111">Sur la page **exécution des commandes** , SQL Server 2012 Express est installé en tant que magasin de gestion centrale.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="9e3fe-112">Des règles de pare-feu nécessaires sont créées.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="9e3fe-113">Lorsque l’installation de la base de données et du logiciel requis est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e3fe-114">L’installation initiale risque de prendre un certain temps sans qu’aucune mise à jour ne s’affiche à l’écran de synthèse de la sortie de commande.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="9e3fe-115">Le problème est dû à l’installation de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="9e3fe-116">Si vous avez besoin de surveiller l’installation de la base de données, utilisez le gestionnaire des tâches pour contrôler la configuration.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="9e3fe-117">Dans la page Assistant Déploiement de Lync Server, cliquez sur **installer le générateur de topologie** si vous n’avez pas encore installé les outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="9e3fe-118">Pour en savoir plus, voir [installer les outils d’administration de Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9e3fe-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="9e3fe-119">Vérifiez que la case à cocher «préparer Active Directory» et «préparer le premier serveur Standard Edition» et «installer le générateur de topologie» est activée.</span><span class="sxs-lookup"><span data-stu-id="9e3fe-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

