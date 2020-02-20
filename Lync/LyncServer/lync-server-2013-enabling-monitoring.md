---
title: 'Lync Server 2013 : activation de la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07ea86bfeb9bd13f8fb3c4f34d114af075e6150
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="c3a30-102">Activation de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3a30-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3a30-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="c3a30-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="c3a30-104">Bien que les agents de collecte de données unifiées soient automatiquement installés et activés sur chaque serveur frontal, cela ne signifie pas que vous commencerez automatiquement à collecter les données d’analyse à l’installation de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3a30-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="c3a30-105">Auparavant, vous devez associer vos serveurs frontaux/pools frontaux à une base de données de surveillance et vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience au niveau de l’étendue globale et/ou de l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="c3a30-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="c3a30-106">Pour obtenir des instructions pas à pas sur l’Association de serveurs frontaux ou de pools frontaux à une base de données de surveillance, reportez-vous à la rubrique [Association d’un magasin de surveillance à un pool frontal dans Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) dans le Guide de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c3a30-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="c3a30-107">Ces associations créées et votre nouvelle topologie Lync Server publiée, vous ne pourrez toujours pas recueillir des données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="c3a30-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="c3a30-108">En effet, par défaut, les enregistrements des détails des appels et les données QoE sont désactivés lors de l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3a30-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="c3a30-109">Afin de pouvoir commencer la collecte de données, vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="c3a30-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="c3a30-110">(Notez que vous n’avez pas besoin d’activer à la fois le contrôle d’enregistrement des détails des appels et la surveillance QoE ; si vous le souhaitez, vous pouvez activer un type de surveillance tout en laissant l’autre type désactivé.) Pour activer la surveillance des enregistrements des détails des appels au niveau global, exécutez la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="c3a30-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="c3a30-111">Vous pouvez également activer la surveillance des enregistrements des détails des appels à partir du panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3a30-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c3a30-112">Dans le panneau de configuration Lync Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3a30-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="c3a30-113">Cliquez sur **Analyse**.</span><span class="sxs-lookup"><span data-stu-id="c3a30-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="c3a30-114">Sous l’onglet **Enregistrement des détails des appels**, double-cliquez sur le paramètre **Global**.</span><span class="sxs-lookup"><span data-stu-id="c3a30-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="c3a30-115">Dans le volet **Paramètre de l’enregistrement des détails des appels (CDR)**, sélectionnez **Activer la surveillance des enregistrements des détails des appels**, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c3a30-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="c3a30-116">Pour activer la surveillance QoE au niveau global, exécutez la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="c3a30-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="c3a30-117">Si vous préférez, vous pouvez également activer la surveillance QoE depuis le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3a30-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="c3a30-118">Dans le Panneau de configuration, effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="c3a30-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="c3a30-119">Cliquez sur **Surveillance**.</span><span class="sxs-lookup"><span data-stu-id="c3a30-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="c3a30-120">Sous l’onglet **Données de qualité de l’expérience**, double-cliquez sur le paramètre **Global**.</span><span class="sxs-lookup"><span data-stu-id="c3a30-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="c3a30-121">Dans le volet **Paramètre de qualité de l’expérience (QoE)**, sélectionnez **Activer la surveillance des données de qualité de l’expérience**, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c3a30-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="c3a30-122">Comme indiqué, les exemples précédents activent la surveillance au niveau de l’étendue globale ; ils activent les surveillances CDR et QoE dans toute votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c3a30-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="c3a30-123">Vous pouvez également créer des paramètres de configuration CDR et QoE distincts au niveau de l’étendue du site, puis activer ou désactiver de façon sélective la surveillance pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="c3a30-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="c3a30-124">Par exemple, vous pouvez activer la surveillance CDR pour votre site de Redmond et la désactiver pour votre site de Dublin.</span><span class="sxs-lookup"><span data-stu-id="c3a30-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="c3a30-125">Pour plus d’informations sur la gestion des paramètres de configuration de l’analyse, voir la rubrique relative à la [Configuration des paramètres d’enregistrement des détails des appels et de la qualité de l’expérience dans Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c3a30-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

