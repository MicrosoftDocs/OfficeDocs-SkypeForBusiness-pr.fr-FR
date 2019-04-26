---
title: Configuration des serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées, vous devez définir le pool à un Skype pour Business Server 2019 pool du tronçon suivant. Dans un environnement mixte, à la fois le pool hérité et le Skype pour Business Server 2019 pool s’affichent dans la liste déroulante. Sélectionnez le pool hérité n’est pas pris en charge.
ms.openlocfilehash: 79f4de527008d2d9bf295fcb82eee433d04a1691
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238681"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="f53f3-105">Configuration des serveurs d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="f53f3-105">Configure trusted application servers</span></span>

<span data-ttu-id="f53f3-106">Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées, vous devez définir le pool à un Skype pour Business Server 2019 pool du tronçon suivant.</span><span class="sxs-lookup"><span data-stu-id="f53f3-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f53f3-107">Dans un environnement mixte, à la fois le pool hérité et le Skype pour Business Server 2019 pool s’affichent dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f53f3-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="f53f3-108">Sélectionnez le pool hérité n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f53f3-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f53f3-109">Si vous migrez un serveur d’applications approuvées, vous devez également mettre à jour la version d’UCMA que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="f53f3-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="f53f3-110">Si vous créez un nouveau Pool d’applications approuvées pour Skype pour Business Server 2019, vous devez mettre à jour UCMA pour la version qui est incluse avec Skype pour Business Server 2019 ou la version la plus récente.</span><span class="sxs-lookup"><span data-stu-id="f53f3-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="f53f3-111">Sélectionnez Skype pour Business Server 2019 comme tronçon suivant lors de la création d’un serveur d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="f53f3-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="f53f3-112">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f53f3-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="f53f3-113">Dans le volet gauche, cliquez sur **serveurs d’applications approuvées** , cliquez sur **Nouveau Pool d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="f53f3-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="f53f3-114">Entrez le **Nom complet du Pool** du pool d’applications approuvées et indiquez s’il s’agira serveur unique ou de plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="f53f3-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="f53f3-115">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f53f3-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="f53f3-116">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le Skype pour Business Server 2019 un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f53f3-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="f53f3-117">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f53f3-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="f53f3-118">Sélectionnez le nœud supérieur **Skype pour Business Server**, dans le menu **Action** , sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="f53f3-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="f53f3-119">Vérifiez que le **Pool d’applications approuvées** a été créé avec succès et associé au pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="f53f3-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

