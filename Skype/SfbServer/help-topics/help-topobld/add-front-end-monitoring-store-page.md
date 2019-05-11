---
title: Page Ajouter un magasin d’analyse frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Vous pouvez définir le magasin de surveillance de SQL Server en configurant les propriétés suivantes :'
ms.openlocfilehash: d2af2ea26c15ec30e706eb67262745b977a8881c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904173"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="00c05-103">Page Ajouter un magasin d’analyse frontal</span><span class="sxs-lookup"><span data-stu-id="00c05-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="00c05-104">Vous pouvez **définir le magasin SQL Server de surveillance** en configurant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="00c05-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="00c05-105">**Magasin SQL Server de surveillance**: sélectionnez un nom de domaine complet du serveur SQL (et éventuellement une instance) dans la liste.</span><span class="sxs-lookup"><span data-stu-id="00c05-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="00c05-106">Cliquez sur **Nouveau** pour créer une nouvelle définition de nom de domaine complet de SQL Server et éventuellement un nom d’instance pour le magasin du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="00c05-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="00c05-107">Activez la case à cocher **Activer magasin SQL Server de mise en miroir** si vous souhaitez ajouter à la mise en miroir de base de données pour le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="00c05-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="00c05-108">Dans la liste, sélectionnez une existante **surveillance magasin SQL Server de mise en miroir** .</span><span class="sxs-lookup"><span data-stu-id="00c05-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="00c05-109">Cliquez sur **Nouveau** pour créer une nouvelle définition de nom de domaine complet de SQL Server et éventuellement un nom d’instance pour le magasin miroir.</span><span class="sxs-lookup"><span data-stu-id="00c05-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="00c05-110">Si vous avez sélectionné **la mise en miroir du magasin d’activer le serveur SQL**, sélectionnez éventuellement **utiliser SQL Server la mise en miroir témoin pour activer le basculement automatique** pour sélectionner un magasin de témoins de la liste de la mise en miroir de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00c05-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="00c05-111">Cliquez sur **Nouveau** pour créer une nouvelle définition de nom de domaine complet de SQL Server et éventuellement un nom d’instance pour le magasin de témoins de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="00c05-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="00c05-112">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="00c05-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="00c05-113">Une fois que vous avez fini d’entrer les options de cette boîte de dialogue poursuivre la configuration, cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="00c05-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="00c05-114">Cliquez sur **Annuler** pour annuler toutes les modifications et quitter l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="00c05-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="00c05-115">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active.</span><span class="sxs-lookup"><span data-stu-id="00c05-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00c05-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00c05-116">See also</span></span>

[<span data-ttu-id="00c05-117">Association d’un magasin de surveillance à un pool frontal dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="00c05-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
