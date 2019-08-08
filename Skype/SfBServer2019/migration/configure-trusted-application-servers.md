---
title: Configuration des serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans un environnement mixte, si vous créez un nouveau serveur d’applications de confiance, vous devez définir le pool de prochains tronçons comme un pool Skype entreprise Server 2019. Dans un environnement mixte, le pool hérité et le pool 2019 de Skype entreprise Server apparaissent dans la liste déroulante. La sélection du pool hérité n’est pas prise en charge.
ms.openlocfilehash: b715cd7f3f067c5e54dbc085350fcc7f96b5c4be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239297"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="d96d7-105">Configuration des serveurs d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="d96d7-105">Configure trusted application servers</span></span>

<span data-ttu-id="d96d7-106">Dans un environnement mixte, si vous créez un nouveau serveur d’applications de confiance, vous devez définir le pool de prochains tronçons comme un pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d96d7-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d96d7-107">Dans un environnement mixte, le pool hérité et le pool 2019 de Skype entreprise Server apparaissent dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="d96d7-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="d96d7-108">La sélection du pool hérité n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d96d7-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d96d7-109">Si vous migrez un serveur d’application de confiance, vous devez également mettre à jour la version de UCMA que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="d96d7-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="d96d7-110">Si vous créez un nouveau pool d’applications approuvé pour Skype entreprise Server 2019, vous devez mettre à jour UCMA vers la version incluse dans Skype entreprise Server 2019 ou la dernière version disponible.</span><span class="sxs-lookup"><span data-stu-id="d96d7-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="d96d7-111">Sélectionner Skype entreprise Server 2019 comme tronçon suivant lors de la création d’un serveur d’applications de confiance</span><span class="sxs-lookup"><span data-stu-id="d96d7-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="d96d7-112">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d96d7-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="d96d7-113">Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications de confiance** , puis cliquez sur **nouveau pool d’applications de confiance**.</span><span class="sxs-lookup"><span data-stu-id="d96d7-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="d96d7-114">Entrez le **nom de domaine complet (FQDN)** du pool d’applications de confiance et sélectionnez s’il s’agit d’un serveur unique ou d’un serveur multiple.</span><span class="sxs-lookup"><span data-stu-id="d96d7-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="d96d7-115">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d96d7-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="d96d7-116">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d96d7-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="d96d7-117">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d96d7-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="d96d7-118">Sélectionnez le nœud supérieur **Skype entreprise Server**, puis, dans le menu **action** , sélectionnez **publier**.</span><span class="sxs-lookup"><span data-stu-id="d96d7-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="d96d7-119">Vérifiez que le **pool d’applications approuvé** a été créé avec succès et est associé au pool frontal approprié.</span><span class="sxs-lookup"><span data-stu-id="d96d7-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

