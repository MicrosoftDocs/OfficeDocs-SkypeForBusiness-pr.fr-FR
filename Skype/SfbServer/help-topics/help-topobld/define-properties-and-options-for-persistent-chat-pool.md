---
title: Définir les propriétés et les options de pool de conversations permanentes
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Vous configurez les options pour votre serveur de conversation permanente ou un pool de serveurs de conversation permanente en définissant les propriétés suivantes :'
ms.openlocfilehash: 23b307af37ae16a3ffb5c90e97d3974f3f5317ff
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503598"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="7a331-103">Définir les propriétés et les options de pool de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="7a331-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="7a331-104">Vous configurez les options pour votre serveur de conversation permanente ou un pool de serveurs de conversation permanente en définissant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="7a331-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="7a331-105">**Nom complet du pool de conversation permanente**: propriété obligatoire qui définit un nom convivial qui s’affichera pour ce serveur de conversation permanente ou un pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7a331-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="7a331-106">**Port de conversation permanente**: propriété obligatoire qui définira le port numéro auquel ce serveur de conversation permanente ou Persistent Chat Server pool écoutera.</span><span class="sxs-lookup"><span data-stu-id="7a331-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="7a331-107">**Activer la conformité**: activez la case à cocher si vous envisagez de déployer et d’implémenter la fonctionnalité de conformité de conversation permanente facultative et une base de données.</span><span class="sxs-lookup"><span data-stu-id="7a331-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="7a331-108">**Stocke les utiliser sauvegarde SQL Server pour activer la récupération d’urgence**: Activez cette case à cocher si vous envisagez de déployer et d’implémenter la récupération d’urgence du serveur SQL conversation permanente stocke à partir d’un jeu de sauvegarde configuré des magasins sur un autre serveur SQL.</span><span class="sxs-lookup"><span data-stu-id="7a331-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="7a331-109">Pour plus d’informations, voir [configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="7a331-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a331-110">Cette option n’est disponible que pour les pools comportant plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="7a331-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="7a331-111">**Utiliser ce pool comme valeur par défaut pour le site \<site ce serveur ou ce pool est configuré dans\>**: Activez cette case à cocher s’il s’agit du serveur de conversation permanente par défaut ou du pool Persistent Chat Server pour le site.</span><span class="sxs-lookup"><span data-stu-id="7a331-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="7a331-112">Vous devez disposer un serveur de conversation permanente par défaut ou pol par site.</span><span class="sxs-lookup"><span data-stu-id="7a331-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a331-113">Si votre topologie comporte plusieurs sites, la case à cocher **Toujours utiliser ce pool pour tous les sites** s’affiche également.</span><span class="sxs-lookup"><span data-stu-id="7a331-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="7a331-114">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="7a331-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="7a331-115">Une fois que vous avez fini d’entrer les options pour ce pool afin de passer à la définition du pool de serveurs de conversation permanente, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="7a331-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="7a331-116">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="7a331-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="7a331-117">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="7a331-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a331-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a331-118">See also</span></span>

[<span data-ttu-id="7a331-119">Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7a331-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7a331-120">Ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie</span><span class="sxs-lookup"><span data-stu-id="7a331-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)