---
title: Développeur des paramètres généraux d’une application externe
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez les instructions ci-dessous.
ms.openlocfilehash: 99ccca72613edbde4b38d21dd8e8bb121e5a8dd5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697359"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="94e67-103">Développeur des paramètres généraux d’une application externe</span><span class="sxs-lookup"><span data-stu-id="94e67-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="94e67-104">Pour modifier les propriétés d’un serveur d’application de confiance qui a déjà été défini, suivez les instructions ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="94e67-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="94e67-105">Vous pouvez modifier deux sections :</span><span class="sxs-lookup"><span data-stu-id="94e67-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="94e67-106">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="94e67-106">General settings</span></span>
> 
> <span data-ttu-id="94e67-107">Paramètres du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="94e67-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="94e67-108">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="94e67-108">General Settings</span></span>

<span data-ttu-id="94e67-109">Vous pouvez modifier l’actuel nom de domaine complet (FQDN) du pool de serveurs d’applications de confiance.</span><span class="sxs-lookup"><span data-stu-id="94e67-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="94e67-110">Modifiez le nom du nom de domaine complet (FQDN) du pool.</span><span class="sxs-lookup"><span data-stu-id="94e67-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="94e67-111">Les enregistrements d’hôte DNS (Domain Name System) doivent exister pour la nouvelle entrée avant qu’un client ou un serveur puisse se connecter au nouveau nom du pool.</span><span class="sxs-lookup"><span data-stu-id="94e67-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="94e67-112">Pour pouvoir répliquer les données de configuration vers ce pool, sélectionnez **activer la réplication des données de configuration** .</span><span class="sxs-lookup"><span data-stu-id="94e67-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="94e67-113">Supprimez la coche si vous ne souhaitez pas répliquer les données de configuration.</span><span class="sxs-lookup"><span data-stu-id="94e67-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="94e67-114">Paramètres de saut suivant</span><span class="sxs-lookup"><span data-stu-id="94e67-114">Next Hop Settings</span></span>

<span data-ttu-id="94e67-115">Dans la liste déroulante, vous pouvez spécifier le serveur tronçon suivant du pool de serveurs d’applications de confiance en sélectionnant le serveur frontal Enterprise Edition défini dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="94e67-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="94e67-116">Un réalisateur ou un pool de réalisateurs n’est pas une sélection valide pour le tronçon suivant d’un serveur d’applications de confiance et n’apparaîtra pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="94e67-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="94e67-117">Cliquez sur **OK** pour accepter et enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="94e67-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="94e67-118">Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.</span><span class="sxs-lookup"><span data-stu-id="94e67-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

