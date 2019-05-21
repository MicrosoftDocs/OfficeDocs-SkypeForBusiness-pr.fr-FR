---
title: Définir les propriétés et les options de pool de conversations permanentes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Vous pouvez configurer les options pour votre serveur de chat permanent ou le pool de serveurs de chat permanent en définissant les propriétés suivantes:'
ms.openlocfilehash: f719a4c76be88dd571c551645bacd13ef22e9a19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306142"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="92dd0-103">Définir les propriétés et les options de pool de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="92dd0-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="92dd0-104">Vous pouvez configurer les options pour votre serveur de chat permanent ou le pool de serveurs de chat permanent en définissant les propriétés suivantes:</span><span class="sxs-lookup"><span data-stu-id="92dd0-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="92dd0-105">**Nom d’affichage du pool de conversations permanentes**: propriété requise définissant un nom convivial qui sera affiché pour ce serveur de chat permanent ou le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="92dd0-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="92dd0-106">**Port de chat permanent**: propriété requise définissant le numéro de port que le serveur de chat permanent ou le pool de serveurs de chat permanent écoutera.</span><span class="sxs-lookup"><span data-stu-id="92dd0-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="92dd0-107">**Activer la conformité**: activez la case à cocher si vous envisagez de déployer et d’implémenter la fonctionnalité et la base de données de compatibilité de conversation persistante facultative.</span><span class="sxs-lookup"><span data-stu-id="92dd0-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="92dd0-108">**Utiliser les magasins de sauvegarde SQL Server pour activer la reprise après sinistre**: activez cette case à cocher si vous envisagez de déployer et de mettre en œuvre une reprise après sinistre des magasins SQL Server de discussion persistante à partir d’un jeu de stockage de sauvegarde configuré sur un autre serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="92dd0-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="92dd0-109">Pour plus d’informations, reportez-vous à la rubrique Configuration de la [haute disponibilité et de la reprise après sinistre pour le serveur Chat permanent dans Skype entreprise server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="92dd0-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="92dd0-110">Cette option n’est disponible que pour les pools comportant plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="92dd0-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="92dd0-111">**Utilisez ce pool par défaut pour le site \<de site\>sur lequel ce serveur ou ce pool est configuré**: activez cette case à cocher s’il s’agit du serveur de chat permanent par défaut ou du pool de serveurs de chat permanent pour le site.</span><span class="sxs-lookup"><span data-stu-id="92dd0-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="92dd0-112">Vous devez disposer d’une conversation permanente par défaut ou d’un serveur. pol par site.</span><span class="sxs-lookup"><span data-stu-id="92dd0-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="92dd0-113">Si votre topologie comporte plusieurs sites, la case à cocher **Toujours utiliser ce pool pour tous les sites** s’affiche également.</span><span class="sxs-lookup"><span data-stu-id="92dd0-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="92dd0-114">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="92dd0-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="92dd0-115">Cliquez sur **suivant** une fois que vous avez terminé d’entrer les options pour ce pool et continuez avec la définition du pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="92dd0-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="92dd0-116">Cliquez sur **Annuler** pour ignorer toutes les modifications et fermer l’Assistant **Définition d’un nouveau pool de conversations permanentes**.</span><span class="sxs-lookup"><span data-stu-id="92dd0-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="92dd0-117">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="92dd0-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92dd0-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92dd0-118">See also</span></span>

[<span data-ttu-id="92dd0-119">Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="92dd0-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="92dd0-120">Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="92dd0-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
