---
title: Développeur des paramètres généraux d’une application externe
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez les instructions ci-dessous.
ms.openlocfilehash: eacc0c854290fcf24196a8e4c58829231dc725c4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793742"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="e9450-103">Développeur des paramètres généraux d’une application externe</span><span class="sxs-lookup"><span data-stu-id="e9450-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="e9450-104">Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez les instructions ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e9450-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="e9450-105">Vous pouvez modifier deux sections :</span><span class="sxs-lookup"><span data-stu-id="e9450-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="e9450-106">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="e9450-106">General settings</span></span>
> 
> <span data-ttu-id="e9450-107">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="e9450-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="e9450-108">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="e9450-108">General Settings</span></span>

<span data-ttu-id="e9450-109">Vous pouvez modifier l’actuel nom de domaine complet (FQDN) du pool de serveurs d’applications de confiance.</span><span class="sxs-lookup"><span data-stu-id="e9450-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="e9450-110">Modifiez le nom du nom de domaine complet (FQDN) du pool.</span><span class="sxs-lookup"><span data-stu-id="e9450-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="e9450-111">Les enregistrements d’hôte DNS (Domain Name System) doivent exister pour la nouvelle entrée avant qu’un client ou un serveur puisse se connecter au nouveau nom du pool.</span><span class="sxs-lookup"><span data-stu-id="e9450-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="e9450-112">Pour pouvoir répliquer les données de configuration vers ce pool, sélectionnez **activer la réplication des données de configuration** .</span><span class="sxs-lookup"><span data-stu-id="e9450-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="e9450-113">Supprimez la coche si vous ne souhaitez pas répliquer les données de configuration.</span><span class="sxs-lookup"><span data-stu-id="e9450-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="e9450-114">Paramètres de saut suivant</span><span class="sxs-lookup"><span data-stu-id="e9450-114">Next Hop Settings</span></span>

<span data-ttu-id="e9450-115">Dans la liste déroulante, vous pouvez spécifier le serveur tronçon suivant du pool de serveurs d’applications de confiance en sélectionnant le serveur frontal Enterprise Edition défini dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="e9450-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="e9450-116">Un réalisateur ou un pool de réalisateurs n’est pas une sélection valide pour le tronçon suivant d’un serveur d’applications de confiance et n’apparaîtra pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9450-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="e9450-117">Cliquez sur **OK** pour accepter et enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="e9450-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="e9450-118">Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.</span><span class="sxs-lookup"><span data-stu-id="e9450-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

