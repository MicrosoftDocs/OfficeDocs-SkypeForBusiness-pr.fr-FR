---
title: Configurer les serveurs d’applications approuvées
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dans un environnement mixte, si vous créez un serveur d’applications approuvé, vous devez définir le pool du saut suivant comme pool Skype Entreprise Server 2019. Dans un environnement mixte, le pool hérité et le pool Skype Entreprise Server 2019 apparaissent dans la liste liste. La sélection du pool hérité n’est pas prise en charge.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753944"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="4e099-105">Configurer les serveurs d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="4e099-105">Configure trusted application servers</span></span>

<span data-ttu-id="4e099-106">Dans un environnement mixte, si vous créez un serveur d’applications approuvé, vous devez définir le pool du saut suivant comme pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4e099-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="4e099-107">Dans un environnement mixte, le pool hérité et le pool Skype Entreprise Server 2019 apparaissent dans la liste de listes.</span><span class="sxs-lookup"><span data-stu-id="4e099-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="4e099-108">La sélection du pool hérité n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4e099-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e099-109">Si vous migrez un serveur d’applications approuvé, vous devez également mettre à jour la version d’UCMA que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="4e099-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="4e099-110">Si vous créez un nouveau pool d’applications de confiance pour Skype Entreprise Server 2019, vous devez mettre à jour UCMA vers la version incluse dans Skype Entreprise Server 2019 ou la dernière version disponible.</span><span class="sxs-lookup"><span data-stu-id="4e099-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="4e099-111">Sélectionner Skype Entreprise Server 2019 comme saut suivant lors de la création d’un serveur d’applications de confiance</span><span class="sxs-lookup"><span data-stu-id="4e099-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="4e099-112">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="4e099-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="4e099-113">Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications** de confiance et cliquez sur **Nouveau pool d’applications de confiance.**</span><span class="sxs-lookup"><span data-stu-id="4e099-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="4e099-114">Entrez le **nom de pool du** pool d’applications de confiance et sélectionnez s’il s’appliquera à un ou plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="4e099-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="4e099-115">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4e099-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="4e099-116">Dans la page **Sélectionner le saut suivant,** dans la liste, sélectionnez le pool frontal Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4e099-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="4e099-117">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4e099-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="4e099-118">Sélectionnez le nœud supérieur **Skype Entreprise Server** et, dans le menu **Action,** sélectionnez **Publier.**</span><span class="sxs-lookup"><span data-stu-id="4e099-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="4e099-119">Vérifiez que le **pool d’applications** fiables a bien été créé et qu’il est associé au pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="4e099-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

