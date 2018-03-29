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
description: 'Vous configurez les options de votre serveur de Chat permanent ou d’un pool de serveur de conversation persistant en définissant les propriétés suivantes :'
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="e46aa-103">Définir les propriétés et les options de pool de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="e46aa-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="e46aa-104">Vous configurez les options de votre serveur de Chat permanent ou d’un pool de serveur de conversation persistant en définissant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="e46aa-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="e46aa-105">**Nom complet du pool Chat persistant**: une propriété requise qui définit un nom convivial qui s’affiche pour ce serveur de Chat permanent ou d’un pool de serveur de conversation persistant.</span><span class="sxs-lookup"><span data-stu-id="e46aa-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="e46aa-106">**Port de conversation permanent**: une propriété requise qui définit le port numéro que ce serveur de conversation permanent ou pool de serveur de conversation persistant écoutera.</span><span class="sxs-lookup"><span data-stu-id="e46aa-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="e46aa-107">**Conformité**: activez la case à cocher si vous envisagez de déployer et de mettre en œuvre la fonctionnalité de mise en conformité de conversation persistant facultative et de la base de données.</span><span class="sxs-lookup"><span data-stu-id="e46aa-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="e46aa-108">**Utilisez sauvegarde SQL Server stocke pour la reprise après sinistre**: sélectionnez cette case à cocher si vous envisagez de déployer et de mettre en œuvre la reprise après sinistre de la permanente de SQL Server de Chat stocke à partir d’un jeu de sauvegarde configuré de banques sur un autre de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e46aa-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="e46aa-109">Pour plus d’informations, consultez [configurer la haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="e46aa-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e46aa-110">Cette option n’est disponible que pour les pools comportant plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="e46aa-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="e46aa-111">**Utiliser ce pool par défaut pour le site \<site que ce serveur ou ce pool est configuré dans\>**: Cochez cette case s’il s’agit par défaut persistante Chat Server ou pool de serveur de conversation persistant pour le site.</span><span class="sxs-lookup"><span data-stu-id="e46aa-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="e46aa-112">Il vous faut un serveur de conversation permanent par défaut ou pol par site.</span><span class="sxs-lookup"><span data-stu-id="e46aa-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e46aa-113">Si votre topologie comporte plusieurs sites, la case à cocher **Toujours utiliser ce pool pour tous les sites** s’affiche également.</span><span class="sxs-lookup"><span data-stu-id="e46aa-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="e46aa-114">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="e46aa-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="e46aa-115">Une fois que vous avez terminé d’entrer les options pour ce pool de procéder à la définition de pool persistant Chat Server, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="e46aa-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="e46aa-116">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="e46aa-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="e46aa-117">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="e46aa-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e46aa-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e46aa-118">See also</span></span>

#### 

[<span data-ttu-id="e46aa-119">Plan pour un serveur de conversation permanents dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e46aa-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="e46aa-120">Ajouter serveur de Chat permanente à votre Skype pour la topologie de Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e46aa-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

