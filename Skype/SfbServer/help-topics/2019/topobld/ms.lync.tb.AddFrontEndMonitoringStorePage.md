---
title: Page Ajouter un magasin d’analyse frontal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous pouvez définir le magasin SQL Server pour la surveillance en configurant les propriétés suivantes :'
ms.openlocfilehash: e867ec998e1380e70125d0ad743f83b06737758e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811664"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="5ece0-103">Page Ajouter un magasin d’analyse frontal</span><span class="sxs-lookup"><span data-stu-id="5ece0-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="5ece0-104">Vous pouvez **définir le magasin SQL Server pour la surveillance** en configurant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="5ece0-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="5ece0-105">**Surveillance SQL Server magasin :** sélectionnez un SQL Server de domaine complet (et éventuellement une instance) dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5ece0-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="5ece0-106">Cliquez **sur Nouveau** pour créer une définition SQL Server FQDN et éventuellement un nom d’instance pour le magasin du serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="5ece0-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="5ece0-107">Activez **la case à SQL Server la** mise en miroir du magasin si vous souhaitez ajouter la mise en miroir de base de données pour le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="5ece0-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="5ece0-108">Sélectionnez un **Miroir du magasin SQL Server de surveillance** existant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5ece0-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="5ece0-109">Cliquez **sur Nouveau** pour créer une définition SQL Server FQDN et éventuellement un nom d’instance pour le magasin miroir.</span><span class="sxs-lookup"><span data-stu-id="5ece0-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="5ece0-110">Si vous avez sélectionné Activer la mise en **miroir** du magasin SQL Server, sélectionnez éventuellement Utiliser le témoin de mise en miroir **SQL Server** pour activer le fait de faire échouer automatiquement la sélection d’un magasin de témoins de mise en miroir SQL Server dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5ece0-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="5ece0-111">Cliquez **sur Nouveau** pour créer une définition SQL Server FQDN et éventuellement un nom d’instance pour le magasin témoin de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="5ece0-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="5ece0-112">Cliquez sur **Précédent** pour revenir à la boîte de dialogue précédente de définition de pool.</span><span class="sxs-lookup"><span data-stu-id="5ece0-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="5ece0-113">Après avoir défini les options de cette boîte de dialogue, cliquez sur **Suivant** pour poursuivre la configuration.</span><span class="sxs-lookup"><span data-stu-id="5ece0-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="5ece0-114">Cliquez sur **Annuler** pour ignorer toutes les modifications et quitter l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="5ece0-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="5ece0-115">Cliquez sur **Aide** pour accéder à une aide contextuelle, comme celle de la page active, par exemple.</span><span class="sxs-lookup"><span data-stu-id="5ece0-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ece0-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ece0-116">See also</span></span>

[<span data-ttu-id="5ece0-117">Associer un magasin d’analyse à un pool frontal dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5ece0-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
