---
title: Définir les propriétés et les options de pool de conversations permanentes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Vous configurez les options de votre serveur de conversation permanente ou de votre pool de serveurs de conversation permanente en définissant les propriétés suivantes :'
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218545"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="e481a-103">Définir les propriétés et les options de pool de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="e481a-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="e481a-104">Vous configurez les options de votre serveur de conversation permanente ou de votre pool de serveurs de conversation permanente en définissant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="e481a-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="e481a-105">**Nom complet du pool de conversations permanentes**: propriété obligatoire définissant un nom convivial qui s’affichera pour ce serveur de conversation permanente ou ce pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e481a-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="e481a-106">**Port de conversation permanente**: propriété obligatoire qui définit le numéro de port sur lequel le serveur de conversation permanente ou le pool de serveurs de conversation permanente écoute.</span><span class="sxs-lookup"><span data-stu-id="e481a-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="e481a-107">**Activer la conformité**: activez cette case à cocher si vous envisagez de déployer et d’implémenter la fonctionnalité et la base de données de conformité de conversation permanente facultatives.</span><span class="sxs-lookup"><span data-stu-id="e481a-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="e481a-108">**Utiliser des magasins SQL Server de sauvegarde pour activer la récupération d’urgence**: activez cette case à cocher si vous envisagez de déployer et d’implémenter la récupération d’urgence des magasins SQL Server de conversation permanente à partir d’un jeu de banques de sauvegarde configuré sur un autre serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e481a-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="e481a-109">Pour plus d’informations, reportez-vous à la rubrique [configure High Availability and Disaster Recovery for persistent Chat Server in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="e481a-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e481a-110">Cette option est disponible uniquement pour les pools avec plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="e481a-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="e481a-111">\*\*Utiliser ce pool comme serveur par défaut pour \<site that this server or pool is being configured in\> le site \*\*: activez cette case à cocher s’il s’agit du pool de serveurs de conversation permanente ou de conversation permanente par défaut pour le site.</span><span class="sxs-lookup"><span data-stu-id="e481a-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="e481a-112">Vous devez disposer d’un serveur de conversation permanente par défaut ou de Pol par site.</span><span class="sxs-lookup"><span data-stu-id="e481a-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e481a-113">Si votre topologie comprend plusieurs sites, une case à cocher **utiliser ce pool comme valeur par défaut pour tous les sites** s’affiche également.</span><span class="sxs-lookup"><span data-stu-id="e481a-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="e481a-114">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="e481a-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="e481a-115">Une fois que vous avez terminé d’entrer les options pour ce pool, cliquez sur **suivant** pour continuer avec la définition de pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="e481a-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="e481a-116">Cliquez sur **Annuler** pour ignorer toutes les modifications et mettre fin à l’Assistant **Définir un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="e481a-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="e481a-117">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.</span><span class="sxs-lookup"><span data-stu-id="e481a-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e481a-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e481a-118">See also</span></span>

[<span data-ttu-id="e481a-119">Planifier le serveur de conversation permanente dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e481a-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="e481a-120">Ajouter un serveur de conversation permanente à votre topologie Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e481a-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
