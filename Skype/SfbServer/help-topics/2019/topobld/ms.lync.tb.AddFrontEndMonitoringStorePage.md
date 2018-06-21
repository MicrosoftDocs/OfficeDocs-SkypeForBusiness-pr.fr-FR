---
title: Ajouter un frontal Page magasin de surveillance
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Vous pouvez définir le magasin de surveillance de SQL Server en configurant les propriétés suivantes :'
ms.openlocfilehash: bb53d2105bc3a412b06d1fc51fbd4413c49271e6
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988333"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="c7e41-103">Ajouter un frontal Page magasin de surveillance</span><span class="sxs-lookup"><span data-stu-id="c7e41-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="c7e41-104">Vous pouvez **définir le magasin SQL Server de surveillance** en configurant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7e41-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="c7e41-105">**Magasin SQL Server de surveillance**: sélectionnez un nom de domaine complet du serveur SQL (et éventuellement une instance) dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c7e41-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="c7e41-106">Cliquez sur **Nouveau** pour créer une nouvelle définition de nom de domaine complet de SQL Server et éventuellement un nom d’instance pour le magasin du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="c7e41-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="c7e41-107">Activez la case à cocher **Activer magasin SQL Server de mise en miroir** si vous souhaitez ajouter à la mise en miroir de base de données pour le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="c7e41-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="c7e41-108">Dans la liste, sélectionnez une existante **surveillance magasin SQL Server de mise en miroir** .</span><span class="sxs-lookup"><span data-stu-id="c7e41-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="c7e41-109">Cliquez sur **Nouveau** pour créer une nouvelle définition de nom de domaine complet de SQL Server et éventuellement un nom d’instance pour le magasin miroir.</span><span class="sxs-lookup"><span data-stu-id="c7e41-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="c7e41-110">Si vous avez sélectionné **la mise en miroir du magasin d’activer le serveur SQL**, sélectionnez éventuellement **utiliser SQL Server la mise en miroir témoin pour activer le basculement automatique** pour sélectionner un magasin de témoins de la liste de la mise en miroir de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c7e41-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="c7e41-111">Cliquez sur **Nouveau** pour créer une nouvelle définition de nom de domaine complet de SQL Server et éventuellement un nom d’instance pour le magasin de témoins de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="c7e41-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="c7e41-112">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="c7e41-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="c7e41-113">Une fois que vous avez fini d’entrer les options de cette boîte de dialogue poursuivre la configuration, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="c7e41-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="c7e41-114">Cliquez sur **Annuler** pour annuler toutes les modifications et quitter l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="c7e41-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="c7e41-115">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="c7e41-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7e41-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7e41-116">See also</span></span>

[<span data-ttu-id="c7e41-117">Associer un pool frontal dans Skype pour Business Server dans un magasin d’analyse</span><span class="sxs-lookup"><span data-stu-id="c7e41-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)