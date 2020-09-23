---
title: Page Ajouter un magasin d’analyse frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Vous pouvez définir le magasin SQL Server pour la surveillance en configurant les propriétés suivantes :'
ms.openlocfilehash: 85b8518bb533de68423dea93f259fc7b927ed9ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218875"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="1c780-103">Page Ajouter un magasin d’analyse frontal</span><span class="sxs-lookup"><span data-stu-id="1c780-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="1c780-104">Vous pouvez **définir le magasin SQL Server pour la surveillance** en configurant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="1c780-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="1c780-105">**Magasin SQL Server de surveillance**: sélectionnez un nom de domaine complet SQL Server (et éventuellement une instance) dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1c780-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="1c780-106">Cliquez sur **nouveau** pour créer une définition de nom de domaine complet SQL Server et éventuellement un nom d’instance pour le magasin du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1c780-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="1c780-107">Activez la case à cocher **activer la mise en miroir du magasin SQL Server** si vous voulez ajouter la mise en miroir de base de données pour le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1c780-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="1c780-108">Sélectionnez un **Miroir du magasin SQL Server de surveillance** existant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1c780-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="1c780-109">Cliquez sur **nouveau** pour créer une définition de nom de domaine complet SQL Server et éventuellement un nom d’instance pour le magasin miroir.</span><span class="sxs-lookup"><span data-stu-id="1c780-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="1c780-110">Si vous avez sélectionné **activer la mise en miroir du magasin SQL Server**, sélectionnez éventuellement **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** afin de sélectionner un magasin de témoins de mise en miroir SQL Server dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1c780-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="1c780-111">Cliquez sur **nouveau** pour créer une définition de nom de domaine complet SQL Server et éventuellement un nom d’instance pour le magasin de témoins de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="1c780-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="1c780-112">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="1c780-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="1c780-113">Après avoir défini les options de cette boîte de dialogue, cliquez sur **Suivant** pour poursuivre la configuration.</span><span class="sxs-lookup"><span data-stu-id="1c780-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="1c780-114">Cliquez sur **Annuler** pour ignorer toutes les modifications et quitter l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="1c780-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="1c780-115">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.</span><span class="sxs-lookup"><span data-stu-id="1c780-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c780-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c780-116">See also</span></span>

[<span data-ttu-id="1c780-117">Associer un magasin de surveillance à un pool frontal dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="1c780-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
