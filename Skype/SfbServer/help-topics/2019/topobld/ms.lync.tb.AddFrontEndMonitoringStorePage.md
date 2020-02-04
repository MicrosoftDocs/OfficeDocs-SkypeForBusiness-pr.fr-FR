---
title: Page Ajouter un magasin d’analyse frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour définir la gestion SQL Server Store, vous devez configurer les propriétés suivantes :'
ms.openlocfilehash: e9d26322fa9f3844864f9645e4dcefbccdddecd3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702859"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="65574-103">Page Ajouter un magasin d’analyse frontal</span><span class="sxs-lookup"><span data-stu-id="65574-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="65574-104">Pour **définir la gestion SQL Server Store** , vous devez configurer les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="65574-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="65574-105">**Surveiller SQL Server Store**: sélectionnez un nom de domaine complet SQL Server (et éventuellement une instance) dans la liste.</span><span class="sxs-lookup"><span data-stu-id="65574-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="65574-106">Cliquez sur **nouveau** pour créer une nouvelle définition de nom de domaine complet SQL Server et éventuellement sur un nom d’instance pour le magasin du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="65574-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="65574-107">Activez la case à cocher **activer la mise en miroir du magasin SQL Server** si vous souhaitez ajouter la mise en miroir de la base de données pour le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="65574-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="65574-108">Sélectionnez une **image miroir SQL Server Store** existante dans la liste.</span><span class="sxs-lookup"><span data-stu-id="65574-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="65574-109">Cliquez sur **nouveau** pour créer une nouvelle définition de nom de domaine complet SQL Server et éventuellement sur le nom d’instance du magasin en miroir.</span><span class="sxs-lookup"><span data-stu-id="65574-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="65574-110">Si vous avez sélectionné **activer la mise en miroir du magasin SQL Server**, sélectionnez éventuellement **utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique** pour sélectionner un magasin témoin de mise en miroir SQL Server dans la liste.</span><span class="sxs-lookup"><span data-stu-id="65574-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="65574-111">Cliquez sur **nouveau** pour créer une nouvelle définition de nom de domaine complet SQL Server et éventuellement sur le nom d’instance du magasin témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="65574-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="65574-112">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="65574-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="65574-113">Cliquez sur **suivant** lorsque vous avez fini d’entrer les options de cette boîte de dialogue pour poursuivre la configuration.</span><span class="sxs-lookup"><span data-stu-id="65574-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="65574-114">Cliquez sur **Annuler** pour ignorer toutes les modifications et arrêter l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="65574-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="65574-115">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="65574-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="65574-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65574-116">See also</span></span>

[<span data-ttu-id="65574-117">Associez un magasin d’analyse à un pool frontal dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="65574-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
