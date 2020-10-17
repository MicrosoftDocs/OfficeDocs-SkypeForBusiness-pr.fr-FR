---
title: Création et configuration de stratégies utilisateur pour l’archivage dans Lync Server
description: Création et configuration de stratégies utilisateur pour l’archivage dans Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dad260910f01e10c71dbbde67af98ea9a207e33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563090"
---
# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="d4155-103">Création et configuration de stratégies utilisateur pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4155-103">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4155-104">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="d4155-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="d4155-105">Pour activer ou désactiver l’archivage pour des utilisateurs spécifiques hébergés sur Lync Server, vous devez d’abord créer une stratégie utilisateur, puis l’appliquer à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d4155-105">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="d4155-106">Pour plus d’informations sur l’application de stratégies d’utilisateur à des utilisateurs et groupes d’utilisateurs spécifiques, voir [Applying a Lync Server Archiving Policy to a User in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d4155-106">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="d4155-107">Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="d4155-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d4155-108">Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de blocage Exchange In-Place déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation In-Place.</span><span class="sxs-lookup"><span data-stu-id="d4155-108">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="d4155-109">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d4155-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="d4155-110">Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="d4155-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="d4155-111">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d4155-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="d4155-112">Pour configurer une stratégie d’archivage pour les utilisateurs hébergés sur Lync Server</span><span class="sxs-lookup"><span data-stu-id="d4155-112">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="d4155-113">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="d4155-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4155-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4155-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d4155-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, reportez-vous à la rubrique [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d4155-115">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4155-116">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="d4155-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="d4155-117">Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="d4155-117">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="d4155-118">Dans **Nouvelle stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d4155-118">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="d4155-119">Dans **Nom**, spécifiez le nom de la stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d4155-119">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="d4155-120">Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).</span><span class="sxs-lookup"><span data-stu-id="d4155-120">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="d4155-121">Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="d4155-121">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="d4155-122">Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="d4155-122">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="d4155-123">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="d4155-123">Click **Commit**.</span></span>

<span data-ttu-id="d4155-124">Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie.</span><span class="sxs-lookup"><span data-stu-id="d4155-124">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="d4155-125">Pour plus d’informations sur l’application d’une stratégie utilisateur à des utilisateurs spécifiques, reportez-vous [à l’application d’une stratégie d’archivage Lync Server à un utilisateur dans Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d4155-125">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

