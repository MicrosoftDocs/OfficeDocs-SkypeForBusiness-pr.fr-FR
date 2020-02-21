---
title: 'Lync Server 2013 : configuration de la stratégie globale pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f381aeb1493637dae0f5e25a72e3154bfeb76513
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="f4698-102">Configuration de la stratégie globale pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4698-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4698-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f4698-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f4698-104">Lorsque vous déployez vos serveurs frontaux, Lync Server crée une stratégie globale pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="f4698-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="f4698-105">Par défaut, l’archivage est désactivé dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="f4698-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="f4698-106">La stratégie globale contrôle si l’archivage est activé pour les communications internes et externes pour l’ensemble de votre déploiement, sauf si vous configurez des stratégies de site ou d’utilisateur, qui remplacent la stratégie globale, ou si vous utilisez l’intégration de Microsoft Exchange pour tout ou partie des vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f4698-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="f4698-107">Si vous utilisez l’intégration de Microsoft Exchange, la stratégie globale ne s’applique pas aux utilisateurs hébergés sur Exchange 2013 et les boîtes aux lettres sont placées en conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="f4698-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="f4698-108">Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir [How Archiving Works dans Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation ou Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="f4698-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4698-109">Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de conservation inaltérable d’Exchange contrôlent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="f4698-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="f4698-110">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f4698-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="f4698-111">Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="f4698-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="f4698-112">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f4698-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="f4698-113">Pour configurer la stratégie globale pour l’archivage lors de l’utilisation de bases de données d’archivage Lync Server</span><span class="sxs-lookup"><span data-stu-id="f4698-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="f4698-114">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f4698-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4698-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4698-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="f4698-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f4698-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f4698-117">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f4698-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="f4698-118">Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f4698-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f4698-119">Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f4698-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="f4698-120">Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="f4698-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="f4698-121">Dans **Description**, fournissez des informations sur la stratégie (par exemple, stratégie globale de *nom_division*).</span><span class="sxs-lookup"><span data-stu-id="f4698-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="f4698-122">Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="f4698-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="f4698-123">Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="f4698-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="f4698-124">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f4698-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

