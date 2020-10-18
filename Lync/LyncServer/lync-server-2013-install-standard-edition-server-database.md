---
title: 'Lync Server 2013 : installation de la base de données serveur Standard Edition'
description: 'Lync Server 2013 : installation de la base de données serveur Standard Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a20d2c01de94ad88960555db78c57c6b79d92f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574080"
---
# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="13f84-103">Installer la base de données de serveur Standard Edition pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13f84-103">Install Standard Edition server database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13f84-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="13f84-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="13f84-105">La configuration d’un serveur Standard Edition Server en tant que seul serveur dans votre infrastructure qui héberge des utilisateurs diffère de celle des autres serveurs dans la mesure où il existe une sélection dans l' **Assistant Déploiement** spécifiquement pour la configuration du serveur initial.</span><span class="sxs-lookup"><span data-stu-id="13f84-105">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="13f84-106">Pour installer un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="13f84-106">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="13f84-107">Ouvrez une session sur le serveur sur lequel vous allez installer le serveur Standard Edition en tant qu’administrateur local ou en tant que domaine équivalent.</span><span class="sxs-lookup"><span data-stu-id="13f84-107">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="13f84-108">Si vous n’avez pas préparé les services de domaine Active Directory, effectuez d’abord ces procédures.</span><span class="sxs-lookup"><span data-stu-id="13f84-108">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="13f84-109">Pour plus d’informations, consultez la rubrique [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="13f84-109">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="13f84-110">Dans l’Assistant Déploiement Lync Server, cliquez sur **préparer d’abord le serveur Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="13f84-110">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="13f84-111">Dans la page **Préparer le serveur Standard Edition**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="13f84-111">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="13f84-112">Sur la page **exécution de commandes** , SQL Server 2012 Express est installé en tant que magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="13f84-112">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="13f84-113">Les règles de pare-feu nécessaires sont créées.</span><span class="sxs-lookup"><span data-stu-id="13f84-113">Necessary firewall rules are created.</span></span> <span data-ttu-id="13f84-114">Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="13f84-114">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="13f84-115">L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande.</span><span class="sxs-lookup"><span data-stu-id="13f84-115">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="13f84-116">Ceci est dû à l’installation de SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="13f84-116">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="13f84-117">Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches.</span><span class="sxs-lookup"><span data-stu-id="13f84-117">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="13f84-118">Sur la page Assistant Déploiement Lync Server, cliquez sur **installer le générateur de topologie** si vous n’avez pas préalablement installé les outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="13f84-118">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="13f84-119">Pour plus d’informations, reportez-vous à la rubrique [install Lync Server 2013 administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="13f84-119">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="13f84-120">Vérifiez que des coches vertes apparaissent bien en regard de « Préparer Active Directory », « Préparer le serveur Standard Edition » et « Installer le Générateur de topologie ».</span><span class="sxs-lookup"><span data-stu-id="13f84-120">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

